# Git popular command for some purposes.

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinge)


## Overview
The repo will provide a list command usually use with git when developing a product. Include: basicly control source code, update the source code, merge code and some other problem when using with git.  

## Features

### Basic command
Starting of project a leader will create a initial project. In a initial project will include structure of project, requirements,... 
All of member will clone this repo and develop the fetures base on the this structure and save into their branch. 

```sh
git clone https://github.com/ngoctuhan/name_of_project.git  
```
Create a your branch 
```sh
git checkout -b your_branch 
```
Change into a branch
```sh
git checkout branch_name
```
Check current branch
```sh
git status
```
Check list local branchs, remote branchs
```sh
git branch 
git branch -r
git branch -a
```
Change name of a branch: if you want to change current branch
```sh
git branch -m new_name
```
Change name of other branch
```sh
git branch -m old_name new_name
```
Delete remote branch 
```sh
git push origin --delete my-branch-name
```
Delete local branch
```sh
git branch -d my-branch-name
```
Push code 
```sh
git add .
git commit -m 'what is changed'
git push 
```
If local branch is not exist to push:
```sh
git push -u origin my-branch-name
git push -u origin HEAD
```
Check difference between local branch & remote branch 
```sh
git diff 
```
## Fix some issues

Pull code but the has change in local, you want to pass all of change local:
```sh
git reset --hard HEAD
git clean -f -d
git pull
```
## How to naming banch

A good name of branch has format:
<type>_<issue id>_<name_of_issue>

- presenst purpose of branch. Type can is Feature, Fix, Refactor, Test…
- issue id (or task id, story id…) was defined on git or redmine, trello...
- name_of_issue: short description about purpose of issue.

## Development

### Rebase

In process coding at base branch has many commit from many people. So you are easy missing and conflict commit code with other person. So you must usually pull & update the lasted code from base branch. 

Example: You & team need dev a comerial product include many features: payments, buy, watch & select goods. Each a person will be asign a task. But everyone need start from master branch. Master banch was create by a leader. If anyone finish task then merge code into master. 

The avg time for task is around 3-4 days. So while you are coding the branch has many change and many update. This updateing can make for your code will conflict. So you need merge & fix conflict. If you don't process soom. The code will has many conflicts. 

So you must usually rebase code:

To rebase source code, Follow bellow step:
- commit source code at your branch.
- checkout into main branch git checkout <branch>, fetch (git fetch) và pull lastest source  (git pull)
- Back again your brach
- Conduct git rebase <branch-origin>
- Resolve conflict if exist

### Squash commits 

In Git you can merge several commits into one with the powerful interactive rebase. It's a handy tool I use quite often; I usually tidy up my working space by grouping together several small intermediate commits into a single lump to push upstream.

```sh
git rebase -i HEAD~N
```
where N is the number of commits you want to join, starting from the most recent one.

More: https://www.internalpointers.com/post/squash-commits-into-one-git

### Pull request

A pull request – also referred to as a merge request – is an event that takes place in software development when a contributor/developer is ready to begin the process of merging new code changes with the main project repository.

### Merge code
