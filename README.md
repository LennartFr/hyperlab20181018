# Hyperledger Fabric workshop at https://www.theden.io/ in Fremont. 
URL: https://ibm.biz/HyperledgerFremont

Lennart Frantzell @ LinkedIn

10/24/2018

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Agenda
~~~
7:00: Sign-in, mingle, food, welcome, form teams 
7:20: Lennart: Introduction to IBM Blockchain and Hyperledger  
7:40: Labs.
      Lab 1: Developer Journeys for Blockchain  https://developer.ibm.com/code/technologies/blockchain/
      Lab 2: Let's write an app with the Hyperledger Composer
      Lab 3: Into the IBM Cloud with IBM Blockchain
8:15: Where do we go from here?       
9:00: Event ends   
~~~~

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Section One, How did it all start?
 
October 2008. It all started with Satoshi Nakamoto and his paper [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) which addressed a key problem in electronic commerce:

<img src="https://farm5.staticflickr.com/4505/24079519258_ab8a80f7ed_o.png" width="769" height="229" alt="Double Spending">
<p>

<i>A blockchain is a decentralized virtual ledger for recording transactions <b>without central authority </b> through a distributed cryptographic protocol. It is made up of three technologies 

1. cryptographic algorithms, 
1. a distributed protocol, 
1. and replicated data 
<p>
which combined provide a trustworthy service to a group of nodes that do not fully trust each other. 
<p>
Source: https://www.zurich.ibm.com/dccl/papers/cachin_dccl.pdf

<img src="https://cdn-images-1.medium.com/max/1600/1*0rKNjHVnhdUmlm_LCig2zg.png">


<a href="https://www.ibm.com/blogs/bluemix/2017/03/new-benefits-program-cloud-solutions-providers-isvs/">New Benefits Program for Cloud Solutions Providers ISVs</a>

# News Update

<img src="https://www.hyperledger.org/wp-content/uploads/2018/10/EEA-Hyperledger-02-1.png"><p>

<a href="https://www.hyperledger.org/blog/2018/10/01/growing-the-enterprise-blockchain-ecosystem-through-open-standards-and-open-source-code">Growing the Enterprise Blockchain Ecosystem Through Open Standards and Open Source Code</a>

<a href="https://www.hyperledger.org/resources/publications/blockchain-performance-metrics">Hyperledger Performance Metrics</a>

<a href="https://cachin.com/cc/talks/20170106-blockchain-rwc.pdf">Cryptography and Protocols in
Hyperledger Fabric</a>

<a href="https://developer.ibm.com/code/technologies/blockchain/">IBM Blockchain Code Patterns</a>


<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Section Two, The tools we'll be using: Hyperledger from Linux Foundation

## Hyperledger Components

<a href="https://www.hyperledger.org/">Hyperledger by Linux Foundation</a>

<img src="https://hyperledger.org/wp-content/uploads/2018/07/Hyperledger_Greenhouse-59-2.png">
<hr size="5" color="black">
<p>
<img src="https://farm1.staticflickr.com/960/41055079635_d00c82c7dd_z.jpg">

https://www.hyperledger.org/projects/fabric

https://hyperledger-fabric.readthedocs.io/en/release-1.3/

Hyperledger, an open source collaborative effort to advance cross-industry blockchain technologies, 
is hosted by The Linux Foundation®. 

Deployed in Docker images.

<a href="https://hyperledger-fabric.readthedocs.io/en/release-1.2/_images/AppConceptsOverview.png">

<img src="https://static.andigital.com/wp-content/uploads/2017/07/08102002/pasted-image-0.png">

<img src="https://farm1.staticflickr.com/968/27085403057_c8a2ccd0cc_z.jpg" alt="composer">

https://www.hyperledger.org/projects/composer

