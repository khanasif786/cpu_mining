# cpu mining made easy
Repository for making CPU mining easier to all.

This Mining Procedure is based on CPU (RandomX algorithm) using xmrig miner.
### NOTE: GPU mining can also be done but it will be having much lesser speed if xmrig is used.

## setup:
This setup assumes that you have already installed git. if not use this command:

```
sudo apt-get install git
```

Istalling dependencies:

```
sudo apt-get install build-essential cmake libuv1-dev libssl-dev libhwloc-dev
```

Clone the xmrig wherever you want:

```
git clone https://github.com/xmrig/xmrig.git
```

Building the code:

```
mkdir xmrig/build && cd xmrig/build
cmake ..
make -j$(nproc)
```
