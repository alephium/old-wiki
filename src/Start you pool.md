## Build



1. [install redis](https://redis.io/topics/quickstart)
    > ubuntu ``` sudo apt install redis-server```
    
2. [install alephium full node](https://wiki.alephium.org/Full-Node-Starter-Guide.html)
   > be sure to specify in user.conf (see the instructions [Configure Miner Addresses section](https://wiki.alephium.org/GPU-Miner-Guide.html#configure-miner-addresses)) 
   > the mining addresses that you will use in [config.json](https://github.com/alephium/mining-pool/blob/master/config.json)  of the pool. they must match
3. install node.js(>=14) and npm(>=8)
   > install nvm '''wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash'''
   > at this point there will be a problem, the system does not see that nvm is installed. you can use '''[[ -s $HOME/.nvm/nvm.sh ]] && . $HOME/.nvm/nvm.sh'''
   > now install node.js ```nvm install 14.15``` and 
   > update npm ``` npm install -g npm```
   
4.wait until your node is fully synchronized, then you need to log in to your miner wallet (whose address you specified in user.conf and config.json).
   
   ```sh
   curl -X 'PUT' \
  'http://127.0.0.1:12973/wallets' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'X-API-KEY: '\
  -d '{
  "password": "",
  "mnemonic": "",
  "walletName": "",
  "isMiner": true
}'
```

## now you are ready to install

1. git clone https://github.com/alephium/mining-pool.git
2. go to the mining-pool folder ```cd mining-pool```
3. edit the config.json file
    > change these lines
     ```javascript
     "addresses": [],                 // 4 addresses(we have 4 groups) to where block rewards are given
    "wallet": {
        "name": "",                  // wallet name
        "password": ""              // wallet password
        
    ```
    be careful - the addresses are user.conf and config.json must match, use the name and password that you used to log into the wallet on the node
4. ```npm install```
5.  ```npm run start```
