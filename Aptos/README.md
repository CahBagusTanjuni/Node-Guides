<p style="font-size:14px" align="right">
<a href="https://t.me/BeritaCryptoo" target="_blank">Join our telegram <img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
<a href="https://twitter.com/BeritaCryptoo" target="_blank">Join our twitter <img src="https://user-images.githubusercontent.com/108946833/184274157-08210464-fa03-493d-b01c-2420c67a524f.jpg" width="30"/></a>
</p>

<p align="center">
  <img width="100" height="auto" src="https://user-images.githubusercontent.com/50621007/165930080-4f541b46-1ae3-461c-acc9-de72d7ab93b7.png">
</p>

## Perangkat Keras

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | 8 cores (Intel Xeon Skylake or newer) |
| RAM | 32GB RAM  |
| Penyimpanan  | 300GB |

## Perangkat Lunak

|Komponen | Persyaratan Minimum |
| ------------ | ------------ |
| OS | Ubuntu 20.04 | 

# Pendaftaran Aptos AIT3
> https://aptoslabs.com/incentivized-testnet
## Buat Wallet di Petra
- Instal ekstensi Petra (Aptos Wallet)
> https://github.com/aptos-labs/aptos-core/releases/tag/wallet-v0.1.7
- Extract file yang sudah di download
- Buka jendela Chrome dan navigasikan ke Ekstensi menggunakan salah satu metode di bawah ini:
   - Di pojok kanan atas jendela browser, klik tiga titik vertikal, lalu Alat lainnya, lalu Ekstensi, atau
   - Pada tab baru atau jendela ketik chrome://extensions di bidang URL dan tekan kembali.
- Aktifkan mode Pengembang di kanan atas halaman Ekstensi.
- Klik Load unpacked di kiri atas, dan arahkan ke folder tempat Anda baru saja membuka ritsleting rilis Wallet yang diunduh.

## Install Aptos Validator 
Gunakan skrip di bawah ini untuk instalasi cepat
```console
wget -qO validator.sh https://raw.githubusercontent.com/xsons/TestnetNode/main/Aptos/validator.sh && chmod +x validator.sh && ./validator.sh
```
Ketika instalasi sudah selesai, silahkan muat variable ke dalam sistem 
```console
source $HOME/.bash_profile
```
## Aktifkan Port
```console
apt install ufw -y
ufw allow ssh && ufw allow https && ufw allow http && ufw allow 6180 && ufw allow 80 && ufw allow 9101 && ufw allow 6181 && ufw allow 6182 && ufw allow 8080 && ufw allow 9103
ufw enable
```
## Cek Kesehatan Node
- Buka https://ait.aptos-node.info/ dan rubah ke v1 
- Masukan IP VPS
- Maka kalian akan melihat seperti ini

![Screenshot_64](https://user-images.githubusercontent.com/108946833/185759982-7dc47140-603f-4258-aa43-b5c77f4148be.png)

### Untuk cek log
```console
docker logs -f testnet-validator-1 --tail 50
```
### Setelah penginstalan kalian harus daftar AIT3
> https://aptoslabs.com/it3

Berikan data yang diminta, Untuk `CONSENSUS KEY`, `CONSENSUS POP`, `ACCOUNT KEY`, dan `VALIDATOR NETWORK KEY`, kalian bisa menemukan nya di `/root/testnet/keys/public-keys.yaml`, atau bisa menggunakan cara ini:

```console
cat ~/$WORKSPACE/keys/public-keys.yaml
```
- OWNNER KEY: Dari wallet Petra `Settings -> Credentials` 

![Screenshot_62](https://user-images.githubusercontent.com/108946833/185756834-8613b9da-a7ec-408a-9c0c-184e82e0f337.png)

## Hapus Aptos
Sebelum menghapus aptos, pastikan kalian sudah membackup!!
```console
cd ~/$WORKSPACE && docker-compose down; cd
rm ~/$WORKSPACE -rf
docker volume rm aptos-validator
unset NODENAME
```
