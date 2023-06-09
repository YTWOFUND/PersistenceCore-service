<h1 align="center"> Snapshot User Guide </h1>
<h3 align="left"> The node snapshot is taken once a day, at 03:00 UTC +2. </h3>

The snapshot is implemented through the tar archiver and compressed with lz4. To unpack the snapshot, it is necessary to install lz4.
```
sudo apt update
sudo apt install snapd -y
sudo snap install lz4
```
Download the snapshot:
```
wget -O persistenceCoreTest.tar.lz4 https://ytwofund.pro/snapshot/persistenceCoreTest/persistenceCoreTest.tar.lz4 --inet4-only
```
Stop the node:
```
systemctl stop persistenceCore.service
```
Reset the node's data:
```
persistenceCore tendermint unsafe-reset-all --home $HOME/.persistenceCore --keep-addr-book
```
Unpack the snapshot to the location of your database:
```
lz4 -c -d persistenceCoreTest.tar.lz4  | tar -x -C $HOME/.persistenceCore/data/
```
Restart the node:
```
systemctl restart persistenceCore.service
```
Request the logs to make sure the node is working and synchronization has started:
```
sudo journalctl -u persistenceCore -f
```
To save space, delete the downloaded snapshot:
```
rm -rf persistenceCoreTest.tar.lz4
```
If everything is done correctly, synchronization with the network will start, but it may take some time.

If you have any problems, please let us know at ytwofund@gmail.com.
