CRC32 like Crypto
=================

This small module creates CRC32 checksum in Crypto style.

In order to access the module use `require('crc32Crypto')`.

In case you just downloaded the .js file, use `require('path/to/crc32crypto.js')`.


crc32crypto.createHash(algorithm)
---------------------------------

Creates a crc32 hash object.

In order to create CRC32 checksum set `algorithm` as `'crc32'`. If `algorithm` differs from `'crc32'` this function creates new Crypto hash with that algorithm instead.


hash.update(data)
-----------------

Just like in Crypto, appends a new chunk of data to the hash. This function may be called as many times as it is needed.

`data` argument expects string or `Buffer` object. 

Unlike Crypto, if data is not a string or Buffer it is coerced to string. That is, `hash.update(new Buffer("123"))` and `hash.update(123)` is essentially the same.


hash.digest(encoding='binary')
------------------------------

Returns checksum of all data passed via `hash.update()`. The encoding is one of `'hex'`, `'binary'` and `'base64'`.

Unlike Crypto, this module doesn't "lock" the data after digest is returned.