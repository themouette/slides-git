<!-- .slide: data-background="img/local-repository/plunge.jpg" data-background-size="cover" class="no-title" -->

# Local Repository

## Let's dive !

---

## git add <i>file</i>

<p style="margin:50px auto;">Add file contents to the **staging area**.</p>

``` sh
$ git add README
```

<p class="fragment" style="margin-top:50px;font-style:italic;">Track a file for the first time.</p>
<p class="fragment" style="font-style:italic;">Track changes on file since previous commit.</p>


---

## git checkout <i>[file]</i>

<p style="margin:50px auto;">Checkout a branch or paths to the working tree.</p>

``` sh
$ git checkout README
$ git checkout my-branch
```

<p class="fragment" style="margin-top:50px;font-style:italic;">Reset **file/path** to **staging area**'s version.</p>
<p class="fragment" style="font-style:italic;">Switch branch.</p>


---

## git commit

<p style="margin:50px auto;">Create a commit from current **staging area**'s status.</p>

``` sh
$ git commit
[master 8a6e1a3] My awesome message.D
2 files changed, 10 insertions(+), 4 deletions(-)
create mode 100644 img/01/branch.png
```

<p class="fragment" style="margin-top:50px;font-style:italic;">Returns the **commit hash** `8a6e1a3`.</p>
<p class="fragment" style="font-style:italic;">To edit your latest commit, use `git commit --amend`.</p>


---

## git status

<p style="margin:50px auto;">Show current working dirrectory and staging area.</p>


---

## git mv <i>src</i> <i>destination</i>

<p style="margin:50px auto;">Rename src into destination.</p>


---

## git rm <i>file</i>

<p style="margin:50px auto;">Delete file from tracking.</p>


---

## git log <i>[file]</i>

<p style="margin:50px auto;">Show commit logs.</p>

``` sh
$ git log

commit 8fbdc87e2f254c1c52ee9c2cae886985421fd3ef
Author: Julien Muetton <themouette@gmail.com>
Date:   Mon Aug 26 13:30:52 2013 +0200

    Init as an npm package

commit f8db4d12eea0174b8e8476c21510133e3bbd27e3
Author: Julien Muetton <themouette@gmail.com>
Date:   Mon Aug 26 13:24:20 2013 +0200

    First commit
```

<pre class="fragment" style="margin-top:50px;font-style:italic;">
<code class="sh">$ git log --graph --decorate  # Display network graph</code></pre>
<pre class="fragment">
<code class="sh">$ git log --stat # show stats</code></pre>
<pre class="fragment" style="font-style:italic;">
<code class="sh">$ git log --pretty=oneline --abbrev-commit # A commit per line</code></pre>


---

## git diff <i>[file]</i>

<p style="margin:50px auto;">Show changes between two states (commits, staging, working directory...)</p>

``` sh
$ git diff
diff --git a/index.html b/index.html
index de3bfb6..b3d2ddf 100644
--- a/index.html
+++ b/index.html
@@ -36,10 +36,16 @@

some awesome content
- some former content
+ some new content

```

<p class="fragment" style="margin-top:50px;font-style:italic;">`git diff topic..master` to compare branches.</p>
<p class="fragment" style="margin-top:50px;font-style:italic;">`git diff HEAD--8a6e1a3` to compare commits.</p>


---

## git stash

<p style="margin:50px auto;">Stash the changes in a dirty working directory away.</p>

``` sh
$ git stash
```

<p class="fragment" style="margin-top:50px;font-style:italic;">`git stash list` to list stashs.</p>
<p class="fragment" style="margin-top:50px;font-style:italic;">`git stash apply` to apply latest stash.</p>
<p class="fragment" style="margin-top:50px;font-style:italic;">`git stash pop` to apply and delete latest stash.</p>


---

## git blame <i>file</i>

<p style="margin:50px auto;">Show what revision and author last modified each line of a file.</p>

``` sh
$ git blame README

2c2513c7 (Julien Muetton    2013-08-26 18:48:45 +0200   1) # GIT basics
2c2513c7 (Julien Muetton    2013-08-26 18:48:45 +0200   2)
2c2513c7 (Julien Muetton    2013-08-26 18:48:45 +0200   3) ---
2c2513c7 (Julien Muetton    2013-08-26 18:48:45 +0200   4)
2c2513c7 (Julien Muetton    2013-08-26 18:48:45 +0200   5) ## Local first

```


---

## Transitions

![](img/local-repository/transitions.png)
