
# Cheat sheet #4

*To make quickly available a few notes about repetitive tasks, that I easily forget :)*

Quick code snippets and links
  
 ### Install Matrix Element
 
```
sudo apt install -y wget apt-transport-https
‍
sudo wget -O /usr/share/keyrings/element-io-archive-keyring.gpg https://packages.element.io/debian/element-io-archive-keyring.gpg
‍
echo "deb [signed-by=/usr/share/keyrings/element-io-archive-keyring.gpg] https://packages.element.io/debian/ default main" | sudo tee /etc/apt/sources.list.d/element-io.list

sudo apt update

sudo apt install element-desktop
```


official [element website](https://element.io/download#linux)
