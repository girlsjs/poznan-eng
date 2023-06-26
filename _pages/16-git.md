---
title: 16. GIT
layout: post
---


GIT is a tool for controlling changes in a project. It creates a history and enables efficient collaboration among multiple programmers. To use GIT, it's worth learning a few concepts:

**terminal** - a text application used for browsing, handling, and manipulating files on your computer. How to launch it?

Windows: Start → All Programs → Accessories → Command Prompt

Mac OS: Applications → Utilities → Terminal

Linux: Applications → Accessories → Terminal

**repository** - a place where our application is located. GIT observes the history of this folder. You can have multiple such folders on your computer.

**commit** - a package of changes that is part of the history of a given repository. While working on a project, you create additional commits and manage them.

**branch** - a branch of your project. Programmers work on separate branches, e.g., on different functionalities of a website, and then merge them into one entity.

### GIT Installation:

[https://git-scm.com/downloads](https://git-scm.com/downloads)

### Basic Commands:

* **git init** - initializes a GIT repository in the specified directory.

* **git add file_name** - adds changes in the specified file to the commit.

* **git commit -m "commit_message"** - adds a description to the commit.

* **git add origin repository_address**, e.g., [https://github.com/username/my-repository.git](https://github.com/username/my-repository.git) - sets a specific remote repository address as the main repository.

* **git push origin master** - sends changes to the remote branch.

* **git checkout branch_name** - changes the active branch to the one chosen by the user.

* **git pull** - fetches changes from the remote repository.

### Task:

1. Install GIT on your computer following the instructions on this page: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
2. Create an account on [github.com](https://github.com/).
3. Create a new repository on GitHub.
4. Initialize a GIT repository in the directory containing the "A jednak się kręci" page.
5. Send the files from this directory to the remote repository on GitHub.

## GitHub Pages

GitHub also offers hosting for your pages.

### Authentication on Github

* **Currently** we need to generate a login token, we can no longer log in with a password from the terminal as before.

[See step-by-step instructions here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

### Task:

1. Create a new organization or repository on GitHub.
2. Based on the instructions provided on this page: [https://pages.github.com/](https://pages.github.com/), publish the "Wyprawy Kosmiczne" page on GitHub Pages.
3. View the new page in your browser.

**Hint:**

[Step-by-step guide on GitHub Pages](https://www.flynerd.pl/2018/02/opublikowac-strone-internetowa-github-pages-krok-kroku.html)
