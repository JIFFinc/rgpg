# rgpg [![Install gem](https://badge.fury.io/rb/rgpg.png)](https://rubygems.org/gems/rgpg) [![Build status](https://travis-ci.org/rcook/rgpg.png?branch=master,0.3.0,0.2.4)](https://travis-ci.org/rcook/rgpg)

A simple Ruby wrapper around `gpg` command for file encryption. This version only guaranteed to work with gpg 2.0.22 to 2.2.0.

_rgpg_ is a simple API for interacting with the `gpg` tool. It is specifically designed to avoid altering global keyring state by creating temporary public and secret keyrings on the fly for encryption and decryption.

# Installation

```bash
gem install rgpg
```

# Usage from terminal

This gem adds an `rgpg` command. Type `rgpg` for usage information.

# API usage

## To generate a GPG public-private key pair

```ruby
require 'rgpg'

Rgpg::GpgHelper.generate_key_pair 'mykey', 'me@example.com', 'Joe Bloggs'
```

## To encrypt a file

```ruby
require 'rgpg'

Rgpg::GpgHelper.encrypt_file 'mykey.pub', 'myfile.txt', 'myfile.txt.enc'
```

## To decrypt a file

```ruby
require 'rgpg'

Rgpg::GpgHelper.decrypt_file 'mykey.pub', 'mykey.sec', 'myfile.txt.enc', 'myfile.txt' [, 'secret_key_passphrase']
```

# Licence

_rgpg_ is released under the MIT licence.

