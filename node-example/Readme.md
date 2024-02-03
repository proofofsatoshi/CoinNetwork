# Run a SND Validator
## Setting up a node
1. Git clone https://github.com/proofofsatoshi/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/SND  /root/
```
3. Create an Account

```
cd /root/SND
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake SND coin, all you should do is sending your SND coin to the SND Consensus contract address over the SND network from the validator address.
    The SND Consensus contract address: 0xa9C73c31851EbAEC671aa65EEE5368AEF5075F99
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to SND and send the SND coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /SND/nodes/validator/keys/SND/UTC--xxxx
    /SND/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
