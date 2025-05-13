# Git Submodules

[*source: Atlassian*](https://www.atlassian.com/git/tutorials/git-submodule)

Repository can not have other repositories inside it, but they can have links to other repositories (submodules).

- git commands only work in the root of the base repository / submodule, without effecting the other repo
- cloning the base repo dose not clone submodules

## Cloning submodules

1. clone the base repo: `git clone /url/to/repo/with/submodules`
2. adjust the list of the submodules in `.gitmodules` to control which submodules are cloned with the next command
3. download the submodules `git submodule init`
4. update the submodules to the latest commits `git submodule update`

## Linking submodules to a repository

1. at the root of the base repo run: `git submodule add https://bitbucket.org/jaredw/awesomelibrary` + ` <directory>` 
   (*maybe use the ssh link and directory is optional*)

---

### Problems

#### Submodule wants to auth old way with username/password

[*source: DEV*](https://dev.to/lwdjohari/configuring-git-multi-repository-setup-with-submodules-write-access-via-git-ssh-read-only-via-4mg2)

The problem is that even if you are using ssh in the root repo to authenticate (for push / pull), that the submodule is maybe set for `HTTPS` connection.

1. From the root run `git submodule foreach 'git remote -v ` to see push and fetch settings
   if `https://github.com/<your-git-user>/core.git (push)`, ...
2. From submodule-root run `git remote set-url --push origin git@github.com-<your-git-user>:<your-git-user>/core.git`