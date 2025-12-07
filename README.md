# 1. Install git-flow (Assuming you've completed this step based on your OS)
# Example for Debian/Ubuntu: sudo apt-get install git-flow
# Example for macOS (using Homebrew): brew install git-flow

# 2. Create an empty repository (Do this on GitHub first)
# 3. Clone your repository (Replace <Your-GitHub-Username> with your actual username)
git clone git@github.com:<Your-GitHub-Username>/ALXprodev-advanced_git.git
cd ALXprodev-advanced_git

# 4. Create a branch develop (This uses the default Git branch 'main' or 'master' as the base)
git branch develop

# 5. Push the develop branch to the remote repository
git push -u origin develop

# 6. Initialize Git Flow within the repository using default settings
# This sets up 'main' (or 'master') as the production branch and 'develop' as the integration branch.
git flow init -d

# 7. Create an empty README.md file
touch README.md

# 8. Commit your file to staging and Push
git add README.md
git commit -m "chore: initial setup and gitflow initialization"
git push
