# Git "Hello world"

![Git version history: commits in a chain, a branch and a merge](img/chapters/git.svg)

In this exercise, you learn the basics of Git version control. Before starting, [install Git on your computer (git-scm.com)](https://git-scm.com/) and [configure it (GitHub)](https://docs.github.com/en/get-started/quickstart/set-up-git). You also need a [GitHub](https://github.com/) account, which you can create at https://github.com/.

🔐 *If you already use GitHub for work, it may be wise to create a separate account for your studies. You do not need to give your own name when registering. You can use your school email address and hide it from other users by following [GitHub's instructions](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address#setting-your-commit-email-address-on-github).*

⛔ *If you do not want to use GitHub on this course under any circumstances, agree on an alternative git service with your teacher.*

**Completing this chapter.** This chapter is done on your own computer and on GitHub. Nothing is submitted to the course system (https://jtjuslin.kapsi.fi/java), and the chapter gives no points. The other chapters of the course are submitted to the course system, and their exercise templates are in the same GitHub organization: https://github.com/o2-syksy2026. In them, you get full points when the tests also pass for code fetched from your **public** GitHub repository. The repository may remain public. The instructions are in the "Submitting and points" section of each chapter.


## Git command-line tool

The instructions focus on Git's command-line tool, and we assume that [basic command-line usage](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line), such as opening the command line and moving between directories, is familiar. You can also solve this and the following exercises with a graphical tool, such as VS Code or GitHub Desktop, but you then need to find the corresponding functions on your own.

* [Command line crash course (developer.mozilla.org)](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
* [Using Git source control in VS Code (code.visualstudio.com)](https://code.visualstudio.com/docs/sourcecontrol/overview)
* [GitHub Desktop (desktop.github.com)](https://desktop.github.com/)


## Git basics

There are countless Git tutorials with different approaches: some create a new repository, some clone an existing one, and some use branches. In this exercise, you only need the commands `clone`, `add`, `commit` and `push`, so you can skip advanced topics, such as branches, for now. We recommend the following sources:

* [What is version control? (Atlassian)](https://www.atlassian.com/git/tutorials/what-is-version-control). See also the [video](https://youtu.be/xQujH0ElTUg).
* [What is Git (Atlassian)](https://www.atlassian.com/git/tutorials/what-is-git)
* [Install Git (Atlassian)](https://www.atlassian.com/git/tutorials/install-git)
* [Git add (Atlassian)](https://www.atlassian.com/git/tutorials/saving-changes)
* [Git Cheat Sheet, pdf (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)


## Exercise

In this exercise, you fork this repository, clone it to your computer, make a small change and push the change back to GitHub.

### Forking and cloning the repository

First fork this repository into your own GitHub repository with GitHub's **Fork** button, and only then clone your fork to your computer:

```sh
git clone https://github.com/<your-github-username>/1-git-hello-world.git
```

Open the cloned directory in your code editor. This repository does not contain a Java project but a single text file, so it looks different in your editor than "regular" projects.

💡 *Git clones the repository into a directory named after the repository by default. The following commands are run inside that directory, so [switch to it on the command line](https://en.wikipedia.org/wiki/Cd_(command)).*

### Editing the file

Open the file [hello.txt](./hello.txt) in your code editor, add the text `hello world` and save the file. Run `git status` and look at its output. Is `hello.txt` shown in the output? What does it say about it?

### Adding the change

A change is added to version control in two steps, which are described in [Git add (Atlassian)](https://www.atlassian.com/git/tutorials/saving-changes). `git status` tells that the file has changed and shows a hint of the command that adds the change:

```sh
git status
git *** hello.txt    # replace *** with the command given by status
```

One commit can contain several files, but this one file is enough this time.

### Creating a commit

`git status` now shows which files are ready to be committed:

```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   hello.txt
```

Create a new commit that contains the change:

```sh
git commit -m "Added hello world to the file"   # replace the message with your own text
```

💡 *`-m` means the commit **m**essage that identifies the change in the version history later.*

### Pushing the commit to the remote repository

Run `git status` again. Git tells that your local copy is one commit ahead of the remote repository:

```
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git ****" to publish your local commits)
```

Publish your changes to the remote repository as Git suggests:

```sh
git ****    # replace **** with the command you got from the previous command
```

Finally, check on GitHub that `hello.txt` has been updated in your fork.


## .gitignore and .gitattributes

The template also contains "hidden" files whose names start with a dot. If you do not see them in your editor, you may need to change the editor's settings. The [.gitignore](./.gitignore) file defines which files are [left out of version control](https://git-scm.com/docs/gitignore), and the [.gitattributes](./.gitattributes) file defines [consistent line endings](https://docs.github.com/en/get-started/getting-started-with-git/configuring-git-to-handle-line-endings) for text files. You can edit these files as needed.


## License and authors

This exercise was developed by Teemu Havulinna and Jukka Juslin, and it is licensed under the [Creative Commons BY-NC-SA license](https://creativecommons.org/licenses/by-nc-sa/4.0/). ChatGPT 3.5 and GitHub Copilot were used in creating the assignment, the source code and the tests.
