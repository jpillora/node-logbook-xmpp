[Logbook](https://github.com/jpillora/node-logbook) XMPP Plugin
============

### Quick Usage

```
npm install --save logbook logbook-xmpp
```

Disable console and send `stderr` to everyone in your contact list:

``` javascript
require('logbook').configure({
  console: {
    enabled: false
  },
  xmpp: {
    enabled: true,
    jid: '...@gmail.com',
    password: '...',
  }
});
```

To prevent too much spam, only `stderr` is logged by default.
This can changed with `xmpp.log: true`.

### Options

##### `to`

An array of `jid` Jabber IDs (Google Accounts in the case of Google Talk).
By default it's the string "*", which means everyone in the given
accounts contact list. Useful if you create
a logbook Jabber account, then you can "subscribe" to it at will.

##### `delay`

This is the delay (in milliseconds) before all acculated messages are concatenated and sent.
This helps to prevent performance loss by batching synchronous messages.

##### `prefix`

This string will be prefixed to every message

##### `machineName`

The machines name (`hostname` on Unix) will be prefixed to every message

### Defaults

  "xmpp": {
    "enabled": false,
    "jid": null,
    "password": null,
    "host": "talk.google.com",
    "port": 5222,
    "to": "*",
    "prefix": null,
    "machineName": false,
    "delay": 100,
    "log": false,
    "err": true
  }