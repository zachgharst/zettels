# Write Better Commits, Build Better Projects

I love this article. [Write Better Commits, Build Better
Projects](https://github.blog/2022-06-30-write-better-commits-build-better-projects/)

I've always been a big fan of reading and reviewing code commit by
commit. Compare the two following styles:

* Commit #1: Do a lot of work to support version 7.8.12 of new runtime.
  Changes to 32 files.
* Commit #2: Fix unexpected bug of new runtime. Changes to 3 files.
* Commit #3: Pipeline change to support new runtime. Changes to 1 file.

Now picture the same individual. They do a bunch of work, figure out
what needs to be done. They make one large commit on a *practice*
branch. Then, they look at the diff between the main branch and their
practice branch; they now make the smallest, incremental steps they can
and detail what they did in each commit:

* Commit #1: Update ORM library. 3 changes.
* Commit #2: Uninstall unused dependency. 4 changes.
* Commit #3: Change deprecated methods to new interfacings. 6 changes.
* Commit #4: Switch project build target for runtime. 1 change.
* Commit #5: Add runtime target to pipeline. 1 change.
* Commit #6: Switch to new friendly syntax of new runtime. 14 changes.
* Commit #7: Adhere to style enforcement. 10 changes.
* Commit #8: Fix unexpected bug of new runtime. 3 changes.
* Commit #9: Update README to reflect new state of project. 1 change.

Each commit has semantic meaning. I know that when I click on commit #7,
even though it has a lot of changes, I should only be seeing stuff like
changes to indentation, braces, etc. rather than these types of changes
adding noise to the PR. As well, there's serious value in being able to
read through the history of the repo to understand the code. Detailed
pull request commits should detail: the current problem, what's changing
to address the problem, and how the change is tested.

The article on GitHub takes it a step beyond -- reorder and squash
commits. `git commit --fix-up [commit]` is new to me, too, and I want to
learn more about it and play with it some.

