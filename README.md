# vim-config
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
    - `pip3 install -U pip setuptools`
3. Lokaltog/powerline plugin
    - `pip3 install --user powerline-status`
4. python-rope/ropevim 
    - Needs the *Rope* library installed first:
        - `sudo pip3 install Rope`
5. nvie/vim-flake8
    - Needs flake8 instealled through python
        - `sudo pip3 install flake8`
       
### Installed Plugin Sparknotes (Description and common commands)
###### VundleVim/Vundle - Pip for Vim. Makes installing packages easy
- :PluginInstall
- :PluginList
###### tpope/vim-fugitive - Git wrapper for Vim
- :Git (any normal Git command that comes after the word *git*)
- The <%> symbol means this file
    - :Git commit %
###### scrooloose/nerdtree - File tree and directory navigation
###### jistr/vim-nerdtree-tabs - Nerdtree stays open and the same across tabs
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
- Needs various development tools:
    - `sudo apt-get install build-essential cmake`
    - `sudo apt-get install python-dev python3-dev`
    - `cd ~/.vim/bundle/YouCompleteMe` `./install.py --clang-completer`
    - (see YouCompleteMe on GitHub for support for more languages)
###### python-rope/ropevim - Python refactoring
- Needs the *Rope* library installed first:
    - `sudo apt install python3-pip`
    - `pip3 install -U pip setuptools`
    - `sudo pip3 install Rope`
###### tmhedberg/SimpylFold - More accurate Python code folding
###### Lokaltog/powerline - Status bar that displays things like the current virtualenv, git branch, files being edited, and much more.
###### Screen (not a vim plugin) - Split or window multiple shells using tmux
- `screen -S <name>` - New screen session with provided session name
- `screen -ls` - List running sessions and names
- `screen -x` - Attach to running session
- `screen -r <name>` - Attach to session name
- `screen -dRR` - Smart attach (Attaches to a screen session. If the session is attached elsewhere, detaches that other display. If no session exists, creates one. If multiple sessions exist, uses the first one.)
- `^a S`\`^a V` - Split display horizontally\vertically
    - Then enter `^a c` to start a new screen instance with shell open
- `^a tab` - Jump to next display region
- `^a X` - Remove current region 
- `^a Q` - Remove all regions but currnent
