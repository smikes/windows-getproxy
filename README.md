# windows-getproxy

## Get HTTP proxy url for Windows

This is a small module to get `http` proxy information for Windows
and expose it to Unix-like clients that expect HTTP_PROXY, 
HTTPS_PROXY, and NO_PROXY environment variables

# Command-line Usage

```
> npm install -g windows-getproxy
> windows-getproxy
> echo %HTTP_PROXY%
..magically, your proxy settings are here..
```

# Programmatic usage

```
npm install --save windows-getproxy
```

```
var wgp = require("windows-getproxy");

wgp.get_proxy(function (err, proxy) { console.log(proxy); });     # writes proxy to stdout
```

# API

## `get_proxy(cb)`

Spawns the `REG.EXE` command to get the proxy settings.

# Supported OS

The `REG.EXE` command has been present in all versions of Windows since Windows XP / Windows 2003 Server,
so this should work on all currently-suppoted Windows variants, and may work on some older versions.

# TODO

 ( ) implement this
 ( ) parse ProxyOverride key and export as NO_PROXY
 ( ) lots of testing
 
 # Author 
 
 Sam Mikes <smikes@cubane.com>
 
 # License 
 
 MIT
