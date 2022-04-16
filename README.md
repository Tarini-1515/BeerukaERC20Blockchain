
# Instructions for application execution of token distribution

Deploying the ERC20 contract to an 
Ethereum testnet network, and distributing 5% of the total supply equally between each of the ETH addresses in the file. 
(e.g. if 100 tokens remain, 5 tokens get distributed into the N accounts in the file - 10 
accounts means each get 0.5 tokens) 
• Each distribution to be executed on the Ethereum testnet network



Important links of the projects: 

1. ERC20 contratc address: https://ropsten.etherscan.io/tx/0x372e710462048ca20d474f1fac31af7c34d4dad07bf8e32df4deb5cf682cca8c
2. Token distribution to account1:  https://ropsten.etherscan.io/tx/0x4405f429e4eae3b33f2898fcbf7c7fdab84fbdcbbb5d2c6deb7adab7e15509a8
3. Token distribution to account2: https://ropsten.etherscan.io/tx/0xa058a9c66efb823403ac2ddbc486452d343c728260156fd584741d40328a6c2a
4. Ethereum testnet ETH Address of Token Owner: 0xf0Bf4a27b88Ce3c48779a1A8c58111ae14d71E70

## Tools/ Applications Used

          1. Visual Studio CODE
          2. Remix.IDE
          3. Infura
          4. Metamask
## INDEX

1. Setting up Metamask account and creating 3 accounts
 where Account1 acts as owner account, and Account2 and Account3 act as additional accounts where we transfer 5% of the total tokens
 Metamask link: https://metamask.io/

2. Setting up Infura account
   Infura website link: https://infura.io/dashboard/ethereum/2e3feb5145fd4709849b30f351a89b1d/settings

3. Setting up Visual Studio Code to run Token Distribution Node JS Code
   Visual Studio Code link: https://code.visualstudio.com/

4. Remix.IDE : Here we exicute the ERC20 code and creat the tokens and deploy the contract
   Remix.IDE: https://remix.ethereum.org/#optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.0+commit.c7dfd78e.js

5. Downloading additional modules which require to exicute distribute.js code

6. Running the ERC20 code and deploying the contrat

7. Editing the .env file and connecting the applications to one another to create and distribute the tokens

8. Connecting the metamask and providing the account details to which the token distribution must be taken place

9. Exicuting distribute.js file 

10. Checking the transaction using transaction hash on Etherscan
     Etherscan: https://ropsten.etherscan.io/tx/0xcb9bb60315f6829b6d18d30adca5ee88812760a7997ee8d6560c2dbd39f78ce8
     
## 1. Setting up Metamask Account

1. Downlaod the Metamask extention to the browser. 
2. Manually enter the secret phrase (which can be 12, 14, 16 letter)
3. set up new password for the Account
4. login the metamask Account
5. Create 3 account using "+create account" icon and add etherum text networks
6. In this project we work on Ropsten Test network.
7. Add faucets into Account1 ( which ever you prefer as the onwer account) ETH faucets help into deploying the contract from REMIX.IDE


## 2. Setting up Infura account
** Infura helps in Blockchain applications from testing to Scaled deployment **
1. Open the Infura website and sign up
2. Infura: https://infura.io/dashboard/ethereum/2e3feb5145fd4709849b30f351a89b1d/settings
3. Create new project and name the project 
4. Click on the Project settings
5. select the project Id and copy the hash


## 3. Setting up Visual Studio Code

1. Download Visual Studio Code and deploy the unzip project
2. Here we get 7 files called
     * node_modules
     * .env
     * accounts.js
     * DeployedContract.sol
     * distribute.js
     * package-lock.json
     * package.json

3. We make sure node is installed
4. Open the termial in the left top.
5. change the path to the blockchain project
6. enter node --version , to check if node is installed.
7. if node is not found, we can install using this link: Cryptii.com

## 4. Setting up REMIX.IDE

1. Change the compiler to the required one from the ERC20 code.

2. With the given Solidity code of ERC20, exicute the code by setting up the enviornmnet as Injected web3
 
3. Connect the Metamask account to the Remix IDE by conforming through the Metamask account


##  5. Adding dependent modules to execute distribute.js code

1. Here the additional modules which we need are:
        1. Web3
        2. dotenv
        3. 'ethereumjs-tx
        4. fm
        5. Big-number

2. We download these modules to run the code smoothly.

## 6. Running ERC20 on Remix.IDE

1. now, we are creating tokens and deploying the contract address

2. Select Your contact, as here it is BeerERC20 - Contracts/BeerToken.Solidity

