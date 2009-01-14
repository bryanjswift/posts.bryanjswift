Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/reflections/posting-from-the-text-editor
Post: 233
Title: Posting from the Text Editor
Slug: posting-from-the-text-editor
Keywords: textmate, vim, xmlrpc
Status: publish
Date: 2009-01-11 23:31:15 -0500
Pings: On
Comments: On
Category: reflections

As much as I like Wordpress because of how easy it is to install and configure I really dislike composing posts in the textarea provided; even in Safari where the textarea can be expanded. I think it's mostly a mental block, inside a web browser does not seem the proper place to compose. In fact the browser writing is a significant contributor to why I haven't written for a while. Then fairly recently I stumbled upon the blogging bundle for TextMate.

The bundle interacts well with Wordpress through xmlrpc. Through the use of meta data at the top of a document the post is created along with tags and categories, the post slug can also be defined. This is peachy, TextMate is a much happier place to write... well anything really. However, TextMate is no longer my editor of choice as I've moved my text editing almost entirely to [MacVim][1].

[1]: http://code.google.com/p/macvim/

I started looking around for a plugin with similar functionality for VIM and found a script called [vimblog][2] by [pedro mg][3]. After downloading the plugin I noticed a couple of things I wasn't too fond of in it. The first thing I noticed was the lack of documentation which meant looking into the script to figure out usage. The second thing which bothered me was having to put my login credentials in the script which meant I couldn't keep it in sync between computers via [source control][4] nor could I use the script for more accessing more than one blog.

[2]: http://www.vim.org/scripts/script.php?script_id=2030
[3]: http://blog.tquadrado.com
[4]: http://github.com/bryanjswift/dotconfig

As a result of these limitations I forked [pedro's script source][5] and began hacking away at it. I'm not finished with it by any means in [my fork of the vimblog script][6] but I do at least have the login credentials and endpoint information in a separate file. I'm looking forward to continuing to develop this script as it is my first real endeavor into using Ruby during something other than tutorials.

[5]: http://github.com/pedromg/vimblog.vim
[6]: http://github.com/bryanjswift/vimblog
