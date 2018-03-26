This is the reference code for [Worktips](https://worktips.info) cryptocurrency.

* Official homepage: [Worktips](http://worktips.info)
* Official repository: [Worktips GitHub](https://github.com/Vordas/Worktips-v2)
* Official Announcement thread: [Worktips BitcoinTalk](https://bitcointalk.org/index.php?topic=3086019.0)
* Official Discord: [Worktips Discord](https://discord.gg/UmZExyz)
* Official Facebook: [Worktips Facebook](https://www.facebook.com/worktipscoin)
* Official Twitter: [Worktips Twitter](https://twitter.com/Worktipscoin)
* Official Telegram: [Worktips Telegram](https://t.me/worktips)
* Official Whitepaper: [Worktips Whitepaper](http://worktips.info/whitepaper_worktips.zip)


## Worktips Cryptocurrency

Worktips [WTIP] is a CryptoNight POW algorithm based coin with a total supply of 184,467,440,735 coins. Fast transactions & privacy make this coin a perfect cryptocurrency for rewarding your workers, co-workers, colleagues and family for a job well done.

- Algorithm: CryptoNight
- Max. supply: 184,467,440,735.0
- CryptoNote name: worktips
- Decimal points: 8
- Block time: 120
- Ticker: WTIP
- Emission speed factor: 18
- P2P port: 17239
- RPC port: 18238

Running a full node helps the Worktips network so please consider compiling the client and running it as a node.


## How to compile


### Compile on Windows 7/10 (64 bit)

**1. Fork the coin**

1. Create an account on [GitHub.com](github.com) or log in to an existing one
2. Fork [Worktips repository](https://github.com/Vordas/Worktips-v2) or/and download it

**2. Install dependencies**

Recommended: Microsoft Visual Studio 14 2015, CMake 2.8.6 or later, and Boost 1.55 or later. 

You may download them from:
- http://www.microsoft.com/
- http://www.cmake.org/
- http://www.boost.org/


**3. BOOST (troubleshooting)**

Navigate your browser to: https://sourceforge.net/projects/boost/files/boost-binaries/1.65.0/ and download the boost libraries 1.6.5 for your Visual Studio version. For this tutorial we are using Microsoft Visual Studio 14 2015 on 64 bit Windows platform.

Download and install Boost 1.65 for MSVC 14 (64 bit): https://sourceforge.net/projects/boost/files/boost-binaries/1.65.0/boost_1_65_0-msvc-14.0-64.exe/download

Set your Windows environment variable _BOOST_ROOT_ to _C:\local\boost_1_65_0' where C: can be case specific and need to be adjusted to your own hard drive letter_.


**4. Configure and generate the project files**

- start CMake GUI and navigate to the repository folder using the field _Where is the source code:_
- in the field _Where to build the binaries:_ specify the build folder location
- click the _Configure_ button to start the configuration
- select _Visual Studio 14 2015 Win64_ option.
- click the _Finish_ button to run the configuration
- after the configuration is done, click the _Generate_ button to generate your project files
- after successfull generation click the button _Open project_ to start building the binaries

**5. Build**

- CMake GUI will open the project in the Microsoft Visual Studio you selected for the configuration
- wait for the Microsoft Visual Studio to scan and prepare all of the files for the project
- the scan is finished when the message _Ready_ appears
- click the _Build_ button from the main menu
- your binaries are located in either the `src/release` or the `src/debug` sub folders depending on your MSVC configuration


### Compile on Linux Ubuntu 14

**1. Install dependencies**

- run an update

``
sudo apt-get update
``

- get all dependencies

``
sudo apt-get install -y build-essential python-dev git cmake libboost1.55-all-dev  libgflags-dev libsnappy-dev zlib1g-dev libbz2-dev libgflags-dev libgflags2  gcc-4.8 g++-4.8
``

**2. Install RocksDB database (long compilation)**

``
git clone https://github.com/facebook/rocksdb.git
``

``
cd rocksdb
``

``
make all
``

**3. Get the coin**

``
cd
``

``
git clone https://github.com/Vordas/Worktips-v2.git worktips
``

**4. CHMOD**

- navigate to:

``
cd worktips/external/rocksdb/build_tools
``

- execute the following commands:

``
chmod +x build_detect_platform
``

``
chmod +x version.sh
``

**5. Build executables (long compilation)**

- Navigate back to repo folder 

``
cd
``

``
cd worktips
``

- Export flags

``
export CXXFLAGS="-std=gnu++11"
``

- Make/Build

``
make
``

_Your executables will be located in `build/release/src` folder._

### Compile on Linux Ubuntu 16

**1. Install dependencies**

- run an update

``
sudo apt-get update
``

- get all dependencies

``
sudo apt-get -y install build-essential python-dev gcc-4.9 g++-4.9 git cmake libboost1.58-all-dev librocksdb-dev
``

**2. Get the coin**

``
git clone https://github.com/Vordas/Worktips-v2.git worktips
``

**3. CHMOD**

- navigate to:

``
cd worktips/external/rocksdb/build_tools
``

- execute the following commands:

``
chmod +x build_detect_platform
``

``
chmod +x version.sh
``

**4. Build executables**

- Navigate back to repo folder 

``
cd
``

``
cd worktips
``

- Export flags

``
export CXXFLAGS="-std=gnu++11"
``

- Make/Build

``
make
``

_Your executables will be located in `build/release/src` folder._


**5. BOOST (troubleshooting)**

**_Warning!_ The following procedure will uninstall your existing boost version and install the minimum version needed to compile successfully.**

- _UNINSTALL_ your active boost version 

``
sudo apt-get remove libboost-dev
``

``
sudo apt-get remove libboost-all-dev
``

``
sudo apt-get autoremove libboost-all-dev
``

- Install BOOST 1.55 on Linux Ubuntu 14

``
sudo apt-get install libboost1.55-all-dev
``

or

- Install BOOST 1.58 on Linux Ubuntu 16

``
sudo apt-get install libboost-dev
``

``
sudo apt-get install libboost-all-dev
``

- Verify installed Boost version

``
dpkg -s libboost-dev | grep Version
``

or


``
cat /usr/include/boost/version.hpp | grep “BOOST_LIB_VERSION”
``

### Run the node

Navigate to folder with executables 

``
cd worktips/build/release/src
``

Start the client/daemon 

``
./worktipsd
``


### Client/daemon command line options

- A name of log file that you want to use for logging.

``
--log-file
``

- Level of logging. Default is 1.

``
--log-level
``

- Disable daemon console commands.

``
--no-console
``


- Used to deploy test nets. Checkpoints and hardcoded seeds are ignored, network id is –data-dir flag. The wallet must be launched with –testnet flag.

``
--testnet
``

- Specify ip to bind rpc server.

``
--rpc-bind-ip
``

- Specify port to bind rpc server.

``
--rpc-bind-port
``

- Interface for p2p network protocol.

``
--p2p-bind-ip
``

- Port for p2p network protocol.

``
--p2p-bind-port
``

- External port for p2p network protocol (if port forwarding used with NAT).

``
--p2p-external-port
``

- Manually add peer to local peerlist

``
--add-peer
``

 
- Specify list of peers to connect to and attempt to keep the connection open.

``
--add-priority-node
``
 
- Specify list of peers to connect to only. If this option is given the options add-priority-node and seed-node are ignored.

``
--add-exclusive-node
``
 
- Connect to a node to retrieve peer addresses, and disconnect.

``
--seed-node
``
 
- Do not announce yourself as peerlist candidate.

``
--hide-my-port
``
 
- Specify file for extra messages to include into coinbase transactions.

``
--extra-messages-file
``
 
- Enable blockchain indexes.

``
--enable-blockchain-indexes
``

Full list of command line options can be found here: 
http://forknote.net/documentation/daemon/


### Useful examples

**Start the daemon in RPC mode on Linux**

``
./worktipsd --rpc-bind-port=18238
``

**Start the wallet in RPC mode on Linux**

``
./simplewallet --wallet-file YOURWALLETNAME --password YOURWALLETPASSWORD --rpc-bind-port 8082  --daemon-port 18238
``

**Reset the wallet in RPC mode on Linux**

``
./simplewallet --command reset --wallet-file YOURWALLETNAME --password YOURWALLETPASSWORD
``

**Start the daemon in exclusive node mode**

``
./worktipsd --add-exclusive-node=45.76.61.98:17239
``

**Start the daemon with bind ports and a specific seed node**

``
./worktipsd  --rpc-bind-port=18238 --p2p-bind-port=17239 seed-node=45.76.61.98:17239
``

**Deleting the blockchain folder (for clean re-sync)**

- Linux
``
sudo rm -rf ~/.worktips/
``
- Windows: 
navigate to your user folder. Find the appData folder. Open the 'appData' folder and find the folder 'roaming' inside. Inside the 'roaming' folder - delete the 'worktips' sub folder. Re-start your client to re-sync from the scratch. If you can't find the 'appData' folder turn the 'Show hidden files and folders' option in your Windows.

**Downloading the blockchain folder from a Linux**

- Install dependencies

``
sudo apt-get install zip apache2
``

- Compress the blockchain folder

``
sudo zip -r worktips.zip ~/.worktips/
``

- Copy the blockchain folder to apache folder

``
cp ~/worktips.zip /var/www/html
``

- Download the compressed blockchain folder using the below address in your web browser

``
http://YOURVPSIPADDRESS/worktips.zip
``

**Restarting redis server on Linux**

``
/etc/init.d/redis-server restart
``

**Adding swap file on Linux**

- Ubuntu 14: https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04
- Ubuntu 16: https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04
