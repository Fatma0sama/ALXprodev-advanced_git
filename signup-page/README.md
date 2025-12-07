# --- Part 1: Second Feature and Merge ---
# Ensure you are back on the develop branch to start the second feature
git checkout develop

# 1. Create a new feature branch feature/implement-signup
git flow feature start implement-signup

# Create directory and README.md
mkdir signup-page
echo "feature coming soon" > signup-page/README.md

# Commit the changes and push to github
git add signup-page/README.md
git commit -m "feat: scaffolding signup page"
git flow feature push

# Merge the 2 branches to the develop branch
# Finish the signup feature (this merges it into develop and deletes the local feature branch)
git flow feature finish implement-signup -k # The -k flag keeps the remote branch for a moment, but local merge is key

# Now, manually merge the first feature (implement-login) into develop as well
# The simplest way is to finish the first feature now, which was committed earlier.
# Note: If you prefer to keep the remote branch, use -k, otherwise it deletes the remote feature branch.
git flow feature finish implement-login

# --- Part 2: Release Process ---
# 2. Create a new release branch release/1.0.0
# The git flow release start command creates the branch from develop and switches to it.
git flow release start 1.0.0

# 3. Make changes to signup/README.md file by adding the specified text inside the release branch
echo -e "\ndata requirements: [email, firstName, lastName, profilePic]" >> signup-page/README.md

# Commit and push changes to github
git add signup-page/README.md
git commit -m "fix: added data requirements to signup page for release 1.0.0"
git push

# 4. Merge the release branch to the main branch and the develop branch, and tag the release.
# The git flow release finish command handles all the merging (release -> main, release -> develop),
# deletion of the release branch, and tagging.
git flow release finish 1.0.0 -m "Release version 1.0.0: Implemented login and signup scaffolding."

# 5. Push the tags to the remote repository
git push --tags
