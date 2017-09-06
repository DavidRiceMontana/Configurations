# vim-config
Configurations for vim to share amongst machines

### Additional Dependencies
1. vim installed with Python3 support: vim-nox
2. Vundle extension manager to make installing the other plugins easy
    - git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
    - touch ~/.vimrc
    - (make sure to then run :PluginInstall in Vim)
3. Lokaltog/powerline plugin
    - Needs python3 pip
        - sudo apt-get install python3-pip
    - Then install powerline (Don't forget :PluginInstall afterwords)
        - pip3 install --user powerline-status
        

### Installed Plugin Sparknotes (Description and common commands)
###### VundleVim/Vundle - Pip for Vim. Makes installing packages easy
- :PluginInstall
- :PluginList
###### tpope/vim-fugitive - Git wrapper for Vim
- :Git (any normal Git command that comes after the word *git*)
- The % symbol means this file
    - :Git commit %
###### scrooloose/nerdtree - File tree and directory navigation
###### jistr/vim-nerdtree-tabs - Nerdtree stays open and the same across tabs
###### ctrlpvim//ctrlp - Search for files
- Enter *ctrl+p* to enter file search mode
- Refresh cache with <F5>
- search parent directories with *..*
###### nvie/vim-flake8 - python PEP8 style enforcer
- Press <F7> to run flake8 on the currently open file
###### vim-scripts/Pydiction - Tab complete Python code
- Press <tab> while typing a keyword, built-in, standard library, or third-party modules