3.  Change the Token name with your unique token name:

       contract BeerERC20 is Context, IERC20, IERC20Metadata {
    mapping(address => uint256) private _balances;

    mapping(address => mapping(address => uint256)) private _allowances;

    uint256 private _totalSupply;

    string private _name;
    string private _symbol;

4. Provide name, symbol, and how many token have to be created into the Metamask account.
                 
    
               constructor() 
        {
        _name = "Beer Token";
        _symbol = "BER";
        
        _mint(msg.sender, 1000000000000000000000000);
    }

5. Exicute the code and copy the Contract address from left corner.

6. We can view the transactions and number of tokens created through Etherscan.
     https://ropsten.etherscan.io/tx/0x372e710462048ca20d474f1fac31af7c34d4dad07bf8e32df4deb5cf682cca8c
## 7. Editing .env file on Visual Studio Code

1.  
    INFURA_TOKEN=2e3feb5145fd4709849b30f351a89b1d
    CONTRACT_ADDRESS=0xE6a5c366C209c1607A89b9E1Ab2c98D3455003f1
    OWNER_ADDRESS=0xf0Bf4a27b88Ce3c48779a1A8c58111ae14d71E70
    SUPER_SECRET_PRIVATE_KEY=4733cb9f1499737931cb471715ac99a188473c8a9ce6be2c70b943c93fe180bf

2. The INFURA_TOKEN is from the Infura Project id

3. We get the CONTRACT_ADDRESS from the Remix.IDE after deploying and executing the ERC20 Code

4. The OWNER_ADDRESS from the  Metamask account

5. Which ever metamask account we have selected, we extract the private key of the same account.


## 8. Token distribution to the mentioned accounts

1. As we have to distribute 5% of the total supply equally between each of the ETH addresses in the file. 
(e.g. if 100 tokens remain, 5 tokens get distributed into the N accounts in the file - 10 
accounts means each get 0.5 tokens) 

2. From the file accounts.txt, we provide the account addresses to the file, to which we would like the token to be distributed

3. Here I have provided 2 of my Metamask accounts, to which I wish 5% of the total tokens is to be distributed.

4.  The accounts I have provided are:

       1. owner account: 0xf0Bf4a27b88Ce3c48779a1A8c58111ae14d71E70
       2. Token distribution account1: 0xc6358f4e2BBbb8928B4a3EFA58d650C5ab5Df7b4
       3. Token distribution account2: 0x3a50fa340C899c6f2609646eb8A4D30A0DAcb0c0

       
## 9. Execute the distribute.js file

1. We have edited all the hashes we reqired and downloded the dependencies too.

2. We excecute the node JS file by the command:
        Node distribute.js

3.  Here the code will be executed and the tokens will be disributed one account after another account.
     

     
PS C:\Users\corne\Downloads\BF_CodeExample\BF_CodeExample> node distribute.js
connected to web3
connected to contract on ropsten

# Token distribution to Account1


distro addresses are: 0xc6358f4e2BBbb8928B4a3EFA58d650C5ab5Df7b4,0x3a50fa340C899c6f2609646eb8A4D30A0DAcb0c0       
symbol is BER
650c5ab5df7b400000000000000000000000000000000000000000000054b40b1f852bda0000029a0582ee7f3b7c89a8f9832f13cc1924a31c140d1331acbbdcf1d23cb04f920fd47a05584b9e17104b87bfa6b44a18d1ec8111d9ddfc31c506a6540fbcf35b3e8ec28
transaction hash: 0x4405f429e4eae3b33f2898fcbf7c7fdab84fbdcbbb5d2c6deb7adab7e15509a8
transaction in block: 12197370



#  Token Distribution to Account2


about to distribute BER, 25000000000000000000000 tokens go to 0x3a50fa340C899c6f2609646eb8A4D30A0DAcb0c0
tx count is 11
signed transaction with super secret private key
about to broadcast transaction0xf8aa0b852e90edd000830f424094e6a5c366c209c1607a89b9e1ab2c98d3455003f180b844a9059cbb0000000000000000000000003a50fa340c899c6f2609646eb8a4d30a0dacb0c000000000000000000000000000000000000000000000054b40b1f852bda000002aa098a8e5ced7843e55348a646246b7ca13a00f4ba3d59eded17926e6ddf67d1be9a0420697dcc20c2bedb6cad5e6802973cd40bd4bf3828fb3bc0a64047cb3a3d026
transaction hash: 0xa058a9c66efb823403ac2ddbc486452d343c728260156fd584741d40328a6c2a
transaction in block: 12197372
## Verifying Transaction Hash on Etherscan

1.  We can verify the Transactions with hash value and block number:
       
2   Token distribution to the first account: 
       
    transaction hash: 0x4405f429e4eae3b33f2898fcbf7c7fdab84fbdcbbb5d2c6deb7adab7e15509a8
    transaction in block: 12197370
      
     Etherscan link: https://ropsten.etherscan.io/tx/0x4405f429e4eae3b33f2898fcbf7c7fdab84fbdcbbb5d2c6deb7adab7e15509a8

3. Token distribution to the second account:

    transaction hash: 0xa058a9c66efb823403ac2ddbc486452d343c728260156fd584741d40328a6c2a
    transaction in block: 12197372

     Etherscan link:  https://ropsten.etherscan.io/tx/0xa058a9c66efb823403ac2ddbc486452d343c728260156fd584741d40328a6c2a



     *****The end***


     
     
     




