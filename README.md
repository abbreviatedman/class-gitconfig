# Class Gitconfig

A starter configuration file to alleviate some initial git issues.

## Installation

### Happy Path

1. Clone or download this repo.
2. Move the file `.gitconfig` into your home directory.

### If You Have A `.Gitconfig` File Already

Unless you know enough Git to be attached to the settings you have already, replace it with this one.

## Final Setup

There are two settings that should be different for each user: their name and email. Contributors to codebases need to know who you are, and Git WILL complain if you don't have your name and email as part of your setup.

The command-line way to configure these settings is usually the recommended method, though you _could_ edit your `.gitconfig` file directly. We'll use the command line.

Enter the two commands below into your terminal, from any directory, hitting return after each line.

For `[your name goes here]`, you should replace the words and the brackets with your name, and the same for the email line. For example, the last part of the first line would be, for _me_: `user.name "Colin Jaffe"`.

``` sh
git config --global user.name "[your name goes here]"
git config --global user.email "[your email goes here]"
```

When you're done, open your `.gitconfig` file, and it should look something like this:

```sh
[core]
	ignorecase = false # prevents a case mismatch between your local filesystem and Git
	editor = $(which code) -w # so that `git commit` opens VS Code instead of Vim
[init]
	defaultBranch = main # the current standard branch name
[pull]
	rebase = false # which method to use for `git pull`
[credential]
	helper = osxkeychain # cache your personal access token in the macOS keychain
[user]
	name = Colin Jaffe
	email = balloonasaurus@gmail.com
```

As you can see, those `git config --global` lines add `name` and `email` keys under the `user` section, with values set to what you entered in quotes. You could just as easily have edited the file itself.

## Final Words

There may be other Git config settings you set over your career, but this will get you off to a good start. Additionally, you have now practiced configuring Git in two different ways, which should prepare you more for configuring it in the future.

Happy hacking!
