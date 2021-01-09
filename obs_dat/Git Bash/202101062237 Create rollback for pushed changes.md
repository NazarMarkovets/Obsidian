#GitBash 

If you make some changes in the project and push them you can go back using 

```bash
git checkout HEAD^ // go to the previous commits ONLY to look the changes
```

if you want to watch changes several times ago you can use

```bash
git log #look and select the log hash you need

git checkout [hash]
#or
git checkout HEAD^^ # go two steeps back
```

To revert changes some changes BUT lose them and go to the previous commit use. It works even you have pushed the commit some period before:

```bash
git reset --hard HEAD^ #reset changes and stay on the previous commit
```


If you have done some changes and ==you haven't added changes to the index== you can hide the changes to the start point of the stable commit

```bash
git stash #hide all changes before commit 
git stash apply #unhide changes for commit and push
```

if there will be some troubles with pushing use:
```bash
git push --force
```