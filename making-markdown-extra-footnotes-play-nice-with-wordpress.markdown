Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/thoughts/making-markdown-extra-footnotes-play-nice-with-wordpress
Post: 197
Title: Making Markdown Extra Footnotes Play Nice with Wordpress
Slug: making-markdown-extra-footnotes-play-nice-with-wordpress
Keywords: php, wordpress
Status: publish
Date: 2008-09-03 21:56:33 -0500
Pings: On
Comments: On
Category: thoughts

Recently I started using [PHP Markdown Extra][1] in order to format my posts. I decided to make the switch mostly because I find
writing Markdown slightly more natural than writing HTML; more than that though I find reading and editing posts I've previously
written using Markdown to be as easy as reading a regular word document or a book. Of course, the readability of Markdown text was
sort of the point of the syntax so my observations seem a touch obvious. The crux of my point stems from my reasons for switching
so it felt necessary to elucidate my position.

[1]: http://michelf.com/projects/php-markdown/extra/ "PHP Markdown Extra"

Through the course of learning the Markdown Extra Syntax I found it supported footnotes, for me this was exciting because I have a
tendency when writing to have a lot of tangential thoughts. I usually[^1] use parentheticals to capture these ancillary musings
but I have noticed this tends to detract from the primary issue during reading. Clarity is something I strive for when writing[^2]
and so I figured it would be better to store my tangents away from the rest where they wouldn't detract from the point I was
trying to get across.[^3]

I jumped into using footnotes with both feet and had soon written two posts[^4] making liberal use of footnotes. Upon inspection
of the posts on the front page I noticed the references didn't behave correctly. After some brief investigation I discovered the
ids were the same for every set of footnotes which was frustrating for a couple reasons.

1. The footnotes aren't much use if they don't actually work
2. Duplicate ids means the document won't validate, which makes me sad.

I immediately descended on the problem in an attempt to rectify the situation. To make a long[^5] story short I ended up creating
a SHA1 hash of the footnote's text and using it as an identifier for the references and ids. This works quite well for my purposes
since it seems fairly unlikely I'll be using the same footnote text over and over again[^6], however there are some pretty
obvsious weaknesses to this strategy, which I'll outline below. *But first* I wanted to provide a downloadable patch of the
changes I made in order to make this footnote stuff work: you can get the [Wordpress Friendly Markdown Footnotes][2] patch and
apply it in order to get this working for yourself. I created the patch using git, so if it proves difficult to apply let me know
in the comments or via one of the contact methods on [my about page][3] and I'll fix it up lickity split.

[2]: http://bryanjswift.com/bjs-blog/wp-content/uploads/2008/09/markdown-wordpress-footnotes.patch "Markdown Wordpress Footnots"
[3]: http://bryanjswift.com/about/ "About Bryan J Swift"

Now about those weaknesses; the major problem comes about if you want to use the same footnote text a couple of times. I could
see this coming about more on a site publishing research papers than here but that isn't the point. A better method would have
been to use the Wordpress post id via `<?php the_ID(); ?>` because then the footnote references for the post are all constrained
by a shared value. This was in fact my first idea but it seems core Wordpress loop functions are not available inside filters.
This made me wonder if perhaps there wasn't another way to get the post id, either from a filter argument or from some other
magical place. Needless to say I couldn't figure another way out or I would have used the post id method instead. Another issue,
though I guess it's not really a weakness, is the SHA1 makes the references a bit long and unsightly, not to mention meaningless.
However, I was just happy to get the thing to work.

That is all for now, I'll post updates if I make any improvments or changes.

[^1]: or should I say used to?
[^2]: even if it is remarkably difficult for me to achieve.. darned words.
[^3]: can you tell I was working on my vocab in this paragraph?
[^4]: plus a test post for learning markdown syntax
[^5]: well, long-ish
[^6]: that would be kind of foolish wouldn't it?
