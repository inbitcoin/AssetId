# AssetID-Encoder

> Issuance-Encoder provides the encode/decode functions between a Colored Coins issuance Object to buffer

### Installation

```sh
$ npm install cc-assetid-encoder
```


### Encode Asset ID

Params:
    - BitcoinTransaction - An Object with contains at least the following properties:

```js
{
  'ccdata': [{
    'type': 'issuance',
    'lockStatus': false,
  }],
  'vin': [{
    'txid': '0f45f38a8bcd8331877267e0f3f5f8a4b3c716165e40db4eee34d52759ad954f',
    'vout': 2,

    // The following properties are optional but at least one is required in
    // case 'lockStatus' is FALSE
    'scriptSig': {
      'asm': '3045022100daf8f8d65ea908a28d90f700dc932ecb3b68f402b04ba92f987e8abd7080fcad02205ce81b698b8013b86813c9edafc9e79997610626c9dd1bfb49f60abee9daa43801 029b622e5f0f87f2be9f23c4d82f818a73e258a11c26f01f73c8b595042507a574',
    }
    'address': 'mxNTyQ3WdFMQE7SGVpSQGXnSDevGMLq7dg'
  }]
}


```

Returns a new Buffer holding the encoded issuance.

##### Example:

```js
var assetIdEncoder = require('cc-assetid-encoder')

var bitcoinTransaction = {
  'ccdata': [{
    'type': 'issuance',
    'lockStatus': false,
  }],
  'vin': [{
    'txid': '0f45f38a8bcd8331877267e0f3f5f8a4b3c716165e40db4eee34d52759ad954f',
    'vout': 2,
    'scriptSig': {
      'asm': '3045022100daf8f8d65ea908a28d90f700dc932ecb3b68f402b04ba92f987e8abd7080fcad02205ce81b698b8013b86813c9edafc9e79997610626c9dd1bfb49f60abee9daa43801 029b622e5f0f87f2be9f23c4d82f818a73e258a11c26f01f73c8b595042507a574',
    }
  }]
}

assetIdEncoder(bitcoinTransaction)
// Will print 'Ua3Kt8WJtsx61VC8DUJiRmseQ45NfW2dwLbG6s'

```


### Testing

In order to test you need to install [mocha] globaly on your machine

```sh
$ cd /"module-path"/cc-assetid-Encoder
$ mocha
```


## License

This software is licensed under the Apache License, Version 2.0.
See [LICENSE](LICENSE) for the full license text.


[mocha]:https://www.npmjs.com/package/mocha
