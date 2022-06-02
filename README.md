# 18-Blockchain
## How to Launch Testnet: espinosanet
Dependencies needed: <br>
    MyCrypto desktop app <br>
    Go Ethereum Tools
   
   Instructions for setting up these tools can be found <a href="https://github.com/nenitaE/18-Blockchain/blob/main/Instructions/blockchain-install-guide.md">HERE</a>
    <br><br/>

## Once the tools have been installed, perform the following to launch espinosanet:<br>

Open a terminal window and navigate to the blockchain tools folder.<br>
    

    type: ./puppeth
    when prompted for network name specify espinosanet
    when asked what you would like to do, select: 2. Manage existing genesis
    Then select 2. Export genesis configurations
    Hit enter to specify default folder as current folder
    This will add .json file of genesis configuration for espinosanet
    
## How to initialize nodes:
Open a terminal window<br>
Navigate to the blockchain tools folder and type the following commmands:
<br>

./geth --datadir node1 init espinosanet.json<br>
./geth --datadir node2 init espinosanet.json<br>

## How to run the nodes:
* Open 2 separate terminal windows and navigate to the Blockchain tools folder then type the following command in the first window:<br>
./geth --datadir node1 --unlock "00d38278A28483c84b67f5c442FD695b6159Bbb2" --mine --rpc --allow-insecure-unlock<br>
* Once you have node1 running, scroll up to the enode address and copy the whole address including ip address at the end.

* In the second terminal window type the following command making sure to **replace** the information in the "enode://..." with what you copied from node 1:<br>
./geth --datadir node2 --unlock "FAbB864D9737705cd021aD1EF3cBc88edb6751DC" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

## Connecting to espinosanet on MyCrypto
* Open MyCrypto<br>
* Click "change network" in lower left<br>
* select "add custom node" and fill out the requested info:
     <ol>
     <li>node name: espinosanet
     <li>Network: custom
     <li>Network Name: espinosanet
     <li>Currency: ETH
     <li>Chain ID: 777
     <li>URL: http://127.0.0.1:8545<ol/>

## Navigating to the wallet on MyCrypto
    
    click "view&send"
    click "keystore File" and navigate to keystore file for node 1 in Blockchain Tools folder
    enter password: blessed01
## **Congratulations!** You can now send and receive test ether!