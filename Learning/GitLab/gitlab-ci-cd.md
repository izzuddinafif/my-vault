#gitlab #ci/cd

[YouTube Video](https://www.youtube.com/watch?v=8aV5AxJrHDg&t=228s&ab_channel=LambdaTest)

# Git basics refresher
I will only list commands that are new to me here.
```sh
git init reponame # initializing a repo under certain dir name
git config --global init.defaultBranch main # set default branch name as main
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
git restore filename # discard changes
```

# The Gitlab Interface
## Key Gitlab Terms 

### Group
- Allow you to manage settings across multiple projects
- Logically categorize multiple users or projects
- Provide a cross-project view
### Project
- A container for a git repo
- Built-in CI/CD
- Issue tracking
- Collaboration tools (merge request, etc)
### Member
- Users or Groups that have access to a project
- Members are assigned to roles
- Member roles include permissions to perform actions on projects or groups
### Merge Requests
- A request to merge one branch into another
- Merge requests provide a space to have a conversation with the team about the changes on a branch
- It is the central place through which changes are reviewed and verified
### Issue
- An issue is a way to track work related to a gitlab project
- Issues can be used to report bugs, track tasks, request new features, ask questions and more
- Development workflow should begin with an issue
