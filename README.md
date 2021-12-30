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

After succesfully building the code just find config.json file in this repository.
This is just to show you how my json file looks like.
This file is currently set to mine dogecoin in my wallet using cpu and also only 2 
logical cores are used in my case. 
Changes in this file that have to be done depends on your choice and cpu.

You have to generate your own json file to do this follow this procedure:

*STEP 1:* Go to [xmrig wizard](https://xmrig.com/wizard)

*STEP 2:* Click New configuration -> add pool -> select your pool website

`NOTE: if your custom pool website is not listed just click any one of them and proceed.I am also using unminable.com that is also not present there`

*STEP 3:* In backends select CPU

*STEP 4:* In Misc Select Donate (optional). I am using 1% :/ .

*STEP 5:* Tap on result and download the json file

*STEP 6:* Put that json into `xmrig/build` folder

*STEP 7:* 

some instructions regarding variables used in json file:
Add cpu numbers to rx array to allow them for mining.
eg: if you have 2 core 4 threads and you want to do mining with all the cores and threads then
change rx to [0,1,2,3].

*NOTE: you should be aware of using all cores as it can damage cpu significantly.
as a general rule for saftey only use half of them. in my case rx is [2,3].*


