# <code>internal-ipaddress</code>

> Get your internal IP address

## Install

```
$ npm install internal-ipaddress
```

## Usage

```js
const internalIp = require('internal-ipaddress');

(async () => {
	console.log(await internalIp.v6());
	//=> 'fe80::1'

	console.log(await internalIp.v4());
	//=> '10.0.0.79'
})();

console.log(internalIp.v6.sync())
//=> 'fe80::1'

console.log(internalIp.v4.sync())
//=> '10.0.0.79'
```

The module returns the address of the internet-facing interface, as determined from the default gateway. When the address cannot be determined for any reason, `undefined` will be returned.

The module relies on operating systems tools. On Linux and Android, the `ip` command must be available, which depending on distribution might not be installed by default. It is usually provided by the `iproute2` package.
