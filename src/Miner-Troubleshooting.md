# Troubleshooting

#### How to connect my miner to my full node on another computer in the same subnet ?

1. Add the following to your `user.conf` and restart your full node.
```
alephium.mining.api-interface = "0.0.0.0"
```
2. Run your miner with `-a IP`, where the IP is your full node's IP in the subnet.

#### How to access the Swagger UI of my full node on another computer in the same subnet ?

1. Add the following to your `user.conf` and restart your full node.
```
alephium.api.network-interface = "0.0.0.0"
```
2. Change the `host` of Swagger UI to be the IP of your full node.

#### My miner (via run-miner.sh) cannot connect to my full node on another computer

The script `run-miner.sh` connects to `127.0.0.1` by default. You will need to add `-a IP` into `run-miner.sh`.

#### Why the miner uses huge amount of memory on HiveOS?

You should deactivate the `log to write in RAM` with command `logs-on`.
