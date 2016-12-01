# docker-ubuntu-base
## A Useful base for Ubuntu 16.04 (xenial):

Installing different Ruby, Python and NodeJS versions is annoying in a 
Docker installation:
 
> Why is my Ubuntu stuck on a 3 year old version of NodeJS? 

> Does that guy properly maintain his Xenial Python apt-get repo for 
2.7? 

> How do you make the Docker cache not flail with apt-get -y update 
every time I need to bump ruby versions?

**Ugh!**

Instead of worrying about those, use common language version management 
systems widely supported by the community.

This speeds up your dev time, Docker builds and lets you focus on your
app, not on futzing with apt-get.

Brought to you by the Friendly Dev Team™ at HONK Technologies!

## What's Included?

- rbenv - to manage Ruby installations   (1.1.0)
- n     - to manage NodeJS installations (2.1.0)
- pyenv - to manage Python installations (1.0.4)
- curl, wget, git, vim, rsyslog etc.     (latest versions for xenial)

## Inheriting this Docker image

```Dockerfile
FROM honkdev/ubuntu-base

# Gets the most current LTS version of NodeJS
# Note: n's install command also sets it as the global node version
RUN n lts

# Installs Ruby 2.3.3 and sets it as the global version of Ruby
RUN rbenv install 2.3.3 && rbenv global 2.3.3

# Installs Python 2.7.1 and sets it as the global version of Python
RUN pyenv install 2.7.1 && pyenv global 2.7.1

# Now you have those languages installed,
# Do your application specific stuff here!
```

## Your stuff is out of date!

Open an issue and we'll get a rebuild going quickly.

## There's a cool language missing!

If that language has a nice version management utility that *doesn't
rely* on installing tons of other stuff, fork this repo, add it, then
open a PR! 

We gladly welcome contributions from the community!
