# crypto

## Simple symmetric GPG file encryption and decryption

## About
crypto provides a simple interface to symmetric Gnu Privacy Guard (gpg) encryption and decryption for one or more files on Unix and Linux platforms.  It runs on top of gpg and requires a gpg install on your system.  Encryption is performed with the AES256 cipher algorithm.

Encryption benchmarks vs. default gpg encryption are available [here](http://chrissimpkins.github.io/crypto/benchmarks.html) with additional details for [text](http://chrissimpkins.github.io/crypto/text-benchmarks.html), [pdf](http://chrissimpkins.github.io/crypto/pdf-benchmarks.html), [mp3](http://chrissimpkins.github.io/crypto/mp3-benchmarks.html), and [png](http://chrissimpkins.github.io/crypto/png-benchmarks.html) mime types.

crypto provides a number of options including automated tar archives of multiple files prior to encryption, portable ASCII armored encryption formatting, and SHA256 hash digest generation for your encrypted files.

## Documentation

Detailed documentation is available [here](http://chrissimpkins.github.io/crypto/index.html).

## Quickstart

#### Encrypt a File
```
$ crypto sometext.txt
```

#### Encrypt with Portable ASCII Armored Format
```
$ crypto --armor sometext.txt
```

#### Encrypt Multiple Files with Same Passphrase
```
$ crypto sometext.txt anotherimage.jpg
```

#### Encrypt Multiple Files with Wildcard Expansion
```
$ crypto *.txt
```

#### Encrypt and Generate SHA256 Hash Digest of the Encrypted File
```
$ crypto --hash sometext.txt
```

#### Encrypt All Top Level Files in Multiple Directories with Same Passphrase
```
$ crypto imagedir privatedir
```

#### Pack Multiple Files in a Tar Archive, Then Encrypt the Archive
```
$ crypto --tar privatedir
```

#### Decrypt a File
```
$ decrypto sometext.txt.crypt
```

#### Decrypt All Encrypted Files in Top Level of Directory
```
$ decrypto privatedir
```

#### Decrypt Text to Standard Output Stream
```
$ decrypto --stdout sometext.txt.gpg
```


## Install

### 1) Install GPG

#### Mac OSX Users
Mac OSX users can install gpg from [source](https://www.gnupg.org/download/index.html), with [Homebrew](http://brew.sh/), or by installing the [Mac GPG Tools Suite](https://gpgtools.org/gpgsuite.html).

The Homebrew install command is:

```
brew install gpg
```

Please refer to the detailed documentation on the Gnu Privacy Guard and Mac GPG Tools suite sites for more information if you choose the source or GPG Tools approaches.

#### Linux Users
If gpg is not installed on your Linux distro, you can use your package manager to install it or compile and install it from the [source](https://www.gnupg.org/download/index.html).

### 2) Install crypto
You can install crypto with [pip](https://pypi.python.org/pypi/pip/):

```
pip install crypto
```

or download the [crypto source](https://github.com/chrissimpkins/crypto/archive/master.zip), unpack it, navigate to the top level directory, and install with the command:

```
python setup.py install
```

## Options

### crypto Options

#### `--armor | -a`

Encrypt in a portable ASCII armored format

#### `--hash`

Generate SHA256 hash digest of encrypted file(s)

#### `--space`

Favor reduced file size over encryption speed

#### `--speed`

Favor encryption speed over reduced file size

#### `--tar`

Create tar archives from directories of files, then encrypt

### decrypto Options

#### `--nountar`

Do not automatically unpack tar archives after decryption

#### `--overwrite | -o`

Overwrite an existing file with the new decrypted file

#### `--stdout | -s`

Push the decrypted data to the standard output stream instead of generating a new file

### Other Options

#### `--help | -h`

View the help documentation

#### `--usage`

View the usage documentation

#### `--version | -v`

View the crypto version number


## Issues

Please submit a [new issue report on the GitHub repository](https://github.com/chrissimpkins/crypto/issueshttps://github.com/chrissimpkins/crypto/issues) with a detailed overview of the problem that you are having.


## Project Contributors

- [Christoph Russ](https://github.com/christophruss) (@christophruss)

---
[MIT License](https://github.com/chrissimpkins/crypto/blob/master/docs/LICENSE) | Built with the [Naked Framework](https://pypi.python.org/pypi/Naked)
