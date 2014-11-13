<!-- .slide: data-background-image="img/extras/extras.jpg" data-background-size="auto 90%" class="hide-title" data-background-color="#fff" -->

# Extras

---

## Submodules

> Avoid submodules

``` sh
git submodule add https://github.com/hakimel/reveal.js.git reveal.js

git submodule update --init
```

---

## Hooks

Extend Git behaviour

---

### Client Side

<div class="three-cols">
<div>
<h4>Commit Workflow</h4>
<ul style="margin-top: 55px;">
    <li>pre-commit</li>
    <li>prepare-commit-msg</li>
    <li>commit-msg</li>
    <li>post-commit</li>
</ul>
</div>

<div>
<h4>Email Workflow</h4>
<p style="font-size: 25px; line-height: 25px;">(when using `git am`)</p>
<ul style="margin-top: 15px;">
    <li>format-patch</li>
    <li>applypatch-msg</li>
    <li>pre-applypatch</li>
    <li>post-applypatch</li>
</ul>
</div>

<div>
<h4>Other</h4>
<ul style="margin-top: 55px;">
    <li>post-checkout</li>
    <li>post-merge</li>
    <li>pre-rebase</li>
    <li>pre-push</li>
</ul>
</div>
</div>

---

### Server Side

* pre-receive
* update
* post-receive

<blockquote style="margin-top: 60px;">
<p>Learn more on [Git Hooks](http://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)</p>
</blockquote>


