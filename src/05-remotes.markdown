<!-- .slide: data-background="img/remotes/enter-remotes.jpg" data-background-size="cover" class="no-title" -->

# Enter remotes


---

## Remote

A remote is a mirror of your local repository.

![](img/remotes/remotes.png)


---

## git clone <i>remote</i> <i>[path]</i>

<p style="margin:50px auto;">Clone a repository into a new directory.</p>

``` sh
$ git clone git@github.com/themouette/fossil-core.git

(master) $ git branch -a
    * master
    remotes/origin/HEAD -> origin/master
    remotes/origin/master
```

<p class="fragment" style="margin-top:50px;font-style:italic;">You can use http(s) or ssh to communicate with remotes.</p>
<p class="fragment" style="margin-top:50px;">Default remote is names `origin`.</p>


---

## git remote

<p style="margin:50px auto;">Manage remote mirrors.</p>

``` sh
$ git remote
origin

$ git remote show origin
* remote origin
Fetch URL: git@github.com:themouette/fossil-core.git
Push  URL: git@github.com:themouette/fossil-core.git
HEAD branch: master
Remote branch:
    master tracked
Local branch configured for 'git pull':
    master merges with remote master
Local ref configured for 'git push':
    master pushes to master
```

<p class="fragment" style="margin-top:50px;font-style:italic;">You can add multiple remotes.</p>


---

## git fetch

<p style="margin:50px auto;">Download objects and refs from another repository.</p>

``` sh
$ git fetch origin
```

![](img/remotes/fetch.png)

<p class="fragment" style="font-style:italic;">Note that nothing changes in your local direcory.</p>


---

## git pull [--rebase] <i>remote</i> <i>branch</i>

<p style="margin:50px auto;">Fetch and merge or rebase remote branch.</p>

``` sh
$ git pull --rebase origin master
```

<div class="fragment" style="margin-top:50px;font-style:italic;">
<p>Equivalent to:</p>

<pre><code class="sh">
$ git fetch origin/master
$ git rebase origin/master
</code></pre>
</div>


---

## git push <i>remote</i> <i>branch</i>

<p style="margin:50px auto;">Update remote refs along with associated objects.</p>

``` sh
$ git push origin serverfix
Counting objects: 20, done.
Compressing objects: 100% (14/14), done.
Writing objects: 100% (15/15), 1.74 KiB, done.
Total 15 (delta 5), reused 0 (delta 0)
To git@github.com:schacon/simplegit.git
* [new branch]      serverfix -> serverfix
```
<p class="fragment" style="margin-top:50px;font-style:italic;">Only fast forward
commits can be pushed</p>
