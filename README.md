# Git Commands 
## Log 

1) git log
2) git log --decorate --graph --oneline --all

## Commit

1) git commit --amend (to amend the commit msg)

## Comparison

1) git diff --staged HEAD
2) Working Directory/Staged for changes/Commited to REP(.git)
3) git log --oneline
4) git diff <c_hash_1> <c_hash_2>
5) git diff HEAD HEAD^(last commit -1)
6) git diff master origin/master

## Branching
1) git b my_new_branch
2) git ch my_new_branch
3) git b -m curr_name new_name
4) git b -d Bran_to_be_deleted
5) git log --oneline --graph --decorate
6) git merge branch_wa_wanna_merge_on_curr_checked_out_branch
7) shortcut for add and commit is 
 git c -am"branch : msg"

## Rebasing
1) git rebase master (on current checked out branch)
2) git rebase --abort (in case some conflict occured & you don't wanna proceed).
3) or resolve conflict then, git add, git rebase --continue
4) git pull --rebase origin master

## Stashing
1) git stash , git stash apply
2) git stash list, git stash drop
3) git stash pop (apply & delete)
4) git stash save "stash 1 msg"...3 times
5) git stash apply stash@{1}
6) git stash drop stash@{1}
7) git stash clear (to delete all the stashes)

stashing into a branch
1) git stash -u (to stash untracked(new) files as well)
2) git stash branch new_branch
 -new_branch is created, -stash applied, -stash is dropped.

## Tags
1) git tag myTag (creates a lightweight tag)
2) git tag --list (WARN : dont write -list or else tag named -list will be created)
3) git show myTag
4) git tag --delete myTag
5) git tag --list
6) git tag -a version3.3.3_an_annotated_tag
 "Enter annotated tag message in the pop-up"
7) Whenever u issue a tag cmd, it'll apply tag to the curernt commit.
8) git diff ver1.1  ver1.2
9) git tag -a ver_x.y <commit_hash> ,for applying tag to a particular commit.
 *Enter message in the pop-up"
10) git tag -a ver_x.y -f <new_commit_hash>, for updating the tag in case you applied tag to wrong a commit.
11) git push origin myTag (will push corresponding commit)
12) git push origin master --tags (will push any tag thats missing)
13) git push origin :myTag
 will delete remote myTag, not on local
 
 ## GitLab
 ```yaml
 stages:
  - building
  - testing

test the car:
  stage: testing
  script:
    - ls
    - test -f build/car.txt
    - cd build
    - grep "chassis" car.txt
    - grep "engine" car.txt

build the car:
  stage: building
  script:
    - mkdir build
    - cd build
    - touch car.txt
    - echo "chassis" >> car.txt
    - echo "engine" >> car.txt
  artifacts:
    paths:
      - build/
 ```
