<!-- .slide: data-background="img/branches/use-branches.jpg" data-background-size="cover" class="no-title" -->

## Branches

---

## Linear History

![](img/branches/linear-history.png)

---

## Typical git repository

![](img/branches/branches.png)


---

## Branches

The **top** of a linked list has a name: the **BRANCH** name.

![](img/branches/branch.png)

---

## Tag

A **Tag** is a label on a commit.

![](img/branches/tag.jpg)

---

## Notes On Tags

* **HEAD** is a symbolic ref, which points to the **current branch**.
* Whereas branches moves, tags doesn't

---

## git branch

<p style="margin:50px auto;">List, create, or delete branches</p>

``` sh
(master) $ git branch my-branch

(master) $ git branch
    * master
    my-branch

(master) $ git branch -d my-branch
```

<p class="fragment" style="margin-top:50px;font-style:italic;">Only local branches can be managed</p>


---

## git checkout <i>my-branch</i>

<p style="margin:50px auto;">Switch working directory to `my-branch`</p>

``` sh
(master) $ git branch my-branch
(master) $ git checkout my-branch

(my-branch) $ git branch
    master
    * my-branch
```

<p class="fragment" style="margin-top:50px;font-style:italic;">You can use shortcut `git checkout -b my-branch`</p>


---

## git rebase <i>master</i>

<p style="margin:50px auto;">Replay the current branch on top of `master`.</p>

``` sh
(mywork) $ git rebase master
```

![](img/branches/rebase.png)

<p class="fragment" style="margin-top:50px;font-style:italic;">If merge is not obvious, git asks you to solve conflict manualy.</p>


---

## git merge

<p style="margin:50px auto;">Join two or more development histories together.</p>

``` sh
(master) $ git merge iss53 --no-ff
```

![](img/branches/merge.png)

<p class="fragment" style="margin-top:50px;font-style:italic;">Using `--no-ff` keeps track of the feature branch.</p>


---

## git cherry-pick

<p style="margin:50px auto;">Pick a commit and apply it on current **HEAD**.</p>

``` sh
(master) $ git cherry-pick 8a6e1a3
```

![](img/branches/cherry-pick.png)


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
