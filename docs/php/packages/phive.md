# The PHAR Installation and Verification Environment (PHIVE)

https://phar.io/

> Install phar distributed PHP applications with easy.

### How it works

PHIVE makes installation easy by providing a means to resolve the given alias to an actual download location, including the verification of the certificate supplied by the server. Once downloaded, the archive’s SHA1, SHA256 or SHA512 hash is verified as well as its OpenPGP/GnuPG signature.

Instead of re-downloading the same phar multiple times, the archive is kept at a shared location (by default in ~/.phive) and only a symbolic link is created for the project. You can of course also explicitly request a copy of the phar to be made in favor of symbolic links (use --copy).

### Installation
```sh
wget -O phive.phar https://phar.io/releases/phive.phar
wget -O phive.phar.asc https://phar.io/releases/phive.phar.asc
gpg --keyserver hkps://keys.openpgp.org --recv-keys 0x9D8A98B29B2D5D79
gpg --verify phive.phar.asc phive.phar
chmod +x phive.phar
sudo mv phive.phar /usr/local/bin/phive
```

### Usage
```sh
# List all available packages
phive list
# List all installed packages
phive status --all
# Install psalm
phive install psalm
```


```sh
# Install using phar.io registered alias
phive install phpunit
# Install using github <name>/<repository>
phive install theseer/Autoload
# Ignore security implications and install unsigned phar via github <name>/<repository>
phive install --force-accept-unsigned vendor/unsigned-project
# Install using a fixed url
phive install https://phar.phpunit.de/phpunit-7.3.5.phar
# When used in CI environments - specify trusted keys and suppress progress output
phive --no-progress install --trust-gpg-keys 4AA394086372C20A,2A8299CE842DD38C phpab phpunit
# Create a copy of the phar rather than using a symlink
phive install --copy phpdox
# Install a phar with a specified version constraint
phive install psalm@^4.1.1
# Use ./build/tools directory rather than default ./tools as symlink target folder
phive install --target ./build/tools phpdox
# Install all phar files declared in phive.xml
phive install
```
