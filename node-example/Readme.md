# Run a BANK Validator
## Setting up a node
1. Git clone https://github.com/bankcex/BANKNetwork.git

2. Copy source form node-example to root folder
```
cp -r BANKNetwork/node-example/BANK  /root/
```
3. Create an Account

```
cd /root/BANK
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
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

    To stake BANK coin, all you should do is sending your BANK coin to the BANK Consensus contract address over the BANK network from the validator address.
    The BANK Consensus contract address: 0x72e46221d340d2Fa573cdba6D4B69610ff683079
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BANK and send the BANK coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BANK/nodes/validator/keys/BANK/UTC--xxxx
    /BANK/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
