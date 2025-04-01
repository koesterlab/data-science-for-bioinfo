# version control

## git: the version control tool

For quite some years, [`git`](https://git-scm.com/) has become the de-facto standard for distributed version control.
It can be used to granularly track changes to your code base while collaborating in within and across teams.
And its wide adoption means that it integrates well into the graphical user inteface of any modern [integrated development environment (IDE)](ide.md), while you can also use it directly on the [command line](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line).

### learning git

* [happy git with R](https://happygitwithr.com): A very good and comprehensive, self-paced course for learning how to use git, applying this to coding in R (and integrating it with using the RStudio IDE). 
* [git book](https://git-scm.com/book/en/v2): The [`Getting Started`](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) and [`Git Basics`](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository) chapters should get you going, the following chapters introduce you to more advanced applications.
* [wizard zines git cheatsheet](https://wizardzines.com/git-cheat-sheet.pdf): A git cheat sheet with the most important git subcommands at one glance. Having this printed out and ready at hand will make looking them up a lot quicker. Also, the maker of this cheat sheet (Julia Evans), has a bunch of [useful blog posts about `git`](https://jvns.ca/categories/git/) and two helpful [wizard zines (booklets)](https://wizardzines.com/) called "how git works" and "oh shit, git".
* [interactive git cheat sheet](https://ndpsoftware.com/git-cheatsheet.html): For interactively exploring different git subcommands and what they do, with a visualization of different places where code changes can be tracked, this is a very cool tool. It's for playing around or looking stuff up once you feel a bit more comfortable with git.
* [git command reference](https://git-scm.com/docs): In addition to a full reference of all git subcommands (that you can execute on the command line), this page also provides links to the above mentioned cheat sheets.

## GitHub: *de facto* standard online platform to work with git repositories

[GitHub](https://docs.github.com/en) has become the *de facto* standard for distributed version control using `git` repositories.
It has [extensive free features](https://github.com/pricing#compare-features), especially for publicly hosted repositories.
This includes continuous integration resources, even for private repositories.
And GitHub provides extensive documentation.
However, repositories will be hosted on company servers that will not necessarily conform to your country's data regulations.
Thus, for certain projects you might have to use an in-house platform like GitLab (see below).

## GitLab: Open Source online platform to work with git repositories

[GitLab](https://docs.gitlab.com/) is an [Open Source](https://opensource.org/osd) alternative to GitHub, with most of the same features.
As the platform itself is Open Source code, it can be [installed and hosted in-house](https://docs.gitlab.com/ee/install/) by an institution.
Thus, it is the go to solution for educational and research instutions that want to avoid having (private) repositories hosted on outside servers.

## collaborating using git: git, GitHub and GitLab flow

For collaborative work on a code base, you need to agree on some basic rules of how to use git and GitHub or GitLab.
Usually, you can pick up on a lot of these conventions by simply using one of the online platforms and by looking at existing projects.
Most of them implicitly use [GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow), so reading through the explanation linked here will get you a long way.

GitHub flow is a reduction of the more complicated [git flow](https://nvie.com/posts/a-successful-git-branching-model/) from 2010 to setup where code is released often and quality is assured by continuous integration.
Should you ever encounter a project where GitHub flow does not provide the level of control you need, [GitLab flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html#production-branch-with-gitlab-flow) should get you started.
