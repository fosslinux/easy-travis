# easy-travis

A set of scripts I use to make Travis CI that bit easier.

## Targets

- Debian {8,9,10,sid}
- Ubuntu {16.04,18.04,19.04}

## How it works

Travis CI only supports Ubuntu 14.04 and 16.04 natively, however there are a 
host of different solutions avaliable to emulate other distributions. 

## LXD

The official recommended way is docker, but I really dislike docker and it 
wasn't working for my purposes, so I'm using LXD. LXD is a container 
virtualization software that emulates an entire Linux distro, including having
an init, etc.
