![Vigarch](https://placehold.co/800x200/282a36/f8f8f2?text=Berserk+PKG+Core)

## Installation

Add the following code snippet to your `/etc/pacman.conf`:

```bash
[berserkarch]
SigLevel = Optional TrustAll
Server = https://gitlab.com/berserkarch/berserk-packages/berserk-pkg-builds/-/raw/main/repo
```

```bash
# Add the key to pacman's keychain
sudo pacman-key --add gauravraj_pubkey.asc

# Locally sign the key, telling pacman you trust it to sign packages
sudo pacman-key --lsign-key B024DCEFADEF4328B5E3A848E7E0F2B78484DACF
```

Then, run `sudo pacman -Sy` to update repository.
