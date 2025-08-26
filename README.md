# Dive Into Clojure and Datomic

Welcome to this workshop on Clojure and Datomic.

# Workshop Prerequisites

For this workshop you will need a Java Runtime (JRE) or JDK, the Clojure CLI and
Datomic Transactor.

## Install Java

If you don't have Java installed, head over to https://adoptium.net/temurin and
download the latest LTS release for your platform. The site should detect your
OS and give you the correct download link on the landing page. Otherwise go to
the downloads page, and choose the JDK 21 - LTS release for your OS.

Run the installer. Test the install with:

```sh
java -version
```

## Install Clojure CLI

This step is semi-optional. Neither VS Code or IntelliJ requires it. The Clojure
CLI is nice to have, as it lets you run stuff from the shell. Whether that is
builds, REPLs, tests or something else entirely. This workshop will rarely,
leave the IDE, though, and mostly just to run the database and not the Clojure
CLI.

Follow the [Installation
instructions](https://clojure.org/guides/install_clojure) on the official
Clojure website.

Test the install with:

```sh
clojure -version
```

### Windows notes

WSL is the recommended way on the Clojure site, and they also refer to an MSI
package to install the CLI. In addition, it's possible to use the bash scripts
and Linux install process with Cygwin, or install the CLI as a Powershell module
from [the official install
scripts](https://github.com/clojure/brew-install/releases/tag/1.12.1.1550).

## IDE Setup

For a smooth developer experience with Clojure, it is recommended to have your
IDE integrate with the REPL. Most of the mainstream IDEs have plugins to do
this. Otherwise you end up with a lot of manual back and forth, copying from the
IDE and pasting things in the REPL, or restarting the Clojure process to
evaluate things again.

If you find yourself spending a lot of time getting Vim or Emacs plugins
installed and configured, you might want to use VS Code or IntelliJ if you are
comfortable with one of them. At least if you have them installed already.

### Jetbrains IntelliJ

I recommend [Cursive](https://cursive-ide.com/), which is free for
non-commercial use. You can download it from IntelliJ's plugin manager, but you
need to get a license key from the website. For the purpose of this workshop,
you can apply for a non-commercial license.

If you are considering using Clojure and Cursive commercially, the current
pricing for commercial use of the plugin, is $99 for individuals and $199 per
user for companies before any volume discounts.

### VS Code

[Calva](https://calva.io) is a plugin for VS Code to work with Clojure and
integrate with the REPL. You can search for it and install it in the Extension
pane in VS Code.

Calva should also work in Cursor and Windsurf.

### Emacs

Install the packages clojure-mode (syntax highlighting, etc.) and cider (REPL
support).

You probably want to use [clojure-lsp](https://clojure-lsp.io/installation/) as
well, which requires the package lsp-mode. It will give you some extra niceties,
like improved navigation.

On our team, we use [Magnar's
emacs-reboot](https://github.com/magnars/emacsd-reboot), which does quite a bit
of CIDER setup, but this is a complete .emacs.d. If you just want the Clojure
stuff, have a look at
[packages/setup-clojure-mode.el](https://github.com/magnars/emacsd-reboot/blob/main/packages/setup-clojure-mode.el),
[packages/setup-cider.el](https://github.com/magnars/emacsd-reboot/blob/main/packages/setup-cider.el) and
[packages/setup-paredit.el](https://github.com/magnars/emacsd-reboot/blob/main/packages/setup-paredit.el).
There are several other configs that you might find useful like the lsp setup and
clj-refactor. Some might depend on scripts in
[settings](https://github.com/magnars/emacsd-reboot/tree/main/settings), like
the clj-refactor config requires the clj-auto-refer-mode.

You might want to change keybindings set up in setup-paredit if you choose to
use it. It is a bit specific to (Norwegian) Mac keyboards.

### Vim

I am incompetent when it comes to Vim, so I will refer you to the official
[Clojure site's
references](https://clojure.org/guides/editors#_vim_highly_efficient_text_editing).

Make sure you get one of the REPL packages, whether it is Fireplace or vim-iced, or
Conjure for Neovim users. You should probably get at least one package to work
with S-expressions, the building blocks of LISPs. vim-sexp seems pretty
complete, compared to surround which is a more general bracket insertion plugin.
