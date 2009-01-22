Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/reflections/the-lesson-about-usr
Post: 239
Title: The Lesson About /usr
Slug: the-lesson-about-usr
Keywords: *nix, mac, software
Status: publish
Date: 2009-01-22 08:50:21 -0500
Pings: On
Comments: On
Category: reflections

Lately I have taken it upon myself to upgrade certain unix friendly applications which ship by default with Mac OS X Leopard. I can not say for sure what started this but I'm fairly certain it began with [MacFuse][1] and and my desire to find various things which would allow me to make use of this awesome bit of technology. The first one I found was [sshfs][2] which is available as from the MacFuse developers. Soon after I read something about the mystically difficult to find ftpfs. For reasons I can no longer recall I decided I simply had to find and install it. The one I found was [curlftpfs][3] and when I attempted to compile it I quickly discovered my version of curl was not up to snuff.

[1]: http://code.google.com/p/macfuse/
[2]: http://code.google.com/p/macfuse/wiki/MACFUSE_FS_SSHFS
[3]: http://curlftpfs.sourceforge.net/

Having been shamed once by an installer I quickly reached out in search of the latest version of curl's source. After all I've done the `configure; make; make install` routine plenty of times before. Sadly it took me far too long to realized the *vast* majority of time I've done the `configure; make; make install` routine it was to install **new** software not upgrade existing packages. So I went through the process the first time and couldn't get curlftpfs to compile still; curl had not been compiled to the correct location because the old version of curl was still being found in the path. Running blithely ahead I recompiled with the 'correct' prefix of /usr. Now this install location should have been my second clue signifying I should stop what I was doing. Instead I moved right along compiling and installing into the /usr directories. I finished compile attempt number two for curlftpfs having learned it had not been compiled with some necessary option enabled and so it was time to compile curl *again* this time with the option enabled. Of course here the configure fails because I am missing the necessary libraries.

Naturally forging ahead I go and get the missing libraries compile and install them and try curl again. I have forgotten the reason but I know I was doomed for a couple more failures before I attempted to do what I should have done in the first place which is use my already installed [MacPorts][4] and just upgrade. Which is what I eventually try. However, it would appear the port command provided by MacPorts also relies on curl so this is a total bust. At this point I've forgotten all about getting curlftpfs to work and just want curl and port working again. By this time my frustration must have been palpable because I have no recollection of what I did to get those two things correctly compiled and running again.

[4]: http://www.macports.org/ 

The lesson I have learned from this is pretty simple. *Don't mess with the /usr directory without a backup/restore plan.*
