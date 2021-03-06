# EOS Encrypt

# !! THIS REPO HAS MOVED [EOS-Nation/eos-encrypt](https://github.com/EOS-Nation/eos-encrypt)

Allows to encrypt & decypt a message with an EOS key pair using AES shared key encryption mechanism.

Decryption is achieved by combining the receiver's private key and the sender's public key to create the private key necessary to decrypt the message.

This module uses `eosjs-ecc` to perform the required cryptographic operations.

## Install

**npm**

```bash
$ npm install --save eos-encrypt
```

## Usage

```js
import { encrypt, decrypt } from 'eos-encrypt';

const public_key = "EOS6MRyAjQq8ud7hVNYcfnVPJqcVpscN5So8BhtHuGYqET5GDW5CV";
const private_key = "5KQwrPbwdL6PhXujxW37FSSQZ1JiwsST4cqQzDeyXtP79zkvFD3";

const message = "Private Message, shhhh!";
const encrypted = encrypt(private_key, public_key, message);
// => TO DECRYPT: eos-communication
// .1167451677...23460624..862584768Q+h1AeLQbjfzZJD1Nsx6kk3U/jSNStwoWstz9uNCadw=

const decrypted = decrypt(private_key, public_key, encrypted);
// => Private Message, shhhh!
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [encrypt](#encrypt)
    -   [Parameters](#parameters)
    -   [Examples](#examples)
-   [decrypt](#decrypt)
    -   [Parameters](#parameters-1)
    -   [Examples](#examples-1)

### encrypt

Encrypt Message

#### Parameters

-   `private_key` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** EOSIO Private Key
-   `public_key` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** EOSIO Public Key
-   `message` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Message to Encrypt
-   `maxsize` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Maximum character message size (optional, default `256`)

#### Examples

```javascript
const encrypted = encrypt(private_key, public_key, message);
```

Returns **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Encrypted Message

### decrypt

Decrypt Message

#### Parameters

-   `private_key` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** EOSIO Private Key
-   `public_key` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** EOSIO Public Key
-   `message` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Encrypted Message

#### Examples

```javascript
const decrypted = decrypt(private_key, public_key, message);
```

Returns **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Decrypted Message
