# Setting up zsh, oh-my-zsh, colorls on Mac.

--------------------------------------------------------------------------------------------------------------
## 1. Install brew.

#### Run this command on your terminal:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Add brew to your zsh PATH:
```
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/ali/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/ali/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

--------------------------------------------------------------------------------------------------------------
## 2. Install zsh.

#### Install zsh using homebrew:
```
brew install zsh
```

#### Make zsh your default shell:
```
chsh -s /bin/zsh
```

#### Restart your terminal:
```
source ~/.zshrc
```

#### Verify your default shell:
```
echo $SHELL
```

--------------------------------------------------------------------------------------------------------------
## 03. Install Oh My ZSH.

#### Copy and below command to your terminal and press enter to install Oh-My-ZSH:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### Install PowerLevel10K theme:
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

--------------------------------------------------------------------------------------------------------------
## 04. Download FuraMono Nerd Font from above github repository and install it.

#### Go to terminal Preferences and change terminal font to FuraMono Nerd Font Regular.


--------------------------------------------------------------------------------------------------------------
## 05. Install zsh-autosugestions and zsh-syntax-highlighting.
```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

#### Now edit your ~/.zshrc file to use the PowerLeve10K theme, Awesome Patched font, Autocorrection, Autosuggestion and Syntax highlighting.
```
nano ~/.zshrc
```

#### Find the ZSH_THME and replace it with:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

#### Also add this line below to use Nerd Patched fonts
```
POWERLEVEL9K_MODE="nerdfont-complete"
```

#### If you want to enable auto correction then find uncomment the line by removing # from

#ENABLE_CORRECTION="true"
//to this
```
ENABLE_CORRECTION="true"
```

#### Now we will add plugins so scroll down a little till you find
```
plugins=(git)
```

#### And now add the plugins which we downloaded, like this
```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

#### Configure Oh-My-ZSH:
```
p10k configure
```

Resource: https://medium.com/@shivam1/make-your-terminal-beautiful-and-fast-with-zsh-shell-and-powerlevel10k-6484461c6efb


--------------------------------------------------------------------------------------------------------------
## 06. Install colorls.

#### First install dependencies such as Ruby:
```
brew install ruby
```

#### Add Ruby to your zsh PATH:
```
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
```

#### Now install clolorls software:
```
sudo gem install colorls
```

#### Finally add these lines to the end of your .zshrc file:
```
alias ll='colorls -lA --sd --group-directories-first'
alias ls='colorls --group-directories-first'
```

#### General Aliases
```
alias cls='clear'
alias py='python3'
alias zr='source ~/.zshrc'
```

#### Global Aliases
```
alias -g L='| less'
alias -g J='| jq'
```

#### Suffix Aliases
```
alias -s {py,txt,go,js}='code'
```

#### Restart your terminal:
```
source ~/.zshrc
```

## We have completed oh-my-zsh setup. Enjoy your experience! =)
