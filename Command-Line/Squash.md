### How-to squash multiple commits in a single one
#### Add squash alias to .gitconfig (should be only done once)
- Type `git config --global -e` to edit the global .gitconfig file.
- To write on this file in vim just type `a`.
- Now you add `squash = "!f(){ git reset --soft HEAD~${1} && git commit --edit -m\"$(git log --format=%B --reverse HEAD..HEAD@{1})\"; };f"`to the [alias] section.
- To save this file in vim type `Esc:wq`.
#### Use the squash alias
- Go to your project location
- Select the right branch using `git checkout [BRANCH]`
- Type `git squash [amount of commits to be squashed]`. **It squashes the latest x commits of the current branch even if they aren't pushed to the remote yet!**
- Last you have to upload your squash to the remote by typing `git push -f [REMOTE] [BRANCH]`.
