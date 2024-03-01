# VCD

This repository contains the VCD (Version Control with Git) documentation and related resources authored by **rln**.

For detailed information on VCD and its usage, please refer to the [Git for DevOps Repository](https://github.com/r-narayanan4/Git-for-Devops.git).

## Contents

1. [VCS](https://github.com/r-narayanan4/Git-for-Devops/tree/main/1.VCS)
2. [Git Basics](https://github.com/r-narayanan4/Git-for-Devops/tree/main/2.Git-Basics)
3. [Git Advanced](https://github.com/r-narayanan4/Git-for-Devops/tree/main/3.Git-Advanced)
4. [Differences](https://github.com/r-narayanan4/Git-for-Devops/tree/main/4.Differences)
5. [Git For CI/CD](https://github.com/r-narayanan4/Git-for-Devops/tree/main/5.Git-For-CI-CD)


## Git for DevOps

## 1. What is Git?

Git is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency. It allows multiple people to work on the same project simultaneously without interfering with each other's work.

## 2. What is VCS (Version Control System) SCM (Source Code Management) Revision Control?

Version Control System (VCS), also known as Source Code Management (SCM) or Revision Control, is a system that records changes to a file or set of files over time so that you can recall specific versions later. It helps in coordinating work among multiple developers, ensuring that changes made by one person do not conflict with changes made by others.

## 3. Difference between CVCS (Centralized Version Control System) and DVCS (Distributed Version Control System)?

- **CVCS (Centralized Version Control System):** In CVCS, there is a single central server that stores all files and the entire history of the project. Developers must connect to this central server to obtain the latest version of files or to commit changes.
- **DVCS (Distributed Version Control System):** In DVCS, every developer has their own local repository, complete with the entire project history. This allows developers to work independently without needing constant access to a central server. Changes can be shared between repositories through push and pull operations.

## 4. What are Standalone VCS Software Tools?

Standalone VCS software tools are version control systems that operate independently of any specific project management or software development platform. Examples include Git, Mercurial, and Subversion.

## 5. What are Hosting Platforms for Git Repositories?

Hosting platforms for Git repositories are online services that provide storage for Git repositories and often additional features such as issue tracking, code review, and continuous integration. Examples include GitHub, GitLab, and Bitbucket.

## 6. What is Git Branch?

A Git branch is a separate line of development within a repository. It allows you to work on different features, fixes, or experiments without affecting the main codebase. Branches are lightweight and easy to create and merge.

## 7. What is Merging?

Merging in Git is the process of combining changes from one branch (source branch) into another branch (target branch). It integrates the changes made in the source branch into the target branch, resulting in a new commit that reflects the combined history of both branches.

## 8. What is Git Conflict and How Do You Resolve It?

A Git conflict occurs when two or more branches have made changes to the same part of a file, and Git is unable to automatically merge the changes. To resolve a conflict, you need to manually edit the conflicted file to choose which changes to keep, then commit the resolved file.

## 9. What is Trunk-Based Development?

Trunk-based development is a branching model where most of the work takes place in a single trunk, usually called trunk, master, or main. The trunk receives daily merges from all developers in the team. It simplifies version control by maintaining a single source of truth and minimizes the chances of merge conflicts.

## 10. What is Git Cherry Pick?

Git cherry-pick is a command used to apply a specific commit from one branch to another. It allows you to select individual commits and copy them to another branch without merging the entire branch.

## 11. What is Git Rebase?

Git rebase is a command used to reapply commits on top of another base branch. It allows you to modify the commit history by rearranging, editing, or squashing commits. Rebase is often used to maintain a cleaner and more linear commit history.

For further differences, refer to [this link](https://github.com/r-narayanan4/Git-for-Devops/blob/main/4.Differences/differences.md).
