GIT practical
=============

This practical is for 2 students. Each student choose a role: A or B.
When an exercise mention Release master, actions are be done only once on a
separate repository. Both students should follow those steps together.

## Start the project

**Release Master**

Create a new directory and initialize an empty git repository:

``` sh
$ mkdir blessed
$ cd blessed
$ git init
```

Add an README.markdown file and create the initial commit:

``` sh
$ touch README.markdown
$ git add README.markdown
$ git commit
```

Then create a brand new `foo` project on Gitlab server. This project belongs to
a group and not an individual.

Follow the instruction to push foo project on the server.

You just created the **blessed repository**

> When blessed repository is initialized, you can remove it from your own
> file system, you should never work on blessed repository directly.

## Fork project

**Player A and Player C**

Go on Gitlab server and fork the blessed repository.

On your computer clone your own repository:

``` sh
$ git clone git@gitlab:user/foo.git
$ cd foo
```

## Reference blessed repository

**Player A and Player B**

To keep your repository in sync with latest blessed development, you must
reference it as a remote:

``` sh
$ git remote add blessed git@gitlab:group/foo.git
```

## Feature branches

**Player A and Player B**

> Note that for this step, you must replace playerX with your very own role.

Create a new branch `feature-profile`.

``` sh
$ git checkout -b feature-profile
```

Create a new file `profile/playerX.md` and put your name in it.

Add and commit this file. Push your new branch to your fork:

``` sh
$ git add profile/playerX.md
$ git commit
# add the commit name
$ git push origin feature-profile
```

## Create a merge request

**Player A and Player B**

In the Gitlab interface, create a new merge request, you want to merge your
branch `feature-profile` into the blessed `master` branch.

## Accept a merge request

**Release Master**

In Gitlab interface, accept both merge requests and have a look to blessed
Network tab.

> Everything went fine as both changes are orthogonal.

## Rebase your work

**Player A and Player B**

Go back to master branch, fetch new blessed commits and rebase your master
branch to reflect blessed state:

``` sh
$ git checkout master
$ git fetch blessed
$ git rebase blessed/master
```

> Note: to remove your local branch, just do:

``` sh
$ git branch -d feature-profile
```

## Rebase interactive

**Player A and Player B**

Both of you will work on `README.markdown` to provoke a conflict.

``` sh
$ git checkout -b feature-readme
```

Add following content:

```
Git is a free and open source distributed version control system designed to
handle everything from small to very large projects with speed and efficiency.

I, PlayerX will enjoy using it every day.

Git is easy to learn and has a tiny footprint with lightning fast performance.
It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with
features like cheap local branching, convenient staging areas, and multiple
workflows.
```

Add, commit and push.

``` sh
$ git add README.markdown
$ git commit
```

You just realised you forgot to replace `PlayerX` with your own ID, so do it and
commit your changes.

To beautify history, you will merge the two latest commits into one:

``` sh
$ git rebase -i HEAD~2
```

Replace the second line `pick` with `f` and save the file.
Look at the log:

``` sh
$ git log
```

You just rewrote history !

Push your work:

``` sh
$ git push origin feature-readme
```

Then open a new Merge Request on blessed repository.

## Manage conflicts

**Release master** Accepts One of the requests. The second can't be merged
automatically.

You must rebase your work against blessed master to make it mergeable:

``` sh
$ git fetch blessed
$ git checkout master
$ git rebase blessed/master
$ git checkout feature-readme
$ git rebase master
# As history has been rewritten, you must force push
$ git push -f origin feature-readme
```

The merge request can be merged automatically.


**We're done, enjoy your GIT journey !**
