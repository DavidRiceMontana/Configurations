# Linux
## Vim
Configurations for vim to share amongst machines
### Additional Dependencies
1. vim installed with Python3 support: vim-nox
2. Vundle extension manager to make installing the other plugins easy
    - `git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim`
    - `touch ~/.vimrc`
    - (make sure to then run :PluginInstall in Vim)
3. Screen (Not essential, but I list shortcuts for it below and like using it. Note that Screen is not a vim plugin)
    - `sudo apt install screen`
4. Python3 basics needed
    - `sudo apt install python3-pip`
    - `sudo pip3 install -U pip setuptools`
5. YouCompleteMe dependencies:
    - `sudo apt-get install build-essential cmake`
    - `sudo apt-get install python-dev python3-dev`
    - `cd ~/.vim/bundle/YouCompleteMe`
        - `./install.py --clang-completer`
    - (look up the github for Valloric/YouCompleteMe for support for additional languages)
6. Lokaltog/powerline plugin
    - `pip3 install --user powerline-status`
7. python-rope/ropevim 
    - Needs the *Rope* library installed first:
        - `sudo pip3 install Rope`
8. nvie/vim-flake8
    - Needs flake8 instealled through python
        - `sudo pip3 install flake8`
9. google/yapf
    - `sudo pip3 install yapf`
10. majutsushi/tagbar
    - Needs Exuberant Ctags installed alongside it:
        - `sudo apt install exuberant-ctags`
    
### Installed Plugin Sparknotes (Description and common commands)
###### VundleVim/Vundle - Pip for Vim. Makes installing packages easy
- :PluginInstall
- :PluginList
###### tpope/vim-fugitive - Git wrapper for Vim
- :Git (any normal Git command that comes after the word *git*)
- The <%> symbol means this file
    - :Git commit %
###### scrooloose/nerdtree - File tree and directory navigation
###### ctrlpvim//ctrlp - Search for files
- Enter <ctrl+p> to enter file search mode
- Refresh cache with <F5>
- search parent directories with <..>
###### nvie/vim-flake8 - python PEP8 style enforcer
- Press <F7> to run flake8 on the currently open file
- <Enter> - go to next error
###### vim-scripts/Pydiction - Tab complete Python code
- Press <tab> while typing a keyword, built-in, standard library, or third-party modules
###### vim-scripts/indentpython - Indent tabs automatically according to PEP8 standards
###### scrooloose/syntastic - Real time syntax checking for all languages
- Requires the language-specific syntax checker also be installed (e.g. vim-flake8 for python checking)
- Put cursor on line with a syntax error to see the error message
- This is a complicated plugin. Read through *:help syntastic*
###### python-mode/python-mode - Static analysis, syntax highlighting, refactoring, folding, completion, documentation, and more: all you need to develop python applications in Vim.
- No need to install pylint, rope or any other Python Libraries on your system with this plugin
- Vim motion for python objects (C means class, M means method or function):
    - `[[` - Jump to previous class or function (normal, visual, operator modes)
    - `[[` - Jump to next class or function (normal, visual, operator modes)
    - `[M` - Jump to previous class or method
    - `]M` - Jump to next class or method
    - `aC` - Select a class. (Ex: vaC, daC, yaC, ciC)
    - `iC` - Select inner class. (Ex: viC, diC, yiC, ciC)
    - `aM` - Select a function or method. (Ex: vaM, daM, yaM, caM)
    - `iM` - Select inner function or method. (Ex: viM, diM, yiM, ciM)
###### Valloric/YouCompleteMe - Python autocomplete
- (TODO: there are commands and shortcuts for jumping to definitions/declarations and quick refactoring. Read documentation and make shortcuts for these eventually)
###### ~~python-rope/ropevim - Python refactoring~~
###### tmhedberg/SimpylFold - More accurate Python code folding
- `spacebar` to fold code based on indents  
- `zR` - Unfold all folds
- `zM` - Fold all folds
- `zc` - close a fold
- `zo` - open a fold
###### Lokaltog/powerline - Status bar that displays things like the current virtualenv, git branch, files being edited, and much more.
###### google/yapf - Auto-formatting for python to fit to PEP8 standards (not a vim plugin)
- Run from outside of vim with `yapf -i <filename.py>`
##### nerdcommenter - Effective handling on commenting out code
##### majutsushi/tagbar - Display tags in a window, ordered by scope
- `<F8>` - Open tagbar
###### Screen (not a vim plugin) - Split or window multiple shells using tmux
- `^a c` - create a new shell
- `^a [0-9]` - go to window [0-9]
- `^a S [optional file path to open]` - Make new screen window split horizontally 
- `^a V (or |) [optional file path to open]` - Make new screen window split vertically 
- `^a^l` - redraw window (good for fixing bugs?)
- `^a X` - remove current screen window
- `^a k` - kill the current shell
- `^a d` - Detach, leave everything as is, but return to terminal
- `^a D D` - Detach and logout (quick exit)
- `screen -r` - Return to detached screen window
- `screen -dRR` - Attach non screen state to current screen session
- (screen is a large and useful application with a lot more commands. read up on to how to use it)

# Windows
### Remove Bloatware
This is a PowershellScript that fully removes unwanted programs.  Before running, ensure:
- Powershell is run in administrator mode
- Powershell is allowed to run unsigned scripts. Set with `set-executionpolicy remotesigned`

To run,
- Navigate to the directory where the script lives
- Execute the script with `.\remove_bloatware.ps1 (enter)`
