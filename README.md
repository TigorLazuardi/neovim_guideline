# (Neo)VIM GUIDE BY ME

# Disclaimer:

I don't use (Neo)Vim at all at Windows environment and I don't own any mac machine. I only use windows for gaming, and I uses vim on Linux. so I cannot give any answer if there's a problem of vim on windows. Mac is close enough to Linux that I can be confident in my answer on the problem, but the actual implementation of solution probably needs to be googled if my advise doesn't work.

# What is Vim? And Why Should I Use Vim?

There are dozens of article of what is vim and why should vim.

[What is Vim and Why Use Vim? (Medium)](https://medium.com/@fay_jai/what-is-vim-and-why-use-vim-54c67ce3c18e)

[Vim (Wikipedia)](https://en.wikipedia.org/wiki/Vim_(text_editor))

you can google the rest for more better reasons.

**This is why I use vim:**

Vim is a text editor which emphasized efficiency, most notably by reducing the usage of mouse.

You don't ever use mouse when using vim unless you specifically configured it to do so.

When you write something, it's impossible to have no mistakes at all or have no need to rephrase a sentence or have a change of mind about the paragraph. And thus you have to correct those mistakes. When you move to the place you want to change, most likely you use arrow keys or mouse if its rather far. That reaching for mouse is slow and can be tiring having moving your hand away from keyboard if done repeatedly. Then how about you have to be precise when blocking text to copy or delete? That's another few seconds wasted.

Have you ever thought about how you wish you can delete everything between two double quotes without the precise use of mouse?  How about deleting everything to to the closing parenthesis or opening parenthesis? How about delete the word without pressing delete repeatedly? or change the word under the cursor with two keypress? etc, etc?

How about instead of deleting, you can do the same with copying? How about copy the text between these two quotes, or copy the the text with the quotes included without having to select the block of text first?

Or how about with three keypress you can select block everything between curly brackets? To end of paragraphs? To end of line? To end of sentence? or to start?

*Vim can do all of those. It can be daunting at first, but once you catch the pattern of how vim doing things, suddenly vim is **very-very good and surprisingly simple to implement**.*

**TL;DR: Vim is a text editor which emphasized efficiency, most notably by reducing the usage of mouse.**

If this interests you, read more. Otherwise, well, bye. Thanks for reading!

# VIM INSTALLATION

### Debian Based Distro (Debian, Ubuntu, Pop_OS!, Elementary, Mint, etc)

**Note:** `Ubuntu` only comes with minimal vim, so you do indeed need to do this step if you haven't done it before.

```bash
sudo apt install vim
```

### Arch Based Distro (Arch Linux, Manjaro)

```bash
sudo pacman -S vim
```

### MacOs

```bash
brew install vim
```

### Windows

Do yourself a favor and install [Chocolatey](https://chocolatey.org/). It skips the bullshit of clicking next when installing stuff and doesn't give you malware for doing so. You can install stuff like 7zip via Chocolatey too.

After installing `Chocolatey` do this at powershell:

```powershell
choco install vim
```

**Note: I won't give support on (neo)vim for windows.**

[You may want to read to installation documentation as well](https://chocolatey.org/packages/vim).

### Other Distros

Please google the rest yourself for your own distro.

# Learning VIM

In terminal:

```bash
vimtutor
```

[Vimtutor](http://www2.geog.ucl.ac.uk/~plewis/teaching/unix/vimtutor) gives you everything you need for basic use and doesn't bog you with technical jargons you most likely not know as a vim beginner. It's a 30 minute to 2 hour tutorial depending on your pacing.

`vimtutor` is available after installing vim.

**When using `vimtutor`, do not use plugins or custom settings.  Just use the default clean after install vim. This will help you learn the intended keypresses and what they do**. 

*Tip: Do not afraid to use `vimtutor` again in the next day if you forgot the commands. You most likely forgot about it. Rome wasn't built in a day, and so does learning vim.*

*Tip-2: Not all commands will stick to you from tutorial only. And redoing the tutorial will be boring. Learning vim is best when done in real situation like writing an article, a blog, do some coding, or writing a story. Though before you continue, please complete `vimtutor` at least once in vanilla vim. I will not explain what is normal mode, insert mode, or anything basic in next section.*

# `Tips` Motion Trick in VIM

In normal mode, you can use motions to supercharge your writing.

Move your cursor to some text between double quotes, press `yi"`, and suddenly you just yanked all the text between those double quotes. What you just did is short for **y**ank**i**nside**[key]**. The key can be anything. `yi(` For between parenthesis, `yi{` For between brackets. To copy with the brackets, or the quotes along, use `ya"`.

For deleting, just change `y` to `d`.

Ex: `di"` Will delete all text between double quotes. To change, use `c`

You can also do this to visual select. `va"` To select text and the quote.

# Installing NeoVim

Why install neovim after installing vim? Because I use neovim and the rest of this guide uses Neovim.

For comparisons, open this [site](https://www.slant.co/versus/42/62/~vim_vs_neovim) and scroll somewhere midway. Do read the panes on the right,  it compares vim with neovim. The left pane compares vim (in general) vs the world.

### Debian Based Distro (Debian, Ubuntu, Pop_OS!, Elementary, Mint, etc)

```bash
sudo apt install neovim
```

### Arch Based Distro (Arch Linux, Manjaro)

```bash
sudo pacman -S neovim # Either this one or the one under this.
yay -S neovim-nightly --noconfirm # This is the nightly built. Some features are only available on this version.
```

### MacOs

```bash
brew install neovim
```

### Windows

```powershell
choco install neovim
```

**NOTE: my support for windows ends here. All config is the same in all os, but how to edit those config or access those resources will need different approach, some config may need to be edited to work in Windows environment. Please google them yourself.**

### Other Distros

Please google the rest yourself for your own distro.

# Configurations

I will not explain what the config in detail, or how to edit the config, but I will link the documentation on how to edit such things.

Neovim config can be found on

```bash
$HOME/.config/nvim/init.vim
```

The double quotes in vim config is a comment

```bash
set nocompatible "Remove compability with older versions.
set ignorecase "When searching, make the search case insensitive
set hlsearch "When searching, the searched text is highlighted
set tabstop=2 "2 spaces when pressing tab.
set softtabstop=2
set expandtab
set shiftwidth=2 "If there's a matching bracket, vim will put it properly"
set shiftround "An extension of above"
set autoindent "When you press enter on a tabbed line, Next line is idented properly"
set smartindent "Indent enhancement"
set smarttab "tab enhancement"
set number "Shows line number on the left"
set textwidth=100 "The text width before vim wraps the line"
set clipboard=unnamedplus "Make vim able to copy and paste from outside vim"
set encoding=utf8 "Enforces utf-8"
set guifont=DejavuSansMono\ Nerd\ Font\ Mono "You may want to delete this if you don't have the font"
set cursorline "Highlight where your current line is"
set termguicolors "256 Colors GUI"
set timeoutlen=2000 "Set delay time between input commands before trigger"
set updatetime=200 "Time before vim is refreshed. Default 4000, the stronger your pc, the lower you may set it."
set display+=lastline "Never shortens messages"
set linebreak "Prevent vim from wrap in the middle of a word"
set scrolloff=5 "Make sure there's at least few lines visible between cursor and edge of window. Setting to 999 will make the cursor always on middle of screen"
set autoread "Auto reload file if there's outside edit"
set backspace=indent,eol,start "you may backspace over indentation, endofline, startofline"
set dir=$HOME/.cache/vim "Set dir cache"
set backupdir=$HOME/.cache/vim "set backup dir cache"
set formatoptions+=j "When editing a comment, and in insert mode you add new line while inside said comment, there's a leading comment added"
set noswapfile "Disable swap and backup file. Makes my life easier to be honest with all those backup prompt annoyances, but make sure to save frequently if you do use this
set undodir=$HOME/vim/undodir "Make undo persistent between sessions"
set splitbelow "Horizontal split appears on bottom"
set splitright "Vertical split appears on right

" Enable syntax highlighting
syntax on 

" Alt+J and Alt+K to swap lines
nnoremap <A-j> :m .+1<CR>==
nnoremap <A-k> :m .-2<CR>==
inoremap <A-k> :m .-2<CR>==gi
inoremap <A-j> :m .+1<CR>==gi
vnoremap <A-j> :m '>+1<CR>gv=gv
vnoremap <A-k> :m '<-2<CR>gv=gv

" Moving between vim splits without pressing Ctrl+w first. 
nnoremap <C-J> <C-W><C-J>
nnoremap <C-K> <C-W><C-K>
nnoremap <C-L> <C-W><C-L>
nnoremap <C-H> <C-W><C-H>

" Pressing enter in normal mode enters new line
nnoremap <CR> o<Esc>

" On command mode typing w!! will allow saving of files as sudo when I forgot to start vim using sudo. Not working in windows obviously
cmap w!! w! !sudo tee > /dev/null %

" Press F12 to reload config. Windows users may need to edit forward slash to backslash, but I dunno about that.
nmap <silent><F12> :source $HOME/.config/nvim/init.vim<CR>:echo "Config reloaded"<CR>
```

### Documentation

[Wtf is nmap, nnoremap, blablamap?](https://vim.fandom.com/wiki/Mapping_keys_in_Vim_-_Tutorial_(Part_1))

Do read above link for to map shortcuts to keyboard.

# Leader Key

Leader key is a key that is not hard-coded. If leader key is changed, all shortcuts that uses the leader key will use the new leader key.

**By default**, Leader key is `\`

So when there's a config that looks like this:

```vimscript
nnoremap <leader><f> :echo "Leader f is pressed"<CR>
```

By pressing `\f` in normal mode, nvim will enter the echo message.

I personally like to use `<space>` key instead of `\` for easy reach with both hands.

Enter this to `init.vim`

```bash
" Change leader key to space key
" Remove default space behavior in normal mode
nnoremap <Space> <nop>
" Set mapleader to space
let mapleader = " "
```

Now I press `<space>f` to enter the echo message.