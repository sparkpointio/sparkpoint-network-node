# sparkpoint-network-node

These scripts will help you run a node on the SparkChain Network Testnet

## Requirements 
1.a If using physical server (Windows, MacOS, Linux), setup [Docker Desktop](https://docs.docker.com/get-docker/).
1.b If using VPS, setup [Docker Engine](https://docs.docker.com/engine/install/ubuntu/).
2. Ethereum wallet with at least 0.25 ETH (0.1 ETH required for staking, 0.05 ETH Tier 1 Node Key, 0.1 paying for gas)
3. [Node Key](https://sepolia.arbiscan.io/address/0x26B555cF60452cD3456C7f9077Ea341bB58585A7#writeProxyContract)

## Minimum hardware specs (Linux)
1. CPU: 4 Cores
2. RAM: 4 GB
3. Storage: 20 GB

## Node Key
At the moment, there is no front serving website to guide you in purchasing a node key for SparkChain Network Testnet. Please follow the steps below to purchase a node key.

1. Go to [Arbitrum Sepolia Explorer - Node Key Contract](https://sepolia.arbiscan.io/address/0x26B555cF60452cD3456C7f9077Ea341bB58585A7#writeProxyContract)
2. Go to Write as Proxy and Connect to Web3
3. Open 4. buyNodeKey()
3.1 For "payableAmount (ETH)" type in "0.05" (without double quotes)
3.2 For "amount (uint256) type in "1" (without double quotes)
3.3 For "voucher (string) type in "TESTNET" (without double quotes)
4. Then click write, and confirm transaction from your Metamask

## Instructions

Once you've have purchase a [Node Key](https://sepolia.arbiscan.io/address/0x26B555cF60452cD3456C7f9077Ea341bB58585A7#writeProxyContract), please follow the steps below to complete a local deployment of your node.

1. Clone the https://github.com/sparkpointio/sparkpoint-network-node/ repository
2. If using VPS, run sudo chmod 777 config in the base directory of the sparkpoint-network-node repository.
3. Open config/nodeConfig.json file, and replace "PRIVATE KEY" with your own private key used in purchasing the node key
4. If you have a paid Arbitrum Orbit RPC, replace the "https://sepolia-rollup.arbitrum.io/rpc" with your own Arbitrum Sepolia RPC URL, and adjust "node"."inbox-reader" values to fully utilize your RPC speed
5. Run "npm run start" or "docker compose up -d" in the base directory of the sparkpoint-network-node repository. This will launch the node with a public RPC reachable at http 8449
6. Optionally, run "npm run logs" or "docker compose logs -f nitro" in the base directory of the sparkpoint-network-node repository to view the logs of the node