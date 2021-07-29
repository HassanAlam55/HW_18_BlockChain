# HW_18_BlockChain
## or How to do a ./puppeth on a (shoe) String
 ![Puppet](ScreenShots/puppet.jfif)<br>
To test bitcoin network go to:<br>
step 5 <br>
I have installed the test network in steps 1 - 4 so you should be able to run it.


### 1. Set up Nodes<br>
I created two nodes for exchange Crypto: node1 and node2 with the following commands<br>
./geth --datadir node1 account new<br>
./geth --datadir node2 account new<br>

The infor for the nodes are:<br>
Node 1:<br>
	pwd: testing<br>
	Public address of the key:   0x20AB545aFF9eDA6841C885D0027b978cd18d9bd5<br>
	Path of the secret key file: node1\keystore\UTC--2021-07-27T19-39-50.504693400Z--20ab545aff9eda6841c885d0027b978cd18d9bd5
	forward path: node1/keystore/UTC--2021-07-27T19-39-50.504693400Z--20ab545aff9eda6841c885d0027b978cd18d9bd5<br>

Node 2:<br>
	pwd: testing<br>
	Public address of the key:   0xE0561E959A638346f6a8E501e74BeA6f0c31B011<br>
	Path of the secret key file: node2\keystore\UTC--2021-07-27T19-35-29.144766600Z--e0561e959a638346f6a8e501e74bea6f0c31b011<br>
	forward path: node2/keystore/UTC--2021-07-27T19-35-29.144766600Z--e0561e959a638346f6a8e501e74bea6f0c31b011<br>

### 2. Generate Genesis<br>
I generated a Genesis network using ./puppeth <br>
named: puppethonastring<br>
network id: 333<br>
Type: Proof of Authority<br>
The files are shown in the directory:<br>
 ![Screenshot](ScreenShots/Screenshot-2021-07-27-225027.png)


### 3. Initialize Nodes
I then initialized the nodes<br>
./geth init puppethonastring.json --datadir node1<br>
./geth init puppethonastring.json --datadir node2<br>
 ![Directory](ScreenShots/Directory_Shot.png)


### 4. Mine 
I then started the block chains<br>
./geth --datadir node1 --unlock "0x20AB545aFF9eDA6841C885D0027b978cd18d9bd5" --mine --rpc --allow-insecure-unlock<br>

./geth --datadir node2 --unlock "0xE0561E959A638346f6a8E501e74BeA6f0c31B011" --mine --port 30304 --bootnodes "enode://c06b642873d1a0570815e5d422d38d288c020c898cc84e6fd37d5990903052a2487934afae29a8c8ec0445c710abf0cd0520d989bf99e78870a8691597191dd4@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock<br>

### 5. Test
I started up MyCrypto. You can transfer crypto between your wallets.
![node 2](ScreenShots/node_2_screenshot.png)<br>
!mycrypt](ScreenShots/mycrypto.png)<br>
![status](ScreenShots/mycryptotransactionstatus.png)<br>
![success](ScreenShots/successful_txstust.png)<br>