[Composer Playground](https://composer-playground.mybluemix.net/login)


<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">


# Section Three, Let's take a look at a simple Hyperledger Fabric business network.

<img src="https://github.com/LennartFr/hyperledgerlab2018/blob/master/Screen%20Shot%202018-10-12%20at%2013.05.55.png">

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/Screen%20Shot%202018-10-20%20at%2013.47.54.png">

<img src="https://farm5.staticflickr.com/4458/37771305586_6bf75bc2af_o.png" width="853" height="482" alt="hyperledger architecture">

....your first network (BYFN) scenario provisions a sample Hyperledger Fabric network 
consisting of two organizations, each maintaining two peer nodes, and a "solo" ordering service. 

A blockchain network is comprised primarily of: 

### 1. Fabric Certificate Authority (CA) hyperledger/fabric-ca (also known as Membership Service Provider)

https://hyperledger-fabric-ca.readthedocs.io/en/latest/users-guide.html#overview

Every single operation in the Hyperledger Fabric must be signed by an X.509 certificate. 
The Fabric-ca certificate authority is used for generating X.509 certificates.

CA: Certificate Authority https://hyperledger-fabric-ca.readthedocs.io/en/latest/ 
         Comment: It provides features such as:
         1. Issues certificates to other network participants to enroll in the network,
	       or connects to LDAP as the user registry
         2. issuance of Enrollment Certificates (ECerts)
         3. certificate renewal and revocation

https://hyperledger-fabric-ca.readthedocs.io/en/latest/#welcome-to-hyperledger-fabric-ca-certificate-authority   
More on: https://hyperledger-fabric.readthedocs.io/en/release-1.2/identity/identity.html

<img src="https://hyperledger-fabric.readthedocs.io/en/release-1.2/_images/identity.diagram.11.png">

<img src="https://hyperledger-fabric-ca.readthedocs.io/en/latest/_images/fabric-ca.png">

### 2. A set of Peer nodes , or, simply, peers. Peers are a fundamental element of the network because they host ledgers and smart contracts. 

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/Peers.png">

Recall that a ledger immutably records all the transactions generated by smart contracts (or chaincode). 
Smart contracts and ledgers are used to encapsulate the shared processes and shared information in a network, respectively. 

1. The Fabric ledger is maintained by each peer and includes the blockchain and worldstate
1. A separate ledger is maintained for each channel the peer joins
1. Transaction read/write sets are written to the blockchain
1. Channel configurations are also written to the blockchain

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/Blockchain.png">

### 3. Fabric Orderering service and Consensus
The heart of the consensus algorithm. Before anything is committed to the ledger it must pass thru the
ordering service.

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/ordering.png">


<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/Screen%20Shot%202018-10-19%20at%2011.41.49.png">

Comment: The Hyperledger fabric ordering service is intended to provide an atomic broadcast 
ordering service for consumption by the peers. This means that many clients may 
submit messages for ordering, and all clients are delivered the same series of 
ordered batches in response.

~~~~
curl -sSL http://bit.ly/2ysbOFE | bash -s 1.3.0

===> List out hyperledger docker images

hyperledger/fabric-javaenv    Go is the default chaincode language, however there is also support for Node.js and Java      
                              chaincode. 1.3.0
hyperledger/fabric-tools                                                                                                  
hyperledger/fabric-ccenv      The fabric-ccenv image which is used to build chaincode,                                        hyperledger/fabric-orderer    https://hyperledger-fabric.readthedocs.io/en/release-1.1/ordering-service-faq.html              hyperledger/fabric-peer       https://hyperledger-fabric.readthedocs.io/en/release-1.3/peers/peers.html
~~~~

<img src="https://hyperledger-fabric.readthedocs.io/en/release-1.3/_images/peers.diagram.1.png">

~~~~

hyperledger/fabric-zookeeper  https://hyperledger-fabric.readthedocs.io/en/release-1.3/kafka.html?highlight=zookeeper                             
hyperledger/fabric-kafka      https://hyperledger-fabric.readthedocs.io/en/release-1.1/kafka.html

hyperledger/fabric-couchdb    https://hyperledger-fabric.readthedocs.io/en/release-1.1/couchdb_as_state_database.html 

Creating couchdb ... done
       Comment: Transactions are collected into blocks/batches on the Ordering Service.
       The  blocks are stored locally to disk on every Ordering Service node 
       along with a LevelDB or CouchDB index to these blocks by number. 
       The blocks are delivered via RPC to committing peers. 
       The peers store them locally, and maintain a LevelDB (or CouchDB)based block index.
       
       http://bit.ly/2zORhrC                                                                                            
 ~~~~
### 4: Chaincode or Smart Contracts

https://hyperledger-fabric.readthedocs.io/en/release-1.3/chaincode.html#chaincode-tutorials

 <img src="https://raw.githubusercontent.com/LennartFr/hyperlab20181018/master/Screen%20Shot%202018-10-19%20at%2011.49.41.png">

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/cc1.png">

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/cc2.png">

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/cc3.png">

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Section Four, let's begin devloping our app!

## Use Cases

https://www.ibm.com/blockchain/use-cases/

## Lab 1: Hyperledger Composer  https://github.com/LennartFr/hyperledgerlab2018#-hands-on-lab-
## Lab 2: Decentralized Energy Composer: https://github.com/IBM/Decentralized-Energy-Composer 
## Lab 3: IBM Blockchain Platform

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/IBM%20Cloud%20Samples.png">

https://www.ibm.com/blockchain/platform?|1298|22081

https://github.com/IBM-Blockchain/vehicle-manufacture. Click on Blue Button to kick off the deployment.


<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/car.png">


https://vehicle-manufacture-basilar-fenestration.mybluemix.net/tutorial

<img src="https://github.com/LennartFr/hyperlab20181018/blob/master/ibmcloudbc-1.png">

# Section Five, where do we go from here?

1. Go through the IBM Code Patterns for Blockchain. https://developer.ibm.com/patterns/category/blockchain/
1. Create more advanced applications from the list of IBM Use Cases 
1. Engage with IBM Developer Advocates on your plans and ISV free resources
1. https://www.coindesk.com/ibm-wants-know-ways-blockchain-can-go-wrong/

# Appendix
