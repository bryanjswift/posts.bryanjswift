Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/reflections/releasing-my-first-wordpress-theme
Post: 244
Title: Releasing My First Wordpress Theme
Slug: releasing-my-first-wordpress-theme
Keywords: freelance, wordpress
Status: publish
Date: 2009-01-25 19:52:43 -0500
Pings: On
Comments: On
Category: reflections

When I started work on the Wordpress theme for this blog I did so with thoughts of eventually releasing it into the wild but at the time releasing it was by no means the immediate goal. I wrote the theme myself because I wanted a reason to dive into some PHP as well as because I knew familiarity with (one of) the most popular blogging platforms could only be good for me. I started work on it around the time Wordpress 2.5 was released and [github][github] shows my first commit on 10 May 2008 though I know I started working on it prior to that because the first commit contains a pretty recognizable set of files.

[github]: http://github.com

After working on it for a while I it got to a point where I was more or less satisfied with the way it looked in my primary browsers of concern[^1]. I largely ignored IE(Internet Explorer) because to be honest I didn't expect much traffic and what traffic I figured I get I didn't believe would be using IE. As a result I was content with my theme and while I realize it's not a pillar of web design or anything I think it serves it's purpose and features the important part, the content, prominently.

This all brings me up to about a week ago[^2] when I decided I could use some supplementary income and at the time I thought things looked 'ok' in IE and so it would be quick to polish things off, get it uploaded and wait to see if it got approved. However, once I read the information available on [themeforest][themeforest] and realized what files where required and that there was an approval process I realized I had to take this a little more seriously. Not to mention that when I actually looked at the theme (and hence this site) in IE I realized how wrong I had been about the couple of quick fixes and then upload.

[themeforest]: http://themeforest.net

Knowing someone was going to be reviewing my work also made me a little more critical of it. I had included some MooTools in order to accomplish some pretty basic things. I did this mostly out of laziness and so upon looking at my work critically I knew this needed to come out because the 7 or so lines of JavaScript I had written using MooTools were certainly not enough to justify the library's inclusion (as much as I do love me some Moo). So I took out MooTools and rolled my own native JavaScript to handle things like IE6's lack of :hover support and IE's general lack of :last-child support.

There were also some pretty nasty float bugs to clean up and in the process of all that I decided to take a sip the CSS3 Kool-Aid and smarten my suckerfish menus up for browsers supporting box-shadow. After the bugs were squashed and a little CSS3 was tossed in there I had to do something I never thought I'd have to do for a Wordpress theme; write documentation. After documentation it was just putting together zip files and taking some screenshots.

All in all I think developing this theme was a good experience[^3] and I'm actually looking forward to creating another theme as soon as I have a good idea for it.

[^1]: Firefox, Camino and Safari
[^2]: my github graph says I started committing again in earnest on 18 Jan 2009
[^3]: it was also the first project I used [git][git] for

[git]: http://git-scm.com
