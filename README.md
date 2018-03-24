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


### Compile on Windows

**1. Fork the coin**

1. Create an account on [GitHub.com](github.com) or log in to an existing one
2. Fork [Worktips repository](https://github.com/Vordas/Worktips-v2) or/and download it

**2. Install dependencies**

Dependencies: Microsoft Visual Studio 14 2015, CMake 2.8.6 or later, and Boost 1.55. 

You may download them from:
- http://www.microsoft.com/
- http://www.cmake.org/
- http://www.boost.org/

**3. Configure and generate the project files with CMake GUI**

- start CMake GUI and navigate to the repository folder using the field 'Where is the source code:'
- in the field 'Where to build the binaries:' specify the build folder location
- click the 'Configure' button to start the configuration
- select 'Visual Studio 14 2015 Win64' option.
- click the 'Finish' button to run the configuration
- after the configuration is done, click the 'Generate' button to generate your project files
- after successfull generation click the button 'Open project' to start building the binaries

**4. Build the binaries using Microsoft Visual Studio 14 2015**

- CMake GUI will open the project in the Microsoft Visual Studio you selected for the configuration
- wait for the Microsoft Visual Studio to scan and prepare all of the files for the project
- the scan is finished when the message 'Ready' appears
- click the 'Build' button from the main menu
- your binaries are located in either the `src/release` or the `src/debug` sub folders depending on your MSVC configuration

### Compile on Linux Ubuntu 14/16

**1. Install dependencies**

Run an update

``
sudo apt-get update
``

Get all the deps

``
sudo apt-get -y install build-essential python-dev gcc-4.9 g++-4.9 git cmake libboost1.58-all-dev librocksdb-dev
``

**2. Fork the coin**

Fork the repo

``
git clone https://github.com/Vordas/Worktips-v2.git worktips
``

**3. CHMOD**

Navigate to:

``
cd worktips/external/rocksdb/build_tools
``

Execute the following commands:

``
chmod +x build_detect_platform
``

``
chmod +x version.sh
``

**4. Build executables**

Navigate back to repo folder 

``
cd
``

``
cd worktips
``

Export flags

``
export CXXFLAGS="-std=gnu++11"
``

Make/Build

``
make
``

Your executables will be located in `build/release/src` folder.
