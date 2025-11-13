# Creates a swap file on LUKS-encrypted systems #

On every boot, creates a swap file on LUKS-encrypted systems.
Checks if the system is using LUKS encryption before creating a
swap file.

Can optionally also create a swap file on unencrypted systems.
Useful for systems with low RAM, such as inside virtual machines.

Has an option to shred the swap file on shutdown.

Earlier versions created an encrypted swap file by default, which
was encrypted with an ephemeral key. Unfortunately, this is no longer
possible as of Debian trixie due to a Linux kernel bug.
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
