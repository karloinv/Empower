##  CLI testing

Tx HASH transactions submit in this <small>form(https://docs.google.com/forms/d/e/1FAIpQLScmjUZ_VfJ0AgwdI6hl7gp1Ce8UPGe8t28YoMjgN-6FpISvTw/viewform?usp=send_form)
After sending the transactions, check its success in explorers. Here are some of them:
* https://empower.explorers.guru/
* https://explorer.stavr.tech/empower
***
##### Check info node
```python
empowerd status 2>&1 | jq .NodeInfo
```
##### Check synchronization
```python
empowerd status 2>&1 | jq .SyncInfo
```
##### Check logs
```python
journalctl -u empowerd -f -o cat
```
##### Check balance
```python
empowerd q bank balances <empower14gn80ue...>
```
##### Voting
```python
empowerd tx gov vote <PROPOSAL_ID> <yes|no> --from $WALLET --gas-prices 0.1umpwr --gas-adjustment 1.5 --gas auto -y
```
##### Unjail
```python
empower tx slashing unjail --from $WALLET --gas-prices 0.1umpwr --gas-adjustment 1.5 --gas auto -y
```
##### Delegate tokens
```python
empowerd tx staking delegate $VALOPER <AMOUNT>umpwr--from $WALLET --gas-prices 0.1umpwr --gas-adjustment 1.5 --gas auto -y
```
##### Redelegate tokens
```python
empowerd tx staking redelegate $VALOPER $ANOTHER VALOPER <AMOUNT>umpwr --from $WALLET --chain-id circulus-1 --gas-prices 0.1umpwr --gas-adjustment 1.5 --gas auto -y 
```

