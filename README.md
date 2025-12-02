# Dotfiles

Dotfiles to use in `Termux` & `MacOS`.

## 📦 Installation

>[!IMPORTANT]
> Make sure to **backup** your existing config before starting.

### 🧩 Termux

>[!WARNING]
> In `Termux`, this will overwrite the `~/.termux` directory.

1. Upgrade your packages.

```sh
pkg update && pkg upgrade -y
```

>[!NOTE]
> Some built-in packages would ask if you would lime to use the `package manager`'s version instead of the default ones.
> For most cases, you are fine to use **Y**.

2. Install necessary packages,
    - [git](https://git-scm.com/), Version control.
    - [gh](https://cli.github.com/), GitHub CLI.

```sh
pkg install git gh
```

You may also install [lazygit](https://github.com/jesseduffield/lazygit) to use a TUI for git.

```sh
pkg install lazygit -y
```

3. Install optional packages,
    - [eza](https://github.com/eza-community/eza), Fancy **ls**.
    - [fish](https://fishshell.com/), Fancy shell.
    - [zoxide](https://github.com/ajeetdsouza/zoxide), Fancy **cd**.

```sh
pkg install fish zoxide eza
```

4. Install packages for installing `tree-sitter` parsers,
    <!-- - [rust](), Rust. -->
    - [nodejs-lts](https://nodejs.org/), NodeJS(stable).
    - [clang](https://clang.llvm.org/), C compiler.

```sh
pkg install nodejs-lts clang
```

5. Clone the repository as a `bare git repository`,

```sh
git clone --bare git@github.com:OXY2DEV/.dotfiles.git ~/.dotfiles
```

>[!NOTE]
> This will store the repository data(the stuff usually in `.git/`) in `.dotfiles`.

You will most likely see no change.

6. Disable `showUntrackedFiles` to hide unwanted files in the untracked file list.

```sh
git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME config status.showUntrackedFiles no
```

7. Run `git reset` on specific directories.

    1. Via `lazygit`.

