## Objetivo 
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
## Solución
```bash
bandit29@bandit:~$ mkdir /tmp/repos
mkdir: cannot create directory ‘/tmp/repos’: File exists
bandit29@bandit:~$ mkdir /tmp/repos29
bandit29@bandit:~$ cd /tmp/repos29
bandit29@bandit:/tmp/repos29$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/repos29$ ls
repo
bandit29@bandit:/tmp/repos29$ cd repo
bandit29@bandit:/tmp/repos29/repo$ ls
README.md
bandit29@bandit:/tmp/repos29/repo$ cat readme
cat: readme: No such file or directory
bandit29@bandit:/tmp/repos29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/repos29/repo$ git log
commit 4364630b3b27c92aff7b36de7bb6ed2d30b60f88 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:43 2023 +0000

    fix username

commit fca34ddb7d1ff1f78df36538252aea650b0b040d
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:43 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/repos29/repo$ git checkout fca34ddb7d1ff1f78df36538252aea650b0b040d
Note: switching to 'fca34ddb7d1ff1f78df36538252aea650b0b040d'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at fca34dd initial commit of README.md
bandit29@bandit:/tmp/repos29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit29
- password: <no passwords in production!>

bandit29@bandit:/tmp/repos29/repo$ git checkout 4364630b3b27c92aff7b36de7bb6ed2d30b60f88
Previous HEAD position was fca34dd initial commit of README.md
HEAD is now at 4364630 fix username
bandit29@bandit:/tmp/repos29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/repos29/repo$ git branch -a
* (HEAD detached at 4364630)
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/repos29/repo$ git checkout remotes/origin/dev
Previous HEAD position was 4364630 fix username
HEAD is now at 1d160de add data needed for development
bandit29@bandit:/tmp/repos29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/repos29/repo$
```


## Notas
con git branch pordemos ver tambien las ramas en un repositorio

## Referencias
manual de usuario del comando git