# Prerequisite

`git clone https://github.com/graphprotocol/graph-node`
`git clone https://github.com/graphprotocol/graph-client`

# GRAPH NODE

Use Docker to run a local graph node and connect it to a blockchain via RPC.

`git clone https://github.com/graphprotocol/graph-node/`

Open docker-compose.yml located in:

`graph-node/docker/docker-compose.yml`

Replace http://host.docker.internal:8545 with your RPC url. The default connects to a local ethereum node.

NOTE: Keep `mainnet`:

Go to graph-node/docker and run

`./setup.sh`

`docker-compose up`

The logs will show the current block head. You can compare it with what’s in the block explorer.

Ref [https://medium.com/coinmonks/deploy-subgraphs-to-any-evm-aaaccc3559f](https://medium.com/coinmonks/deploy-subgraphs-to-any-evm-aaaccc3559f)

# GRAPH CLIENT

Init subgraph

`graph init`

Build subgraph

`graph create generated/sample --node http://127.0.0.1:8020`

Deploy subgraph

`graph deploy --ipfs http://localhost:5001 --node http://localhost:8020 generated/sample ./subgraph.yaml`
