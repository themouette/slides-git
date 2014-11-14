Git Hooks
=========

Hooks are located in `.git/hooks` directory.

The only requirement for a hook to run, is to be executable:

``` sh
chmod +x .git/hooks/pre-comit
```

To find more information about git hooks:

``` sh
git help hooks
```

## Local Hooks

First, let's create a pre-comit hook to validate newly committed lines has no
trailing whitespace:

See http://stackoverflow.com/questions/591923/make-git-automatically-remove-trailing-whitespace-before-committing

``` sh
# file .git/hooks/pre-comit
if (/\s$/) {
    bad_line("trailing whitespace", $_);
}
```

## Server Hooks



## Web Hooks

When using GitHub or Gitlab, in repository settings you can declare a web hook.

This is a URL that will be called every time the hook would be called.
