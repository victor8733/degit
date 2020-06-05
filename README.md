<img src="/logo.svg" width="64px"/>

DeGit is a decentralized Git project hosting and maintenance platform.
You can join by starting a node and creating a project, using
your web browser pointing at `127.0.0.1`, just like you
work with GitHub. There will is no central point of failure,
since the network of nodes is run by anonymous volunteers.

To start it simply do (it uses your `.ssh/id_rsa` for authentication):

```bash
$ gem install degit
$ degit run
```

In a few seconds you can open `https://localhost:8080` and enjoy
the system, which is very similar to GitHub.

## Motivation and Related Works

We are not the first who are thinking about a decentralized solution
for Git repositories hosting and managing. There were a few similar products
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
  * It is entirely free for public and private repositories,
  * The data is not owned by anyone,
  * Misconduct is moderated by the board of deputies.
