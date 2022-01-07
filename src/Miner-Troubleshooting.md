# Troubleshooting

#### Why I can only restore 1 of my 4 miner addresses ?

You have to specify `isMiner = true` when restoring your miner address. Please checkout the example here: [Restore-Miner-Wallet](GPU-Miner-Guide.md#restore-your-miner-wallet)

#### How to connect my miner to my full node on another computer in the same subnet ?

1. Add the following to your `user.conf` and restart your full node.
```
alephium.mining.api-interface = "0.0.0.0"
```
2. Run your miner with `-a IP`, where the IP is your full node's IP in the subnet.

#### How to use the Swagger UI of my VPS hosted full node ?

SSH port forwarding is recommended:
```
ssh user@server  -L 12973:127.0.0.1:12973
```

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

#### Why `sweep-all` does not transfer all of my coins to another address?

Only one of the 4 addresses is active for miner wallet. You will need to execute `sweep-all` for all of the 4 addresses. There is an endpoint to switch the active address: [change-active-address](GPU-Miner-Guide.md#change-your-active-address), like switching account in MetaMask.
