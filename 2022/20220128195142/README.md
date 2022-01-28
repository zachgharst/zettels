# Sparse Checkout

Last night, I had an SSD become corrupt while playing a game. While trying to organize my drives, I physically broke off pins off another hard drive! I managed to have backups of all my data, so that wasn't a problem.

I have a unique challenge now though. One of the projects I was working on is **gigantic**. I wanted to look into how to only check out parts of the project that I needed instead of the entire thing.

https://stackoverflow.com/questions/600079/how-do-i-clone-a-subdirectory-only-of-a-git-repository

```
$ mkdir <repo>
$ cd <repo>
$ git init
$ git remote add -f origin <url>
$ git config core.sparseCheckout true
$ echo "some/dir/" >> .git/info/sparse-checkout
$ echo "another/dir/" >> .git/info/sparse-checkout
$ git pull origin master
```

It works great!

Allegedly, but I haven't tried this yet, there's also a new sparse-checkout command.

```
$ git clone --no-checkout <url>
$ cd <url>
$ git sparse-checkout init --cone
$ git sparse-checkout set "some/dir/"
```
