# CyberConnect

# cyberconnect-kotlin-lib
cyberconnect-kotlin-lib is a lib support CyberConnect API, here is an example repo using it
[cyberconnect-kotlin-example](https://github.com/cyberconnecthq/cyberconnect-kotlin-example)

## Getting started

### Installation
For now you can integrate the lib manually, we will support gradle integration very soon!

### Basic usage

#### Init CyberConnect

```kotlin
val cyberConnectInstance = CyberConnect(YOURWALLETADDRESS)
```

#### Authenticate

Once you get authntication from CyberConnect, you can use CyberConnect to build your own social graphs

```kotlin
cyberConnectInstance.registerKey(signature, network) { result in
  //handle the result
}
```
- `signature` - The signature of a particular message, you can get the message using, you can sign the message with your own wallet third party wallet:
```kotlin
val publicKeyString = cyberConnectInstance.getPublicKeyString()
val message = cyberConnectInstance.getAuthorizeString(publicKeyString)
```
- `network` - enum type for network, now support ETH and Solana

#### Connect

```kotlin
cyberConnectInstance.connect(toAddress, alias, network) { result in
  //handle the result
}
```

- `toAddress` - The target wallet address to connect.
- `alias` - (optional) Alias for the target address.
- `network` - (optional) enum type for network, now support ETH and Solana.
- `connectionType` - (optional) The type of the connection. The default value is `Connection.FOLLOW`. See [Connection Type](#ConnectionType) for more details.

#### Disconnect

```kotlin
cyberConnectInstance.disconnect(toAddress, alias, network) { result in
  //handle the result
}
```

- `toAddress` - The target wallet address to disconnect.
- `alias` - (optional) Alias for the target address.
- `network` - (optional) enum type for network, now support ETH and Solana.

#### GetBatchConnectStatus

```kotlin
cyberConnectInstance.getBatchConnections(toAddresses) { result in
  //handle the result
}
```

- `toAddresses` - A list of wallet addresses to connect.

#### SetAlias

```kotlin
cyberConnectInstance.alias(toAddress, alias, network) { result in
  //handle the result
}
```

- `toAddress` - The target wallet address to disconnect.
- `alias` - The alias for the target address.
- `network` - (optional) enum type for network, now support ETH and Solana.


## Contributing

We are happy to accept all kind of contributions, feel free to open issue or pull requests, you can also post your questions in our [Discord Channel](https://discord.gg/cyberconnect)

For other tech info refer to our [dev center](https://docs.cyberconnect.me).

