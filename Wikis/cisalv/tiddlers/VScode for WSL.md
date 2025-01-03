<<code"sudo apt update && sudo apt upgrade -y" >>

```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
rm packages.microsoft.gpg
```

<<code 'echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
'>>

<<code "sudo apt update" >>

<<code "sudo apt install code">>

<<code "code">> 