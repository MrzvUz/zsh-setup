# Setting up zsh, oh-my-zsh, colorls on Mac.

### 1. Install brew.

Run this command on your terminal:

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


Add brew to your zsh PATH:

echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/dev/.zprofile                       
    eval "$(/opt/homebrew/bin/brew shellenv)"


### 2. Install zsh.


Install zsh using homebrew:

brew install zsh


Make zsh your default shell:

chsh -s /bin/zsh


Restart your terminal:

source ~/.zshrc


Verify your default shell:

echo $SHELL


### 03. Install Oh My ZSH.


Copy and below command to your terminal and press enter to install Oh-My-ZSH:

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"


Install PowerLevel10K theme:

git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k


### 04. Download FuraMono Nerd Font from above github repository and install it.

Go to terminal Preferences and change terminal font to FuraMono Nerd Font Regular.


### 05. Install zsh-autosugestions and zsh-syntax-highlighting.

git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting


Now edit your ~/.zshrc file to use the PowerLeve10K theme, Awesome Patched font, Autocorrection, Autosuggestion and Syntax highlighting.

nano ~/.zshrc


Find the ZSH_THME and replace it with:

ZSH_THEME="powerlevel10k/powerlevel10k"


Also add this line below to use Nerd Patched fonts

POWERLEVEL9K_MODE="nerdfont-complete"


If you want to enable auto correction then find uncomment the line by removing # from

#ENABLE_CORRECTION="true"
//to this
ENABLE_CORRECTION="true"


Now we will add plugins so scroll down a little till you find

plugins=(git)


And now add the plugins which we downloaded, like this

plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

