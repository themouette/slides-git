<!-- .slide: data-background="img/branches/use-branches.jpg" data-background-size="cover" class="no-title blue" -->

# Branches

---

## Linear History

![](img/branches/linear-history.svg)

---

## Typical git repository

![](img/branches/branches.png)

---

## Tag

![](img/branches/tag.svg)

A **Tag** is a label on a commit.


---

## Branches

![](img/branches/branch.svg)

The **top** of a linked list has a name: the **BRANCH** name.

---

## Notes On Tags And Branches

![](img/branches/branch-head.svg)

* **HEAD** is a symbolic ref, which points to the **current branch**.
* Whereas branches moves, tags doesn't

---

## git branch

<p style="margin:50px auto;">List, create, or delete branches</p>

``` sh
(master) $ git branch feature

(master) $ git branch
    * master
    feature

(master) $ git branch -d feature
```

<p class="fragment" style="margin-top:50px;font-style:italic;">Only local branches can be managed</p>


---

## git checkout <i>my-branch</i>

<p style="margin:50px auto;">Switch working directory to `my-branch`</p>

<div class="two-cols is-middle">

<pre><code class="sh">
(master) $ git branch feature
(master) $ git checkout feature

(my-branch) $ git branch
    master
    * feature
</code></pre>

<p>
![](img/branches/git-checkout-branch.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/git-checkout-branch-1.svg) <!-- .element: class="fragment invisible-fragment current-visible keep-after" data-fragment-index="0" -->
</p>

</div>

<p class="fragment" style="margin-top:50px;font-style:italic;">You can use shortcut `git checkout -b my-branch`</p>

---

## git rebase <i>master</i>

<p style="margin:50px auto;">Replay the current branch on top of `master`.</p>

``` sh
(feature) $ git rebase master
```

![](img/branches/rebase.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/rebase-1.svg) <!-- .element: class="fragment invisible-fragment current-visible" data-fragment-index="0" -->
![](img/branches/rebase-2.svg) <!-- .element: class="fragment invisible-fragment current-visible" -->
![](img/branches/rebase-3.svg) <!-- .element: class="fragment invisible-fragment current-visible" -->
![](img/branches/rebase-4.svg) <!-- .element: class="fragment invisible-fragment current-visible keep-after" -->

<p class="fragment" style="font-style:italic;">If merge is not obvious, git asks you to solve conflict manually.</p>


---

## git merge

<p style="margin:50px auto;">Join two or more development histories together.</p>

``` sh
(master) $ git merge feature
```

![](img/branches/merge.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/merge-1.svg) <!-- .element: class="fragment invisible-fragment current-visible keep-after" data-fragment-index="0" -->

---

## git merge Fast Forward

``` sh
(master) $ git merge feature
```

![](img/branches/merge-ff.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/merge-ff-1.svg) <!-- .element: class="fragment invisible-fragment current-visible keep-after" data-fragment-index="0" -->

---

## git merge --no-ff

``` sh
(master) $ git merge feature --no-ff
```

![](img/branches/merge-no-ff.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/merge-no-ff-1.svg) <!-- .element: class="fragment invisible-fragment current-visible keep-after" data-fragment-index="0" -->

<p class="fragment" style="margin-top:50px;font-style:italic;">Using `--no-ff` keeps track of the feature branch.</p>


---

## git cherry-pick

<p style="margin:50px auto;">Pick a commit and apply it on current **HEAD**.</p>

``` sh
(master) $ git cherry-pick 8a6e1a3
```

![](img/branches/cherry-pick.svg) <!-- .element: class="fragment invisible-fragment fade-out" data-fragment-index="0" -->
![](img/branches/cherry-pick-1.svg) <!-- .element: class="fragment invisible-fragment current-visible" data-fragment-index="0" -->
![](img/branches/cherry-pick-2.svg) <!-- .element: class="fragment invisible-fragment current-visible" -->


---

## Note on conflicts

``` sh
$ git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.

$ git diff

<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
please contact us at support@github.com
</div>
>>>>>>> iss53:index.html

```

<div  class="fragment">
<p>Git is **verbose**, but for your first conflict...</p>
![](img/branches/better-call-saul.png)
</div>
