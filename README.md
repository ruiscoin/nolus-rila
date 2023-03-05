# SnapShot for Nolus Rila testnet. Updated every day at 00:01 UTC (you can run as 'one command'):

```python
sudo systemctl stop nolusd;\
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup;\
rm -rf $HOME/.nolus/data;\
curl -L https://72.44.73.76/snapshot_latest.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus;\
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json;\
sudo systemctl restart nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```
