# Swap file creator for LUKS-encrypted systems #

swap-file-creator automatically creates and enables a swap file on
systems using LUKS full-disk encryption. A new swap file is created on
every boot if the target path resides on a LUKS-encrypted device.

By default, no swap file is created on unencrypted disks. This can be
optionally overridden (not recommended for privacy), allowing swap-file-
creator to operate on unencrypted storage as well.

The tool is particularly useful for systems with low RAM, such as virtual
machines, where lack of swap may cause freezing during upgrades or heavy
memory operations.

The swap file can be shredded on shutdown for additional privacy, if
enabled. Various parameters, including file path, custom size, and
pre-checks, can be configured through /etc/default/swap-file-creator.

Earlier versions provided an additional dm-crypt layer and created a
swap file encrypted with an ephemeral key. Due to a Linux kernel bug,
this functionality is no longer possible as of Debian trixie, and the
swap file is instead placed directly on top of LUKS full-disk
encryption. More details:
https://lore.kernel.org/lkml/20251111231835.1232ad8f@kf-m2g5/T/#u

## How to install `swap-file-creator` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/keys/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com trixie main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `swap-file-creator`.

```
sudo apt-get install swap-file-creator
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `swap-file-creator`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Premium Support](https://www.kicksecure.com/wiki/Premium_Support)

## Donate ##

`swap-file-creator` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!
