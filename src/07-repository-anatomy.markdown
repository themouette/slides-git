<!-- .slide: data-background="img/repository-anatomy/surgery.jpg" data-background-size="cover" class="no-title black" -->

# Under the hood

## Anatomy Of A Repository

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

---

## Configuration

---

## 3 Types Of Objects

* blob
* tree
* commit

---

### Blob

Each **FILE** that you add to the repo is turned into a **BLOB** object.

---

### tree

Each **DIRECTORY** is turned into a **TREE** object.

_Obviously, a tree object can contain other tree objects and blob objects, just like a directory can contain other directories and files._

---

### Commit

A **commit** is a snapshot of your working tree and a pointer to previous commit.

![](img/repository-anatomy/commit.png)

---

## References

* tag
* branch
