# DeFli-Node
How to run a DeFli Blockchain Node 

### Hardware Requirements  

8-Core CPU
at least 16 GB RAM
an SSD drive with at least 2.5 TB fre 

### Installation

```bash
sudo git clone https://github.com/DeFliTeam/node-create
```
Set ```bash OP_NODE_L1_ETH_RPC``` (in the .env.* file if using docker-compose) please use eth.nownodes.io or eth-sepolia.nownodes.io

Uncomment the line relevant to your network (.env.sepolia) under the 2 env_file keys in docker-compose.yml. 

Configure your Base node settings, including the Testnet Sepolia Settings

```bash
RPC endpoint set to https://rpc-defli-chain-01-jerg8a427n.t.conduit.xyz, 
Explorer set to https://explorerl2new-defli-chain-01-jerg8a427n.t.conduit.xyz 
WS set to wss://rpc-defli-chain-01-jerg8a427n.t.conduit.xyz
```


Run: 

```bash
docker compose up --build
```

You should now be able to curl your Base node: 

```bash
curl -d '{"id":0,"jsonrpc":"2.0","method":"eth_getBlockByNumber","params":["latest",false]}' \
  -H "Content-Type: application/json" http://localhost:8545
```

Persisting Data

By default, the data directory is stored in ${PROJECT_ROOT}/geth-data. You can override this by modifying the value of GETH_HOST_DATA_DIR variable in the .env file.

To load a snapshot you can extract the snapshot into the $GETH_HOST_DATA_DIR folder.







