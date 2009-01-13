Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/thoughts/working-with-git-svn-a-workflow
Post: 109
Title: Working With git-svn; a Workflow
Slug: working-with-git-svn-a-workflow
Keywords: *nix, git, git-svn
Status: publish
Date: 2008-08-31 22:32:04 -0500
Pings: On
Comments: On
Category: thoughts

As I wrote [earlier][1] I've been using git at work via git-svn with a Subversion repository. At first I thought this was brilliant and would solve my continuous branching and merging ails. As it turns out I wasn't entirely correct[^1].

[1]: /2008/08/02/using-git-with-a-multi-branch-subversion-repository/ "Using Git with a Multi-Branch Subversion Repository"

See, while I like git and how easy it makes branching and merging git-svn doesn't play quite as nicely[^2] with branches and merges and rebases as I hoped. Maybe part of my problem is that I needed to keep some of the git branches (which didn't originate as SVN branches) in sync across a couple computers. In order to do this I set up my server[^3] to store the git repository related to my work's SVN repository. The problem with this is every time I fetched and merged from the repository hosted on my server and then did a `git svn rebase` I wound up having to go through and 'resolve' all the conflicts coming from a the svn commits pulled in from the rebase on another computer. Not only was this incredibly annoying but it also meant there was the distinct possibility of winding up with double commits when I next did a `git svn dcommit`.

I'm not too ashamed to admit I had this problem a couple of times before I figured out I needed to use one branch to keep everything synced up with SVN (site_trunk in my case) and another, or several others as the case may be, to do the development work in. This way I use `git svn rebase` and `git svn dcommit` from only the place which is following the SVN branch and do merges as necessary to keep other branches up to date with work which has been done. As a result the 'svn branch' is only used to contact and deal with the SVN repository all other work is done elsewhere. Since I adopted this process I have had no problems with rebasing or double commits.

[^1]: It seems I only blog about things I get wrong. I guess that's good cataloging my mistakes in order to learn from them but it still seems odd to me.
[^2]: In my experience.
[^3]: The one that host's this site.
