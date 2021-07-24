# 18-Blockchain
## How to Launch Testnet: espinosanet
Dependencies needed
    MyCrypto desktop app
    Go Ethereum Tools
    [Click here for instructions on setting up these tools.](https://unchar.bootcampcontent.com/The-Coding-Bootcamp/uncc-virt-fin-pt-02-2021-u-c/-/blob/master/lesson-plans/18-Blockchain/Supplemental/blockchain-install-guide.md)

Once tools have been installed perform the following to launch espinosanet:
Open a terminal window and navigate to blockchain tools folder
    type: ./puppeth
    when prompted for network name specify espinosanet
    when asked what you would like to do, select: 2. Manage existing genesis
    Then select 2. Export genesis configurations
    Hit enter to specify default folder as current folder
    This will add .json file of genesis configuration for espinosanet
## How to initialize nodes:
Open a terminal windows
Navigate to the blockchain tools folder and type the following commmands:

./geth --datadir node1 init espinosanet.json
./geth --datadir node2 init espinosanet.json

## How to run the nodes:
Open 2 separate terminal windows and navigate to Blockchain tools folder then type the following command in the first window:
./geth --datadir node1 --unlock "00d38278A28483c84b67f5c442FD695b6159Bbb2" --mine --rpc --allow-insecure-unlock
Once you have node1 running scroll up to the enode address and copy the whole address including ipaddress at the end.

In second terminal window type the following command.  Be sure to replace the information in the "enode://..." with what you copied from node 1:
./geth --datadir node2 --unlock "FAbB864D9737705cd021aD1EF3cBc88edb6751DC" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

## Connecting to espinosanet on MyCrypto
click "change network" in lower left
select "add custom node" and fill out requested info:
     node name: espinosanet
     Network: custom
     Network Name: espinosanet
     Currency: ETH
     Chain ID: 777
     URL: http://127.0.0.1:8545

## Navigating to wallet on MyCrypto
click "view&send"
click "keystore File" and navigate to keystore file for node 1 in Blockchain Tools folder
enter password: blessed01
you can now send and receive test ether