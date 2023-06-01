<h1 align="center"> State-Sync Peer for PersistenceCoreTestnet. </h1>
To synchronize, you can use our peer by adding it to the config.toml file.

```
171e837618d9ec0b5faf0c91edc0cc3edd1cf204@188.172.228.225:26656
```
To add the peer, you can use the following instructions:
```
PEERS=171e837618d9ec0b5faf0c91edc0cc3edd1cf204@188.172.228.225:26656
sed -i.bak -e "s/^persistent_peers =./persistent_peers = "$PEERS"/" $HOME/.persistenceCore/config/config.toml
```

Alternatively, you can add it manually.
Open the config.toml file with the nano editor.
```
nano .cantod/config/config.toml
```
Add the peer YTWOFUND to the "persistent_peers" line.
