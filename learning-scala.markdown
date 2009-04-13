Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/reflections/learning-scala
Post: 247
Title: My Experience Learning Scala
Slug: learning-scala
Keywords: java, scala, software
Status: publish
Date: 2009-04-13 00:52:29 -0400
Pings: On
Comments: On
Category: reflections

Sometime in the last week I read an article about [Scala][1], actually I think it was the [interview with Twitter engineers about Scala vs. Ruby][2], and it really sparked an interest in the language for me. I'm sure at least part of the reason is because I've been writing mostly JavaScript lately and reading a description of Scala it seemed like a number of the functional programming practices I've picked up writing JavaScript would carry over well. At the same time though Scala is built on top of Java, a language I've become intimately familiar with even if it has fallen somewhat into disuse. Last week after reading the article and feeling this resonance with what I read further about Scala I decided to jump into it and see how much I could pick up.

[1]: http://www.scala-lang.org
[2]: http://www.artima.com/scalazine/articles/twitter_on_scala.html

The Scala website is well documented and has a number of good tutorials but something just wasn't clicking in my head about the syntax or the language in general. I think feeling like I could get a handle on this language quickly is what has really driven me to obsess about it this past week. I ordered [Programming in Scala][3] from Amazon (before [Amazonfail][4] as it's being called on Twitter) which I've read about 200 pages of and continued to read over (and over) the pdf tutorials available to me. This weekend I started putting together an application written in Scala to be deployed on [Google's AppEngine][5] since they released Java support and Scala compiles to Java. Additionally, my tentative plan for the application is to make use of a number of 'Social APIs' which are coming up more and more at work but I still know quite little about. The first API I decided to work with was Twitter's and in just a couple of days (maybe 16 hours) of work I have the basic model classes written along with BDD specs for them using [Scala Specs][6], and I'm also able to pull the data I want from Twitter and deploy to the AppEngine service. All in all I'd say not bad for a weekend's work. There is of course quite a bit left to do before the application is finished but I'm proud of the first steps I've made. If inclined, the source for this experiment is publicly viewable as [twitter-favorites on github][7].

[3]: http://readernaut.com/bryanjswift/books/0981531601/programming-in-scala/
[4]: http://neteffect.foreignpolicy.com/posts/2009/04/12/amazonfail_and_the_politics_of_anti_corporate_cyber_activism
[5]: http://code.google.com/appengine
[6]: http://code.google.com/p/specs/
[7]: http://github.com/bryanjswift/twitter-favorites

*[BDD]: Behavior Driven Development
