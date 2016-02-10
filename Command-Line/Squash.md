## How-To: Squash your Commits
1. Open your `.gitconfig` file, which is located in `~/.gitconfig` or simply open it in the CLI, typing `git config --global -e`
2. Add a new section containing the following line:
  
```
[alias]
  squash = "!f(){ git reset --soft HEAD~${1} && git commit --edit -m\"$(git log --format=%B --reverse HEAD..HEAD@{1})\"; };f"
```

3. Save your file and enjoy using the CLI command `git squash [Amount of Commits]`
4. To upload your squash to the remote you have to force push, using `git push --force [REMOTE] [BRANCH]`
