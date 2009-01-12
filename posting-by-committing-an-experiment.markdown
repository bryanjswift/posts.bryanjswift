Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/thoughts/posting-by-committing-an-experiment
Post: 228
Title: Posting By Committing: An Experiment
Slug: posting-by-committing-an-experiment
Keywords: git, github, wordpress, xmlrpc
Status: publish
Date: 2008-09-22 01:11:55 -0500
Pings: On
Comments: On
Category: thoughts

After seeing [a post on the github blog][1] about [David Baldwin][2] using github [as his blog][3] I got to thinking about how much easier it would be to create my markdown posts offline and then commit them to some repository and have them show up as blog entries.

[1]: http://github.com/blog/164-use-github-as-your-blog
[2]: http://github.com/bilson
[3]: http://github.com/bilson/blog/tree/master

The comments for the github entry point out a number of people using various solutions to achieve an effect similar to what I want however I am somewhat loathe to give up on a web interface in general and Wordpress in particular. But this did get me thinking, what about a post-commit hook so after every commit a script examines the changed files and creates or edits posts as necessary. Google didn't turn up much of anything in the way of making this happen and so I started thinking about how I would write my own solution.

As of right now I'm just in the planning stages but I did realize it would have to be a pre-commit hook on account of wanting to track the post id somewhere and the most logical place seems to be as some meta information at the top of the post. Currently I have the pre-commit hook reading the information I need to send about the post out of the file, the next step will be to figure out creating an XML object to send to the xmlrpc.php file of my Wordpress installation. In addition to dealing with hooks and xmlrpc[^1]  I'm writing the script using Perl in order to get some hands on experience with it.

I'll admit I'm not 100% sure I can make the script do what I want it to do but I'm certainly going to give it a shot because looking at the solutions eluded to in the comments of the post on github there doesn't look to be a solution to satisfy me yet.

My initial planning has the username, password and xmlrpc url being stored as config options via `git config username|password|xmlrpc` while post related information is stored in the actual post file. I think the most likely hang up will be modifying the file which is about to be committed (by adding the post id) because I believe I'd actually have to create the post via xmlrpc, write the response into the file, stop the commit, add the post file back to the index and re-commit. There may also be a problem with the way xmlrpc expects the categories.[^3] Time will tell.

[^1]: which I'd never done before
[^2]: title, categories, tags, post id, content
[^3]: xmlrpc wants category ids rather than category names
