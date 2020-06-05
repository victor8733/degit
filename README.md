<img src="/logo.svg" width="92px"/>

DeGit is a decentralized Git project hosting and maintenance platform.
You can join by starting a node and creating a project, using
your web browser pointing at `127.0.0.1`, just like you
work with GitHub. There will is no central point of failure,
since the network of nodes is run by anonymous volunteers.

To start, simply do (it uses your `.ssh/id_rsa` for authentication):

```bash
$ gem install degit
$ degit run
```

In a few seconds you can open `https://localhost:8080` and enjoy
the system, which is very similar to GitHub.

## Motivation and Related Works

We are not the first who are thinking about a decentralized solution
for hosting and managing of Git repositories. There were a few similar products
created before (if you know anything else, please submit a pull request):

  * [GitChain](http://gitchain.org/)
  * [GitTorrent](https://github.com/cjb/GitTorrent)
  * [git-ssb](https://scuttlebot.io/apis/community/git-ssb.html)
  * [git-dit](https://github.com/neithernut/git-dit)
  * [ZeroNet](https://zeronet.io/) (not exactly Git, but relevant)

Even though [GitHub](https://github.com),
[GitLab](https://gitlab.com),
[BitBucket](https://bitbucket.com), and
[Gitee](https://gitee.com) are great platforms,
they have three critical drawbacks:

  * They are [not](https://news.ycombinator.com/item?id=20499070) 100% reliable,
  * They [ban](https://medium.com/@catamphetamine/how-github-blocked-me-and-all-my-libraries-c32c61f061d3)
    users for
    [almost](https://medium.com/@hamed/github-blocked-my-account-and-they-think-im-developing-nuclear-weapons-e7e1fe62cb74)
    [no reason](https://en.wikipedia.org/wiki/Censorship_of_GitHub), and
  * They are under the [influence](https://techcrunch.com/2019/07/29/github-ban-sanctioned-countries/) of their local governments.

It seems that the need for a decentralized solution is obvious.
We believe that the community would enjoy having a platform
with the following features:

  * Pull requests, stars, and followers,
  * GitHub-like web user interface,
  * Entirely free for public and private repositories,
  * Not owned by anyone,
  * Moderated by the board of deputies.

## How It Works?

The following principles are behind the architecture of DeGit:

  * An author is the owner of a node, authenticated by his/her [RSA key](https://en.wikipedia.org/wiki/RSA_%28cryptosystem%29)
  * A repository is a combination of 1) Git files and 2) immutable stories
  * A story is an issue, a comment, a pull request, a star, a wiki page, etc.
  * Issues, PRs, and comments have hash codes instead of sequential IDs
  * Each story is RSA-signed by its author
  * Each node decides for itself which repositories to host
  * Give-and-take protocol is used: "the more you host for me, the more I host for you"
  * Commits are announced to neighbour nodes, which pull them if they like
  * Conflicts are resolved through DeGit Consensus Algorithm
  * Nodes communicate through HTTP RESTful interfaces

DeGit Consensus Algorithm (proof-of-availability):

  * A branch dominates during [merge](https://git-scm.com/docs/git-merge) if the providing node is more _available_
  * The _availability_ of neighbours is subjectively judged by each node
  * [Commits](https://git-scm.com/docs/git-commit) from less _available_ branches are ignored during merge
  * The _availability_ of itself is always zero

It is highly recommended to avoid making parallel commits to the
same branch, since it may lead to inability to merge and abandonded
(or lost) branches.

## How to Contribute?

Just give us a star and wait. We'll update this page soon.
