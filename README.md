![Vigarch](https://placehold.co/800x200/282a36/f8f8f2?text=Vigarch+PKG+Repo)

## Installation

Add the following code snippet to your `/etc/pacman.conf`:

```
[vigarch]
SigLevel = Optional
Server = https://raw.github.com/cybercraftlabs/vigarch-pkg-repo/main/repo
```

Then, run `sudo pacman -Sy` to update repository.
