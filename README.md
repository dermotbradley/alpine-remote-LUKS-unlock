# alpine-remote-LUKS-unlock

These represent patched versions of the Alpine dropbear and mkinitfs
packages to provide functionality so that when a LUKS-encrypted system is
booted that a SSH server is run by the initram init process that waits for a
SSH connection to be made and them prompts for the LUKS passphrase to unlock
the encrypted root filesystem before continuing with booting as usual.

These changes to the mkinitfs package have already been submitted as a MR:
https://gitlab.alpinelinux.org/alpine/mkinitfs/-/merge_requests/86

These changes to the dropbear package have not yet been submitted to the
Alpine dropbear package in the aports repo as I am waiting for the mkinitfs
MR to be accepted (as it is possible some changes may be requested before
those changes are merged).

The dropbear and mkinitfs directories in this repo represent already patched
versions of the two packages that can be built and stored in a local Alpine
repo.

NOTE: if you use such locally built packages there is a danger that any update
to either of the upstream versions of these packages could break this remote
unlock functionality if/when upstream "official" packages are
installed/upgraded on a system.
