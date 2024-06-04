<h2>Nolus latest snapshot</h2>

<h3>Stop Nolus service and copy validator</h3>

```
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
```

<h3>Donwload latest snapshot</h3>

```
wget http://85.190.246.119/nolus/nolus-rila_2023-03-03.tar | tar -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

<h3>Start nolusd and check logs</h3>

```
sudo systemctl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```
