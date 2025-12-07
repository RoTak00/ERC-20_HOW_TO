# How to


Before starting, you need to install [foundry](https://getfoundry.sh/).

Once the installation process is complete, create your project with foundry running the following command

```bash
$ forge init <PROJECT_NAME>
```


The next step is to clone this repository. and grab the code of the smart contract  `ERC-20.sol`

```bash
$ git clone https://github.com/Ansijax/myToken
```

Once cloned the repository move the  `ERC-20.sol` smart contract in the `src` folder 

Inside the `src` directory you will find the contract `ERC-20.sol`

Modify the contract, inserting:

-the name of the token
-the symbols
-the decimals
also, update the class name of the contract in order to match the name of your token


To verify that everything works correctly, compile the Solidity code with:

```bash
$ forge build
```


We will deploy out token in the Sepolia Testnet Netowork.

Of course to deploy the smart contract you need to have some Ether, a private key and hence an address.

You can create your keypair using the [MetaMask](https://metamask.io/) wallet. It is a browser extension.
Please pay attention that you have to enable [testnet network](https://support.metamask.io/it/configure/networks/how-to-view-testnets-in-metamask/) to use it later on Sepolia.

Once create your address, you can grab some ETH from here:
- mining: [https://sepolia-faucet.pk910.de/](https://sepolia-faucet.pk910.de/)
or from other faucet.


Then you can deploy a smart contract:

```bash
$ forge create src/<CONTRACT_FILE_NAME>:<CONTRACT_CLASS_NAME> --rpc-url https://ethereum-sepolia-rpc.publicnode.com --private-key <YOUR_PRIVATE_KEY> --broadcast --constructor-args <INSERT HERE A NUMBER TO DEFINE YOUR TOTAL SUPPLY>
```

You can retrieve your private key from MetaMask.

If the dolployment ends well, the tool will show you among the other information the address of your token.

Now, verify the code of your smart contract on Etherscan explorer.

```bash
$ forge verify-contract -rpc-url https://ethereum-sepolia-rpc.publicnode.com 
    -etherscan-api-key <ETHERSCAN_API_KEY>
    <TOKEN_ADDRESS>
    src/<CONTRACT_FILE_NAME>:<CONTRACT_CLASS_NAME>
```

To obtain an Etherscan API key, create an account [here](https://etherscan.io/) and generate the key from your profile.

At this point, you will be able to view your smart contract on [Etherscan Sepolia](https://sepolia.etherscan.io/)