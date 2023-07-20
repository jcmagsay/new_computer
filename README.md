# NEW COMPUTER SETUP

## Programs

These are the programs I typically download when setting up a new computer:

1. Chrome - https://www.google.com/chrome/
2. GitHub Desktop - https://desktop.github.com/
3. VS Code - https://code.visualstudio.com/Download
4. iterm2 - https://iterm2.com/
5. ohmyzsh `sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
6. Homebrew `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
7. Node - https://nodejs.org/en/download/
8. Python - https://www.python.org/downloads/

### Mobile Development

1. Android Studio
2. Xcode

## Computer Settings

### Increase Track Pad Speed

```bash
defaults write -g com.apple.mouse.scaling -float 5.0
or 
defaults write -g com.apple.mouse.scaling  5.0
```

### Show Hidden Files

```bash
defaults write com.apple.Finder AppleShowAllFiles true

killall Finder
```

### Make sure Command Line Tools are up-to-date

```bash
xcode-select --install
```

## ITERM2

### ITERM2 / OH MY ZSH Setup

#### Install OhMyZSH

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

#### Update Theme

```bash
# Open VS Code
code .zshrc

# Go to line --> ZSH_THEME="robbyrussell"
update the theme to "agnoster"
```

```bash
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts

# Quit and restart iterm
# 1. Open Preferences
# 2. Profiles > Text > Font
# 3. I personally like Roboto Mono for Powerline with Bold setting @ 14px

# Colors
# Foreground - 27992D
# Selected text - 159D9D
# Cursor - 23FD00
# ANSI COLORS > BLUE > COL 1 - 6C71C4
```

## GitHub

### Add GitHub SSH
https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

```bash
# create
ssh-keygen -t rsa -b 4096 -C "example@email.com"

# Start the ssh-agent in the background
eval "$(ssh-agent -s)"

# Add ssh config file
touch ~/.ssh/config

## add the following to the config
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa # or the location of your rsa key

# Add your SSH private key to the ssh-agent and 
# store your passphrase in the keychain
ssh-add -K ~/.ssh/id_rsa

# copy key to Github account
pbcopy < ~/.ssh/id_rsa.pub
```

## VS Code Setup

### Extensions

1. Atom Keymap
2. Code Spell Checker
3. ESLint
4. GitLens
5. Highlight Line
6. JavaScript and TypeScript Nightly
7. markdown lint
8. Python
9. TODO Highlight
10. TypeScript Hero

### Settings/Preferences

1. Editor: Tab Size --> 2
2. Files: Insert Final Newline
3. Editor: Render Whitespace --> ALL
4. Files: Trim Trailing Whitespace
5. Files: Insert Final Newlines
