# Adds encrypted swap file to the system #

On every boot, creates a new encrypted swapfile with a random password.

Useful for systems with low RAM such as inside virtual machines.

Has an option to shred the swapfile on shutdown.
## How to install `swap-file-creator` using apt-get ##

1\. Download [Whonix's Signing Key]().

```
wget https://www.whonix.org/patrick.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add Whonix's signing key.

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg add ~/patrick.asc
```

3\. Add Whonix's APT repository.

```
echo "deb https://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `swap-file-creator`.

```
sudo apt-get install swap-file-creator
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `swap-file-creator` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`swap-file-creator` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
