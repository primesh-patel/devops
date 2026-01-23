## Add user-name & gmail
# yahan par Git aur GitHub do chizein hain, toh in commands ke through Git ko yeh bataya ja rha ki tumhara Hosting_Platform "yeh" hai aur "usase linked email yeh" hai. Ab GitHub account Git se link ho chuka hai.
git config --global user.name "your_github_username"

git config --global user.email "your_email@gmail.com"

## Verify configuration
# [abhi abhi jo configuration hua hai Git aur GitHub, hua ki nahi yehi confirm karne ke liye]
git config --list

git init

git add .

git commit -m "message"

git branch -M main

git remote add origin <repo_url>

git push -u origin main
