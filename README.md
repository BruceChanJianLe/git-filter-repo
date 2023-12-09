# Git filter-repo

This repository demonstrate usage of filter-repo!
But first, what is filter-repo you might ask?
Have you ever accidentally commit something important you do not want to and push it to a public server?
If yes, this is a tool that can help you remove that sensitive information :D

This note refers to this to [link](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository) and [video](https://www.youtube.com/watch?v=liCAFV8Rmbs&ab_channel=RyanOrsinger)

## Usage
1. Install git-filter-repo
```bash
# I believe it is only available on U22, but hey, you can always use docker
sudo apt install git-filter-repo
```
2. Run THE command
```bash
# cd to your repo
git filter-repo --invert-paths --path PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA
# force it if not a newly clone repo (at your own risk)
git filter-repo --invert-paths --path PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA --force
```
3. Update your repo everywhere
```bash
# git filter-repo will automatically remove your configured remotes, no worries, just add it back
git remote add origin https://github.com/OWNER/REPOSITORY.git
# Force update your remote repo
git push origin --force --all
```

There you go, just 3 simple steps...oh yeah, perhaps more than 3.
