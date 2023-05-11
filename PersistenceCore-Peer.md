<h1 align="center"> State-Sync Peer for PersistenceCore. </h1>
To synchronize, you can use our peer by adding it to the config.toml file.

```
62820f0fcc223171d8d60fb6c38bf7e35047a950@188.172.228.225:26666
```
To add the peer, you can use the following instructions:
```
PEERS=62820f0fcc223171d8d60fb6c38bf7e35047a950@188.172.228.225:26666
sed -i.bak -e "s/^persistent_peers =./persistent_peers = "$PEERS"/" $HOME/.persistenceCore/config/config.toml
```

Alternatively, you can add it manually.
Open the config.toml file with the nano editor.
```
nano .cantod/config/config.toml
```
Add the peer YTWOFUND to the "persistent_peers" line.
