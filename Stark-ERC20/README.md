# ERC20 Basics on StarkNet

In this example, we are going to see how to deploy a simple ERC 20 token contract to  Starknet, and mint some tokens. 

# Getting Started

First clone the git or download the git and unzip it. 

You need to run terminal (on MAC) in the downloaded folder, or open the folder in Virtual Studio Code (windows), and this will be your developing platform.

Mac: To open terminal in the folder, right click folder and select  "New Terminal at Folder"

In the terminal, enter one by one:

pip3 install cairo-lang
python3 -m venv env
source env/bin/activate
pip install cairo-nile

nile init

# Compiling and Deploying

To compile, run the commands:

nile compile

On comliling with the above command, we will see the following messages:

🤖 Compiling all Cairo contracts in the contracts directory
🔨 Compiling contracts/contract.cairo
🔨 Compiling contracts/ERC20_base.cairo
🔨 Compiling contracts/Deploy_ERC20.cairo
✅ Done

Now the contract is compiled, we will deploy it:

Run:

nile deploy Deploy_ERC20 <NAME> <SYMBOL> <SUPPLY> 0 <ADDRESS> --network goerl

Here, Name, Symbol, Supply should be in 'felt' format. To convert a number or string into felt, please use this tool : https://cairo-utils-web.vercel.app
A '0' is placed after Supply, since Supply is a large integer and on converting to felt, it will be a felt array. 
The Address will contain the address to deploy the contract to. This will be your ArgentX wallet address.

Example of correct deploy code:
  
  
nile deploy Deploy_ERC20 1146178124 1146178124 470000000000000000000 0 0x6E113C63B19D65cBEBfC7FeD0E4789FB442Cc352 --network goerl

Once the deploy command is completed, you will see the message:
🚀 Deploying Deploy_ERC20
⏳ ️Deployment of Deploy_ERC20 successfully sent at XXXXXX
🧾 Transaction hash:
📦 Registering XXXXXX

Now, you can go to the registered address on Voyager Goerli, and use Write contract to claim some tokens from the faucet. 
