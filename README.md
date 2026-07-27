# Minecraft Protocol 26.2

Standalone protocol 776 implementation for Minecraft Java 26.2, maintained by
[Complexity-ML](https://github.com/Complexity-ML) for
[GAME LAB](https://github.com/Complexity-ML/game-lab).

| Package | Runtime | Minecraft Java | Protocol |
| --- | --- | --- | --- |
| `minecraft-protocol@1.66.2+complexity.26.2.3` | Node.js 22+ | 26.2 | 776 |

## Install

```bash
npm install "https://github.com/Complexity-ML/node-minecraft-protocol-26.2/releases/download/complexity-26.2.3/minecraft-protocol-complexity-26.2.3.tgz"
```

The release pins the standalone
[`minecraft-data-26.2`](https://github.com/Complexity-ML/node-minecraft-data-26.2)
package and does not depend on a deleted fork or Git submodule.

## Offline client example

```js
const mc = require('minecraft-protocol')

const client = mc.createClient({
  host: '127.0.0.1',
  port: 25565,
  username: 'GAME_LAB_Bot',
  auth: 'offline',
  version: '26.2'
})

client.once('login', () => console.log('Connected with protocol 776'))
client.on('error', console.error)
```

Use offline authentication only on a private server you own or are explicitly
authorized to automate.

## 26.2 coverage

- protocol version 776;
- login `sessionId` and `onlineMode` changes;
- configuration and play packet mappings;
- world-clock updates;
- corrected 26.2 entity metadata serializers;
- corrected advancement icon item-stack templates;
- corrected 26.2 data-component registry IDs;
- client and server serialization;
- online and offline authentication paths.

The release was validated against the official Minecraft Java 26.2 server:
login succeeded and 2,643 live packets were parsed with zero errors. The 26.2
server test suite contains 11 passing tests.

## Documentation

- [Full usage guide](docs/README.md)
- [API reference](docs/API.md)
- [Protocol notes](docs/HISTORY.md)
- [Releases](https://github.com/Complexity-ML/node-minecraft-protocol-26.2/releases)

## Credits and license

Derived from
[PrismarineJS node-minecraft-protocol](https://github.com/PrismarineJS/node-minecraft-protocol).
The upstream history and contributor attribution are retained. Complexity-ML
maintains this 26.2 distribution independently and is not affiliated with
Mojang or Microsoft.

Licensed under the [BSD 3-Clause License](LICENSE).
