---
layout: default
---

[Back](../)

&nbsp;

# Command Collection

&nbsp;

<span style="color:green">Open VS Code in Browser in GitHub</span>  
```git
1. Öffnen eines Repositories im Browser in GitHub
2. Drücken der Taste "." öffnet Vs Code im Browser
```
&nbsp;

Command prints all configured remotes of the repository

```git
>> git remote -v
```
&nbsp;

Command prints the status of the current branch and its files

```git
>> git status
```
&nbsp;

Command prints the most recent commits and additional information

```git
>> git log
```
&nbsp;

Command changes current scope to branch <branch_name>

```git
>> git checkout <branch_name>
```
&nbsp;

Command creates list of every thing you've done in git, across all branches!

```git
>> git reflog
```
&nbsp;

Command lets you go back to old project state ('index' can be seen in 'git reflog')

```git
>> git reset HEAD@{index}
```
&nbsp;

Command is a *commit* with an automatic `git add .`

```git
>> git commit -am "text"
```
&nbsp;

Command to change message of last commit

```git
>> git commit --amend -m "new_text"
```
&nbsp;

Command to add files to last commit

```git
>> git add .
>> git commit --amend --no-edit
```
&nbsp;

Command to create custom git commands.  
Command creates a new command 'ac', that allows us to run an *add and commit* much faster.

```git
>> git config --global alias.ac "commit -am"
...
>> git ac "text"
```
&nbsp;

Command to make 'Log' more readable

```git
>> git log --graph --oneline --decorate
```
&nbsp;




&nbsp;

***