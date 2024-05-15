# Initia-Node

Sistemi Güncelleyelim
```
sudo apt update && sudo apt install curl git jq build-essential gcc unzip wget lz4 -y
```

GO Yükleyelim

```
cd $HOME && \
ver="1.22.0" && \
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz" && \
sudo rm -rf /usr/local/go && \
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz" && \
rm "go$ver.linux-amd64.tar.gz" && \
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> ~/.bash_profile && \
source ~/.bash_profile && \
go version
```

Binary

```
git clone https://github.com/initia-labs/initia.git
cd initia
git checkout v0.2.12
make install
```

Değişkenleri Ayarlayalım (NODE_ADI ve CUZDAN_ADI Bölümünü İstediğiniz Biçimde Değiştirin)

```
echo 'export MONIKER="NODE_ADI"' >> ~/.bash_profile
echo 'export CHAIN_ID="initiation-1"' >> ~/.bash_profile
echo 'export WALLET_NAME="CUZDAN_ADI"' >> ~/.bash_profile
source $HOME/.bash_profile
```

Node'u Başlatalım

```
cd $HOME
initiad init $MONIKER --chain-id $CHAIN_ID
```

Genesis Dosyasını İndirelim

```
wget https://initia.s3.ap-southeast-1.amazonaws.com/initiation-1/genesis.json -O $HOME/.initia/config/genesis.json
```

Seed ve Peerları config.toml Dosyasına Ekliyoruz

```
PEERS="a63a6f6eae66b5dce57f5c568cdb0a79923a4e18@peer-initia-testnet.trusted-point.com:26628,439fe02b731d7f99a62e44ac5b2e1b02353ca631@38.242.251.179:39656,4db605b6f399a173cfc30e843a7d6a10cd3222a3@158.220.86.6:17956,fd14410d3d6ba362a20d47c02e077da86017cadf@65.21.244.157:17956,a8638b4701f2d11e9269dfd4c2ed0509bd7b12d9@194.163.191.117:39656,0ce5a28686d961d0f1315069c03adb74c6fccc80@37.60.244.91:24556,de31968f3b35942b5a1123998ff0c4ebd3c3aae5@88.99.193.146:26656,f396faca04598721481e714dcb0e3c8ed05a406c@49.12.209.114:15656,fd06e3e5f03b31757ee2ce78d0bf85bb1c71a2d9@65.109.166.136:26656,0d5b90a3b620a7e602f099eb4da99fc03995874e@165.22.245.86:17956,028999a1696b45863ff84df12ebf2aebc5d40c2d@37.27.48.77:26656,7033bed7fa79360e24d5d0cf2f5fee8a683766a9@154.26.129.223:17956,1376a7400ee5400e226ebab384ad89de408163dc@62.171.179.87:13656,23251217584bc066c8027cc735ca1b2893896178@185.197.251.195:17956,277ae7258c9ac789262ef125cfdbf1c02958510a@37.27.71.199:22656,32fece76b6d278672fb73059764f5d6f77086f3a@148.251.3.125:19656,c612c1c6ad4a59fb62a31428782921591e8bb684@42.117.19.109:10656,fa69efe26762f987a1e1eaf4ea053b35380838dc@80.65.211.232:17956,0d6437ca9242b5878f6c784b88e918ba12f12c08@89.58.63.240:53456,f24e92c2b15ea8f212ec63ebae5451d8fcc7da8b@81.0.248.152:39656,ba053d26fe5c30842ddcc2c34c9893d78204ced0@157.90.154.36:17956,32f59b799e6e840fb47b363ba59e45c3519b3a5f@136.243.104.103:24556,5c2a752c9b1952dbed075c56c600c3a79b58c395@195.3.221.9:26686,862d16bec51e4e2751b00605416df94b7440b7f3@49.13.147.156:39656,1813a8de79d48674f184553800122f7bf794cd57@213.199.52.16:26656,a633694e4f10060023b3c8319ae130fa927f706b@207.180.251.85:17956,22c876f711032026c54d2ccfe81cb2cfe1ec9ac1@37.60.243.170:26656,15a9693fbcdd9d8aea48030be3b520b1d69e8d66@193.34.213.228:14656,98f0f8e9209aa0a8abad39b94b0d2663a3be24ec@95.216.70.202:26656,c2a36ef8b4aaef3acc7d7cbfd77d10cf4cedaa3d@77.237.235.205:53456,8999ddce339185140913a64c623d0cb2a0e104f5@185.202.223.117:17956,04538a79c786a781345533aecff034379023e661@65.108.126.173:53456,670d532665a0f93ccbba6d132109c207301d6353@194.163.170.113:17956,4d98be9bf94c8ec06f7bbd96a9b4de507d2035b8@37.60.252.43:39656,7d097908682ef4f4e168f2136da2612ec43da27c@85.215.181.21:26656,7f194243f4d9ffbe15412fc5a11eec5c914c9300@167.86.114.207:17956,a3f2bd6fcf79eec06a5f384b3edaf1fe6e4ac9ce@82.208.22.54:17956,6dbb770a4b19f685c1cfe3a16738022eb9ca12e2@101.44.82.135:53456,ef4a25ea7000773cb6094dd5d905686ab7426541@158.220.122.90:14656,2bc4ca9a821b56e5786378a4167c57ef6e0d174f@167.235.200.43:17956,e3ee807b6f4e5a5f76e3e3b73da23a07488f01fb@5.75.170.27:17956,9228bbd89be619dd943e44633585c1657051a7d0@173.212.193.103:17956,cbba1ec1e228e01b31d22864c36fb7039088a5aa@194.163.152.41:53456,ae241bcfd5fffef3173c5bd4c72b0b384db5db88@49.13.213.52:26656" && \
sed -i \
    -e "s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" \
    "$HOME/.initia/config/config.toml"
```

