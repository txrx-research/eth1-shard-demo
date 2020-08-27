# Eth1 Shard Demo

### Prerequisites
- Install [Docker Compose](https://docs.docker.com/compose/install/)

### Run Eth1 Shard Demo
```shell
git clone git@github.com:txrx-research/eth1-shard-demo.git
cd eth1-shard-demo

docker-compose up
```

### Setup your local wallet
You may connect your wallet (e.g. [Metamask](https://metamask.io)) to the Demo Network. 

When docker compose is up there is a gateway node mapped on the local host with JSON-RPC endpoint accessible at `http://localhost:8545` as usual. To send transactions successfully you will have to set `chainId = 20202` for the network configuration.

Once the network is set up, use the following private key to redeem an enormous amout of premined ETH dedicated for your needs:
```
0x0000000000000000000000000000000000000000000000000000000000000001
```

### Demo genesis.json
Here is the full genesis.json file used to bootstrap Eth1 nodes:
```json
{ 
	"config": { 
		"chainId": 20202, 
		"homesteadBlock": 0, 
		"eip150Block": 0, 
		"eip155Block": 0, 
		"eip158Block": 0, 
		"byzantiumBlock": 0, 
		"constantinopleBlock": 0, 
		"petersburgBlock": 0, 
		"istanbulBlock": 0
	}, 
	"alloc": {
  	"0x7E5F4552091A69125d5DfCb7b8C2659029395Bdf": {
    	"balance": "1000000000000000000000000000" 
  	}
	}, 
	"coinbase": "0x0000000000000000000000000000000000000000", 
	"difficulty": "0x20000", 
	"extraData": "", 
	"gasLimit": "0x2fefd8", 
	"nonce": "0x000000000020202", 
	"mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000", 
	"parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000", 
	"timestamp": "0x00"
}
```

### Demonstration of value transfer

[![Demo](https://img.youtube.com/vi/ghIehI02QJ8/0.jpg)](https://www.youtube.com/watch?v=ghIehI02QJ8)

### References
- This setup is based on the Eth1 Shard Simulation:
  - https://github.com/txrx-research/teku/tree/phase1/phase1/src/main/kotlin/tech/pegasys/teku/phase1#eth1-shard-simulation
- Catalyst (eth1-engine):
  - https://github.com/gballet/go-ethereum/tree/eth1-eth2-proto1
- Eth2-client:
  - https://github.com/txrx-research/teku/tree/phase1/phase1/src/main/kotlin/tech/pegasys/teku/phase1
