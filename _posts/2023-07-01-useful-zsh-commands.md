Brew Installation  
[https://osxdaily.com/2023/04/19/fix-brew-command-not-found-on-mac-with-zsh/](https://osxdaily.com/2023/04/19/fix-brew-command-not-found-on-mac-with-zsh/)    
Adding `brew` to the path in MAC  
```
echo "export PATH=/opt/homebrew/bin:$PATH" >> ~/.zshrc
```  
Downloading Brew  
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```  
Brew PATH setup  
```
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/chaitanyavardhan/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```  


Apache Installation:

[https://tecadmin.net/install-apache-macos-homebrew/](https://tecadmin.net/install-apache-macos-homebrew/)