Gas Price Ayarlıyoruz

```
sed -i -e "s/^minimum-gas-prices *=.*/minimum-gas-prices = \"0.15uinit,0.01uusdc\"/" $HOME/.initia/config/app.toml
```

Pruning Ayarları

```
sed -i \
    -e "s/^pruning *=.*/pruning = \"custom\"/" \
    -e "s/^pruning-keep-recent *=.*/pruning-keep-recent = \"100\"/" \
    -e "s/^pruning-interval *=.*/pruning-interval = \"10\"/" \
    "$HOME/.initia/config/app.toml"
```

Servis Dosyası Oluşturalım

```
sudo tee /etc/systemd/system/initiad.service > /dev/null <<EOF
[Unit]
Description=initia node
After=network-online.target

[Service]
User=$USER
ExecStart=$(which initiad) start
Restart=on-failure
RestartSec=10
LimitNOFILE=10000

[Install]
WantedBy=multi-user.target
EOF
```

Sistem Konfigürasyonları

```
sudo systemctl daemon-reload
sudo systemctl enable initiad 
sudo systemctl start initiad
```

Logları Başlatalım

```
sudo journalctl -u initiad -f -o cat
```

Loglar akmaya başladığında CTRL+C yapıp çıkıyoruz ve aşağıdaki kodla peerların eşleşip eşleşmediğini kontrol ediyoruz. Eşleştiyse false çıktısı almamız lazım.

```
initiad status 2>&1 | jq .sync_info
```

![image](https://github.com/mcyucel/Initia-Node/assets/106594298/dd263833-a924-4a67-8cd5-20ac6f78253d)


latest_blok_height https://scan.testnet.initia.xyz/initiation-1 adresindekine varınca false çıktısı verecektir. Ara ara kontrol edeceğiz uzun sürebilir.

False olduktan sonra cüzdan oluşturacağız. Bir keplr cüzdanınız varsa import etmek için aşağıdaki kodu girdikten sonra 12 veya 24 kelimeli seed'leri gireceksiniz

```
initiad keys add wallet --recover
```

Yeni bir Keplr cüzdanı açmak istiyorsanız aşağıdaki kodu girin. Size vereceği 24 kelimeli seed'i kaydedin. Tarayıcıya Keplr cüzdan indirip bu seedler ile cüzdanı import edin.

```
initiad keys add wallet
```

Keplr cüzdanımıza seedleri import ettiysek https://faucet.testnet.initia.xyz/ sitesine cüzdan adresimizi girip faucettan test token alıyoruz.

Validator Kuralım

Web site ve mail adresi kısmını düzenleyin

```
initiad tx mstaking create-validator \
  --amount=10000000uinit \
  --pubkey=$(initiad tendermint show-validator) \
  --moniker=$MONIKER \
  --chain-id=$CHAIN_ID \
  --website="Twitter linkinizi girebilirsiniz" \
  --details="jcc" \
  --security-contact="Mail adresiniz" \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.01" \
  --from=$WALLET_NAME \
  --gas=auto \
  --gas-adjustment=1.4 \
  --gas-prices 0.15uinit \
  -y
```

WinSCP veya benzeri bir program ile sunucunuza bağlanıp priv_validator_key.json dosyasını bilgisayarınıza kaydetmeniz yararınıza olur.
