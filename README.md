<img src="https://github.com/profitviews/bitcoin-wallet/raw/main/assets/images/demystifying-bitcoin-wallets-research-setup.webp" style="width:800px"/>

# Bitcoin Wallets

How to create a Bitcoin wallet.

Manipulating Bitcoin programatically is a remarkably straightforward process - as it should be!  That's the whole promise and genius of Bitcoin, and why it is revolutionary.

To understand this better, read and run [bitcoin-wallet.ipynb](/bitcoin-wallet.ipynb) after setting up your environment.

## Scope and security

This is an **educational demonstration of the mechanics** of Bitcoin key generation, address derivation, Wallet Import Format and transaction signing. It is not a wallet and not a recommendation for holding funds. Specifically:

- It runs on **testnet** by default. Mainnet is an explicit opt-in.
- The private key is stored **encrypted at rest** (scrypt + AES-256-GCM) with owner-only file permissions, existing key files are never overwritten, and key files are git-ignored.
- The private key is **never printed in full**.
- Transactions are **built and signed but not broadcast** unless a flag is set. Broadcasting on mainnet needs a second, separate flag.
- The pure-Python `ecdsa` library is used because it is easy to read, not because it is hardened against side-channel attacks.

Even with these measures, a key held in a file on an internet-connected machine is a hot key with a single point of failure. The notebook ends with a comparison between what it does and production custody practice: HSM or MPC key management, multisig, policy-controlled approvals, hot/warm/cold segregation, tested recovery, monitoring and independent assurance.

## Running it

It was written in Python 3.12.2 (but should be fine in most Python 3 versions).

**To run the code**:

1. Install `git` 
2. Install `jupyter` or `jupyter-lab` - or use [Visual Studio Code](https://code.visualstudio.com/) 
3. Download it with
```shell
git clone git@github.com:profitviews/bitcoin-wallet.git
```
4. `cd bitcoin-wallet`
5. Install dependencies with
```shell
pip install -r requirements.txt
```
6. Launch `bitcoin-wallet.ipynb` as a Jupyter notebook using whichever means you chose above. You'll be prompted for a passphrase to encrypt the generated key.

Any problems, email help@profitview.net or go to [ProfitView](https://profitview.net) and chat to us.

For more cool stuff go to our [home](https://github.com/profitviews).

<a href="https://profitview.net" target="_blank"><img src="https://github.com/profitviews/profitviews/raw/main/assets/images/logo.png" style="width:500px"/></a>
