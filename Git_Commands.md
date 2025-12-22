# Add user-name & gmail
git config --global user.name "your_github_username"
git config --global user.email "your_email@gmail.com"

# Very configuration
git config --list

git init
git add .
git commit -m "message"
git branch -M main
git remote add origin <repo_url>
git push -u origin main
