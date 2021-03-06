<!-- .slide: data-background="img/getting-started/plunge.jpg" data-background-size="cover" class="no-title black" -->

# Getting Started

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

### Commit

A **commit** is a snapshot of your working tree and a pointer to previous commit.

![](img/repository-anatomy/commit.png)

---

## Three Zones

Everything in GIT is in one of those following area.

<ul style="margin-top: 50px;">
    <li><strong class="fragment highlight-green">Working directory</strong>: the directory you work in;</li>
    <li><strong class="fragment highlight-red">Staging area</strong>: prepare next commit;</li>
    <li><strong class="fragment highlight-blue">Repository</strong>: history of every committed change.</li>
</ul>

---

## Three Zones

![](img/repository-anatomy/zones.png)
