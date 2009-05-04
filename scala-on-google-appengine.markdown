Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/thoughts/scala-on-google-appengine
Post: 255
Title: Some Thoughts About Scala on Google's Java AppEngine
Slug: scala-on-google-appengine
Keywords: appengine, java, persistence, scala
Status: publish
Date: 2009-05-04 02:18:15 -0400
Pings: On
Comments: Off
Category: thoughts

I've spent some more time over the last two weeks working on putting an idea of mine into action. My plan was to use Google AppEngine to serve the application and store it's data in BigTable. After I spent some time with [JDO][1] annotations and making sure I got them correct I sent the application to the AppEngine dev server using Ant on my local machine and received an odd [runtime exception][2]. I received a similar error when I pushed the application up to Google's servers. After spending quite a bit of time trying to debug an unfamiliar error I asked on the [Java AppEngine Mailing List][3] if there was [a problem with JDO annotations and Scala][4]. The response I got was that it was a known issue with the 1.1.0 version of the DataNucleus enhancement process.

[1]: http://db.apache.org/jdo/
[2]: http://pastie.org/458308
[3]: http://groups.google.com/group/google-appengine-java
[4]: http://groups.google.com/group/google-appengine-java/browse_thread/thread/54a897386164912/2ff3b8d712a001c3#2ff3b8d712a001c3

I did as the thread suggested and replaced the datanucleus-1.1.0 jars in the AppEngine SDK with downloaded 1.1.2 jars. This eliminated the runtime exception when deployed to both the dev server and Google's servers when attempting to save data. Sadly when I attempted to take the next logical step with the application code and retrieve data for display as well as save it I ran into a new exception. As far as I can tell the error is due to the internals of Google's datanucleus-appengine (1.1.0) jar being incompatible with the newer datanucleus jar files.

Despite how much I would have liked for persistence to be handled easily on the AppEngine, mostly because I wanted to use the Google's servers rather than having to host it myself, I am not really upset about being unable to use the JDO annotations. I could attempt to use JPA annotations rather than JDO and see if they work better but to be perfectly honest using the annotations forced the me to use mutable model classes which felt pretty un-Scala like to me. So for now I'm back to the proverbial drawing board on persistence and I'm even considering not using a persistence framework and interacting with the database through plain old SQL statements. I recognize this will force me to maintain the schema myself but at least I would feel like I was using the Scala language properly.

I did look for some Scala persistence frameworks but most everything I found is using Java based persistence in Scala classes and I'm just hoping to find a solution which feels more, I don't know... correct.
