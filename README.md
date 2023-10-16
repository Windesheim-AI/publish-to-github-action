# `publish-to-github-action`

A GitHub Action to push any local file changes, including new files, back to supplied branch name.

This action is useful to put *after* other actions that modify files in the local checkout
that you'd then like to persist back into the repository.

Usage:

```
- uses: koenvanmeijeren/publish-to-github-action@master
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    BRANCH_NAME: '' #optional defaults to master
```

If you can get away with only ever writing new files, instead of updating them, you won’t regret it ;) Every time you update a file you retain the history of the file. Over time this can become quite large and contain a lot of duplicate data, even when using Git LFS as described below. The only way to garbage collect this historical data is to use a [hefty Java program called BFG](https://rtyley.github.io/bfg-repo-cleaner/) to re-write the history.
