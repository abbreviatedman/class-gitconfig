# Class Gitconfig

A starter configuration file to alleviate some initial Git issues.

### Installation

##### If you don't already have a git config file

If you don't have Git set up yet, or you're not attached to the configuration file you have, then follow these steps to get a basic config set up:

1. Clone or download this repo to anywhere on your machine using: git clone https://github.com/abbreviatedman/class-gitconfig
2. Navigate into the repo's directory using: cd class-gitconfig
2. Copy the file `.gitconfig` into your home directory using: cp .gitconfig

##### If You Have A Git Config File Already

Unless you know enough Git to be attached to the `.gitconfig` file you have already, simply follow the steps in the previous section to replace it with this repo's version. Any configuration you have should be easy to replicate, and the settings in this repo's `.gitconfig` are important to have.

If you _do_ know plenty about Git and _are_ attached to your current `.gitconfig` file, then just copy over the contents of this repo's `.gitconfig` to the bottom of the `.gitconfig` in your home directory. Then remove any duplicates—preferring the ones from this repo.

If this is the first time you're setting Git up and you don't know what we're talking about here, then _definitely_ follow the steps in the previous section to simply replace any `.gitconfig` file you have with the one from this repository.

### After You've Installed: Configuration

Once you have the settings from the `.gitconfig` in this repository in the `.gitconfig` file in your home directory, it's time to add a little more personal configuration.

There are two settings that by their nature are different for each user: their name and email. Contributors to codebases need to know who you are, and Git WILL complain if you don't have your name and email as part of your setup.

The command-line way to configure these settings is usually the recommended method, though you _could_ edit your `.gitconfig` file directly. We'll use the command line, but first, let's view the file to see what it looks like.

##### Viewing The File

To view the file, enter the command `cat ~/.gitconfig` in your terminal. This will print directly to the terminal the contents of the file you just copied into your home directory. It should look exactly like this:

```git-config
[core]
	ignorecase = false # prevents a case mismatch between your local filesystem and Git
	editor = $(which code) -w # so that `git commit` opens VS Code instead of Vim
[init]
	defaultBranch = main # the current standard branch name
[pull]
	rebase = false # which method to use for `git pull`
```

Alternately, you're welcome to open it with your own editor—perhaps with VS Code using `code ~/.gitconfig`.

We'll be editing the file indirectly via the terminal, but you'll see the change happen in this file. We'll check the file again later to see this happen.

##### Changing The File Using The Terminal

Enter the two commands below into your terminal, from any directory, hitting return after each line.

For `[your name goes here]`, you should replace the words _and_ the brackets with your name, and the same for the email line. For example, the last part of the first line would be, for _me_: `user.name "Colin Jaffe"`.

```
git config --global user.name "[your name goes here]"
git config --global user.email "[your email goes here]"
```

When you're done, enter the command `cat ~/.gitconfig` again to view how the file has changed. (If you opened the file in a text editor, switch back and it will likely simply have changed while you weren't looking.) It should look exactly like this, except with _your_ name and email address.

```git-config
[core]
	ignorecase = false # prevents a case mismatch between your local filesystem and Git
	editor = $(which code) -w # so that `git commit` opens VS Code instead of Vim
[init]
	defaultBranch = main # the current standard branch name
[pull]
	rebase = false # which method to use for `git pull`
[user]
	name = Colin Jaffe
	email = balloonasaurus@gmail.com
```

As you can see, those `git config --global` lines you entered earlier added `name` and `email` sections under the `user` section in this file, with values set to what you entered in quotes in the terminal. That's what the `git config` terminal command _does_: edit this configuration file.

In the future, if you need to change a global Git setting, you can either edit this file directly, or use the `git config --global` commands in your terminal as we just did.

### Final Words

There will likely be other Git config settings you change over your career, but this will get you off to a good start. Additionally, you have now seen that you can configure Git in two different ways—through changing the file directly and through the terminal command—and this should prepare you more for configuring it in the future.

Happy hacking!
