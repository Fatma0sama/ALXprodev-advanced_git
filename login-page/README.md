# Ensure you are on the develop branch before starting the feature
git checkout develop

# 1. Create a new feature branch feature/implement-login from the develop branch
# The git flow feature start command creates the branch and switches to it.
git flow feature start implement-login

# 2. In the feature/implement-login, create a new directory and README.md file
mkdir login-page
echo "Login Feature Coming soon" > login-page/README.md

# 3. Commit your changes and push to GitHub
git add login-page/README.md
git commit -m "feat: scaffolding login page"

# 4. Push the feature branch to remote (the branch name is derived by git-flow)
git flow feature push
