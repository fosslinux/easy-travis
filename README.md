# easy-travis

A set of scripts I use to make Travis CI that bit easier.

## Targets

- Debian {8,9,10,sid}
- Ubuntu {16.04,18.04,19.04}

## How to use in your repository

1. Copy the travis folder to your repository. You probably could probably use a git submodule for this, idk how to.

2. Add the following two lines to the top of your .travis.yml:

```
dist: xenial
sudo: true
```

3. For each of the targets (listed above) you want to use, add the following commands to a job in .travis.yml:

```
- travis/target
- source travis/target-run
```

4. For each of your build commands, add:

```
- run BUILD_CMD
```

to your .travis.yml.

If you want to run a script, add:

```
- run_script SCRIPT_PATH
```

to your .travis.yml.

## How it works

Travis CI only supports Ubuntu 14.04 and 16.04 natively, however there are a 
host of different solutions avaliable to emulate other distributions. 

### LXD

The official recommended way is docker, but I really dislike docker and it 
wasn't working for my purposes, so I'm using LXD. LXD is a container 
virtualization software that emulates an entire Linux distro, including having
an init, etc.
