![Vigarch](https://placehold.co/800x200/282a36/f8f8f2?text=BerserkArch+PKG+Builds)

## Installation

Add the following code snippet to your `/etc/pacman.conf`:

```bash
[berserkarch]
SigLevel = Optional TrustAll
Server = https://gitlab.com/berserkarch/berserk-packages/berserk-pkg-builds/-/raw/main/repo
```

Then, run `sudo pacman -Sy` to update repository.
