# SYNOPSIS 
[![NPM Package](https://img.shields.io/npm/v/expansejs-tx.svg?style=flat-square)](https://www.npmjs.org/package/expansejs-tx)
[![Build Status](https://img.shields.io/travis/expansejs/expansejs-tx.svg?branch=master&style=flat-square)](https://travis-ci.org/expansejs/expansejs-tx)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)  

# INSTALL
`npm install expansejs-tx`

# USAGE

  - [example](https://github.com/expansejs/expansejs-tx/blob/master/examples/transactions.js)

```javascript
const EthereumTx = require('expansejs-tx')
const privateKey = Buffer.from('e331b6d69882b4cb4ea581d88e0b604039a3de5967688d3dcffdd2270c0fd109', 'hex')

const txParams = {
  nonce: '0x00',
  gasPrice: '0x09184e72a000', 
  gasLimit: '0x2710',
  to: '0x0000000000000000000000000000000000000000', 
  value: '0x00', 
  data: '0x7f7465737432000000000000000000000000000000000000000000000000000000600057',
  // EIP 155 chainId - mainnet: 1, ropsten: 3
  chainId: 3
}

const tx = new EthereumTx(txParams)
tx.sign(privateKey)
const serializedTx = tx.serialize()
```

**Note:** this package expects ECMAScript 6 (ES6) as a minimum environment. From browsers lacking ES6 support, please use a shim (like [es6-shim](https://github.com/paulmillr/es6-shim)) before including any of the builds from this repo.


# BROWSER  
For a browser build please see https://github.com/expansejs/browser-builds.

# API
[./docs/](./docs/index.md)

# LICENSE
[MPL-2.0](https://tldrlegal.com/license/mozilla-public-license-2.0-(mpl-2))
