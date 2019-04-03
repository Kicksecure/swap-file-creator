# Adds encrypted swap file to the system #

On every boot, creates a new encrypted swapfile with a random password.

Useful for systems with low RAM such as inside virtual machines.

Has an option to shred the swapfile on shutdown.
## How to install `swap-file-creator` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org buster main" | sudo tee /etc/apt/sources.list.d/whonix.list
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

## Payments ##

`swap-file-creator` requires [payments](https://www.whonix.org/wiki/Payments) to stay alive!
