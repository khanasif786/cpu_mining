# CPU mining made easy
Repository for making CPU mining easier to all.

This Mining Procedure is based on CPU (RandomX algorithm) using xmrig miner. (Ubuntu 20 is used for this tutorial)
### NOTE: GPU mining can also be done but it will be having much lesser speed if xmrig is used.



## Setup:
This setup assumes that you have already installed git. if not use this command:

```
sudo apt-get install git
```

Installing dependencies:

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
This is just to show you how my json file looks like. ( My json is so complex because during mining xmrig writes many default instructions to json
if you are a beginner than follow below procedure and only refer my config.json in case of issues).
This file is currently set to mine dogecoin in my wallet using cpu and also only 2 logical cores are used in my case. 
Changes in this file that have to be done depends on your choice and cpu.

You have to generate your own json file, To do this follow this procedure:

*STEP 1:* Go to [xmrig wizard](https://xmrig.com/wizard).

*STEP 2:* Click New configuration -> add pool -> select your pool website.

`NOTE: if your custom pool website is not listed just click any one of them and proceed. I am also using unminable.com that is also not present there.`

*STEP 3:* In backends select CPU.

*STEP 4:* In Misc Select Donate (optional). I am using 1% :/ .

*STEP 5:* Tap on result and download the json file.

*STEP 6:* Put that json into `xmrig/build` folder.

*STEP 7:* Go to [unminable](https://unmineable.com/coins). select your coin (for eg: i am using DOGE). Go to RandomX and copy the server url
in my case that is "rx.unmineable.com:3333" paste that in url section in your config.json.

*STEP 8:* Copy you wallet address whatever you are using. I am using atomic wallet. than paste that in user section like this `<coin><wallet_address><workerName>`
          Note that worker name can be anything. In my case i am mining dogecoin that's why i pasted `DOGE:DJBDTDjGPaXVSRRzMgZQeKqBR5sVUy6WpG.HelpAsif`
          for example mine looks like this: You can use this and help me out :)) .
          
            "url": "rx.unmineable.com:3333",
            "user": "DOGE:DJBDTDjGPaXVSRRzMgZQeKqBR5sVUy6WpG.HelpAsif"

*STEP 9:* Save the config file. open terminal in that folder(xmrig/build) and run `./xmrig` command.


 ***..............................................................TDAAAAAA..............................................................***
 
you have just started making money.


## Help section
### Some instructions regarding variables used in json file:

### 1. Configuring CPU instances for mining
Add cpu numbers to rx array to allow them for mining.
eg: if you have 2 core 4 threads and you want to do mining with all the cores and threads then
change rx to [0,1,2,3].

***NOTE: you should be aware of using all cores as it can damage cpu significantly.
as a general rule for saftey only use half of them. in my case rx is [2,3].***

### 2. Allowing GPU for mining 
If you want use nvidia just make cuda 'true' in config file. and if you have amd card than make opencl 'true'.

***NOTE: For this you should have installed with respective cuda and opencl drivers for the hardware***



