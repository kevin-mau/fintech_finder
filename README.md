# Fintech Finder Application
 
---
### Using Python and Steamlit we build an application that its customers can use to find fintech professionals from among a list of candidates, hire them, and pay them.  We integrate the Ethereum blockchain network into the application in order to enable our customers to instantly pay the fintech professionals whom they hire with cryptocurrency.

### Included in this repository are two Python files.  The first file is called `fintech_finder.py`.  It contains the code associated with the web interface of the application.  The code included in this file is compatible with the Streamlit library.  The second file is called `crypto_wallet.py`.  This file contains the Ethereum transaction functions.  By using import statements, we integrate the `crypto_wallet.py` Python script into the Fintech Finder interface program that is found in the `fintech_finder.py` file.  Integrating these two files allows us automate the tasks associated with generating a digital wallet, accessing Ethereum account balances, and signing and sending transactions via [Ethereum’s Kovan](https://kovan.etherscan.io/) testnet.

---
## Installation Guide

You will need to install streamlit to your environment to run this application:

```python
  pip install streamlit
```

You will also need to create a `.env` file in your repository.  
Add your mnemonic seed phrase and your Infura project id to the `SAMPLE.env` file.
When the information has been added, rename the file `.env`.

## Technologies:

This application utilizes python 3.7 along with the below imports:

```python
  import streamlit as st
  from dataclasses import dataclass
  from typing import Any, List
  
  import os
  import requests
  from dotenv import load_dotenv
  load_dotenv()
  from bip44 import Wallet
  from web3 import Account
  from web3.auto.infura.kovan import w3
  from web3 import middleware
  from web3.gas_strategies.time_based import medium_gas_price_strategy
```
---
## Instructions:

Navigate to the location of the cloned repository on your local machine using the command line interface.  Run the Streamlit application by using this command: 

`streamlit run fintech_finder.py` 

On the resulting webpage, select a candidate that you would like to hire from the appropriate drop-down menu. Then, enter the number of hours that you would like to hire them 
for.  Click the Send Transaction button to sign and send the transaction with your Ethereum account information. If the transaction is successfully communicated to the Ethereum 
Kovan testnet, validated, and added to a block, a resulting transaction hash code will be written to the Streamlit application sidebar.
The account balance, history, and transaction details can be viewed at [Kovan's Etherscan](https://kovan.etherscan.io/) website.

---
## FinTech Finder - Streamlit Application Demonstration:
![demo](https://user-images.githubusercontent.com/85687829/140622709-b7b75593-ab1b-49a9-a093-f3fe5891f4d9.gif)

## Screenshot of The Hirer's (My) Address Balance and History on Etherscan BEFORE the Transaction:
![before](https://user-images.githubusercontent.com/85687829/140622746-7002f3cf-a272-472d-a9eb-5ab7cc393019.png)

## Screenshot of the Transaction Details on Etherscan:
![transaction](https://user-images.githubusercontent.com/85687829/140622770-b7dd05bf-fc3f-4a78-9a52-370bde0494f6.png)

## Screenshot of The Hiree's (the Recipient's) Address Balance and History on Etherscan:
![recipient](https://user-images.githubusercontent.com/85687829/140622801-28cffc7b-a37e-41a5-821c-2e2b9b29e840.png)

## Screenshot of The Hirer's (My) Address Balance and History on Etherscan AFTER the Transaction Has Completed:
![after](https://user-images.githubusercontent.com/85687829/140622806-1c83a675-0f59-4468-8a55-3180a3508296.png)


---

## Contributors

kevin-mau

---

## License

MIT
