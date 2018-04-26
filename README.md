# Troubleshooting
Information for compiling, nodes etc. 

# How do I fix the error "out-of-sync"?
The wallet can show the message "x hours behind" or "out-of-sync" when no block is found for a couple of hours. This message will disappear when the next block is found.

The error message "x hours behind" or "out-of-sync" can be triggered when the last block is mined longer ago than your block time.

E.G. Blocktime : 10 minutes, last block found 30 minutes ago.

You can fix the error by mining your first or next block.

# How do I fix the error "Incorrect or no genesis block found"?
The warning "Incorrect or no genesis block found. Wrong datadir for network" is caused by a different blockchain with the same name.

You can fix this using the following instructions.

Important: replace "examplecoin" with the name of your blockchain.

1) Close your wallet. 
2) Make a backup of the folder "%appdata%\examplecoin".
3) Remove the folder "%appdata%\examplecoin".
4) Start your wallet.

# How do I fix the error "500 internal Server Error" in minerd?
The following only applies for a scrypt PoW/PoS blockchain.

The error message "500 internal Server Error" in minerd is generated because your blockchain passed your last PoW block height.

You can now only stake for PoS blocks.

# How do I fix the compiling error "recipe for target 'rpcrawtransaction.o' failed"?
Note: This error is typical if you're using Ubuntu 16.04 vs. 14.04.

Open the file src/rpcrawtransaction.cpp with a file editor.

Search for the following line of code.

`const CScriptID& hash = boost::get<const CScriptID&>(address);`

Replace this line of code with the following line of code.

`const CScriptID& hash = boost::get<CScriptID>(address);`

# How do I fix the error "error while loading shared libraries"?
The linux daemon is compiled for Ubuntu 14.04 and is not compatible with other versions of Ubuntu.

The error message "error while loading shared libraries: libboost_system.so.1.54.0: cannot open shared object file" is triggered when you start the daemon in an unsupported version of Ubuntu server.

You can fix the error by compiling a new daemon. 
Compiling instructions are available here -> 

# How do I start my wallet on Ubuntu desktop?
You need to install the following dependencies to start your wallet in Ubuntu desktop.

1) `apt-get install build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev git libssl1.0.0-dbg`

2) `apt-get install libdb-dev libdb++-dev libboost-all-dev libminiupnpc-dev libminiupnpc-dev`

3) `apt-get install libevent-dev libcrypto++-dev libgmp3-dev libqtgui4`

# How do I start my wallet on Microsoft Windows?
Windows SmartScreen is a new feature in Windows 8 to help protect users from running unverified software downloaded from the internet. It's a nice feature but it sometimes blocks our generated wallets.

You can fix this using the following instructions.

1) Right click the wallet (exe) and select "Properties".

2) Select "Unblock".

3) You can now start the wallet (exe).

Thank you,
OID Team



