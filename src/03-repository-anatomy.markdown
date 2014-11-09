<!-- .slide: data-background="img/repository-anatomy/surgery.jpg" data-background-size="cover" class="no-title" -->

# Under the hood

## Anatomy Of A Repository

---

## Local first

Everything is local, remote operations are only for sharing.

---

## git init

<p style="margin:50px auto;">Create an empty git repository or reinitialize an existing one.</p>

``` sh
$ git init

Initialized empty Git repository in ~/.git/
```

<p style="margin-top:50px;font-style:italic;" class="fragment">
Running git init in an existing repository will **not** overwrite things that
are already there.
</p>

---

## Three Zones

![](img/repository-anatomy/zones.png)

<ul style="margin-top: 50px;">
    <li><strong class="fragment highlight-green">Working directory</strong>: the directory you work in;</li>
    <li><strong class="fragment highlight-red">Staging area</strong>: prepare next commit;</li>
    <li><strong class="fragment highlight-blue">Repository</strong>: history of every committed change.</li>
</ul>

<aside class="notes">
Everything in GIT is in one of the following area.
</aside>

---

# 3 Types Of Objects

* blob
* tree
* commit

---

## Blob

Each **FILE** that you add to the repo is turned into a **BLOB** object.

---

## tree

Each **DIRECTORY** is turned into a **TREE** object.

_Obviously, a tree object can contain other tree objects and blob objects, just like a directory can contain other directories and files._

---

## Commit

A **commit** is a snapshot of your working tree and a pointer to previous commit.

![](img/repository-anatomy/commit.png)

---

## `.git` directory

```
.git
|-- branches/
|-- hooks/
|-- info/
|-- logs/
|-- modules/
|-- objects/
|-- refs/
|-- COMMIT_EDITMSG
|-- config
|-- description
|-- HEAD
|-- index
`-- packed-refs
```
