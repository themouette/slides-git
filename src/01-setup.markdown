<!-- .slide: data-background="img/setup/setup.jpg" data-background-size="cover" class="no-title black" -->

# Setup


---

## Download an install

Refer to [online
documentation](http://git-scm.com/book/en/Getting-Started-Installing-Git)

---

## git help

<p style="margin:50px auto;">To get some help on a command.</p>

``` sh
$ man git-commit
$ git help
$ git help commit
```

[Git Book](http://git-scm.com/book/en/v2/) is a golden mine too.

---

## Generate an ssh key

``` sh
$ cd ~
$ ssh-keygen -t rsa
$ cat id_rsa.pub
ssh-rsa
AAAAB3NzaC1yc2EAAAABIwAAAQEAyyA8wePstPC69PeuHFtOwyTecByonsHFAjHbVnZ+h0dpomvLZxUtbknNj3+
c7MPYKqKBOx9gUKV/diR/mIDqsb405MlrI1kmNR9zbFGYAAwIH/Gxt0Lv5ffwaqsz7cECHBbMojQGEz3IH3twEvDfF6cu5p
00QfP0MSmEi/eB+W+h30NGdqLJCziLDlp409jAfXbQm/4Yx7apLvEmkaYSrb5f/pfvYv1FEV1tS8/J7DgdHUAWo6gyGUUSZ
JgsyHcuJT7v9Tf0xwiFWOWL9WsWXa9fCKqTeYnYJhHlqfinZRnT/+jkz0OZ7YmXo6j4Hyms3RCOqenIX1W6gnIn+eQIkw==
my computer
```

Then add the public key content to github, bitbucket, gitlab or any other server and test everything is all right.

``` sh
$ ssh git@github.com
Hi themouette! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## Configure your identity

``` sh
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```


---

## Configure your editor

Default is `vi`, but if you really want to change:

<pre style="margin-top: 50px;"><code class="sh">
$ git config --global core.editor emacs
</code></pre>

<pre style="margin-top: 50px;"><code class="sh">
$ git config --global core.editor \
    "'C:/Program Files/Notepad++/notepad++.exe' \
    -multiInst -notabbar -nosession -noPlugin"
</code></pre>

<p style="margin-top: 50px;">
[Vi cheat sheet](http://www.digilife.be/quickreferences/QRC/Vi%20Reference%20Card.pdf)
</p>


---

## Configure your diff tool

<pre style="margin-top: 50px;"><code class="sh">
$ git config --global merge.tool vimdiff
</code></pre>

<p style="margin-top: 50px;">
[Kdiff3](http://kdiff3.sourceforge.net/)
</p>


---

## Add some alias

* [Everyday git aliases](http://code.joejag.com/2013/everyday-git-aliases/)
* [Must have git aliases](http://durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/)

