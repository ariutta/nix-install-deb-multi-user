# Multi-user install script for Nix on Debian

[Nix](https://nixos.org/nix/) has a nice install script for NixOS and macOS, but it doesn't have one for Debian systems.

## Install

```sh
git clone https://github.com/ariutta/nix-install-deb-multi-user.git
cd nix-install-deb-multi-user
sudo -i su -c $(pwd)/nix-install-deb-multi-user
```

## Related

* [nixos-in-place](https://github.com/jeaye/nixos-in-place): Install NixOS on top of any existing Linux distribution without rebooting

## TODO

Right now, `nix-install-deb-multi-user` has the code for downloading the binary. It would be better to use [this script](https://nixos.org/nix/install) to get the binary. The only thing that needs to be changed is this line:
`script=$(echo "$unpack"/*/install)`

That command should be updated so it runs `nix-install-deb-multi-user` when the detected system is Debian.

Also, the downloaded tar archive includes a multi-user install script for macOS. Much of the logic from that script, such as telling the user to remove Nix content from local .profile/.bashrc files could be ported to `nix-install-deb-multi-user`.
