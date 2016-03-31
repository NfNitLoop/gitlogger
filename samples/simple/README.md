In this example, repo_a and repo_b push and pull directly to a centralized repo.

In [git.log] you can see that the `git --graph` gets complicated as it tries to
represent every merge's parent throughout the graph.

In [gitlogger.log], the history is greatly simplified. Since A pushed last, we
walk down the left-hand side of of the history starting from that commit. Any commits
that were introduced to that history as the right-hand side of a merge are
displayed as indented blocks. Merges inside of that indented history don't bother displaying
commits that are also part of the outer left-hand side's history.

One drawback of this approach is that the history of the master branch gets rendered
differently depending on who was the last to (merge and) push. You can avoid
this by using a [pull-request style workflow][pull_workflow], in which every code change is
merged into mainline as a non-fast-forward merge. 

In practice, though, this isn't too bad. Generally a developer is interested in
the history of his own branch, so determining LHS from his commits "makes
sense".

[git.log]: git.log
[gitlogger.log]: gitlogger.log
[pull_workflow]: ../pull_workflow


