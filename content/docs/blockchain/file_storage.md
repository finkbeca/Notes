---
title: File Storage
weight: 2
bookToc: true
---

## Filecoin & IPFS
---
[Slate](https://slate.host/)  
[Decentralzied Storage Overview](https://medium.com/bitfwd/what-is-decentralised-storage-ipfs-filecoin-sia-storj-swarm-5509e476995f)  
[IPFS Ideas](https://docs.ipfs.io/concepts/usage-ideas-examples/)  
[Ceramic](https://ceramic.network/)


### OrbitDB & Notes
[Orbit DB](https://orbitdb.org/)  
[Orbit DB Field Manual](https://github.com/orbitdb/field-manual)    
[Orbit DB Example](https://github.com/orbitdb/example-orbitdb-todomvc)   
[Orbit DB Master List](https://github.com/orbitdb/awesome-orbitdb)  
[Orbit DB Tutorial](https://github.com/orbitdb/web3-workshop/tree/6-play-track)  

[Reference](https://github.com/orbitdb/orbit-db/blob/master/GUIDE.md)   
    OrbitDb is  a peer to peer database where each peer has its own instance of a database. Databases are replicated automatically.
    There are 5 data type or data models:  
    - Key-Value  
    - Log (append only)  
    - Feed (append and removal)  
    - Documents (store indexed JSON Docs)  
    - Counters  

    The database is given an address which can be broken down into 3 parts, the first part tells what protocol is in use, the second part is an IPFS multihash, and the third part is the name.  

    Each entry in a database is also signed by who created it. ''' const indentity = db.identity ''' . This identity can then be used within OrbitDb.  

    You have access control to whom can write to a database. You can define a set of peers that can write to a database or allow anyone write access to a database. By default it is just the creator of the database 

    Public databases are also supported by adding a * to the write access arary

    Adding to databases:
    - KeyValue: db.put()
    - Log: db.add()
    - Feed: db.add()
    - Docs: db.put()
    - Counter: db.inc()

    Getting from Databases:
    - KeyValue: db.get()
    - Log: db.iterator()
    - Feed: db.iterator()
    - Docs: db.get()
    - Docs: db.query()
    - Counter: db.value()

[3Box](https://3box.io/) - Shared Backend for Web3 using Ethereum, IPFS, and OrbitDB  
[3box tutorial](https://github.com/RachBLondon/dapp-store)

    
## Swarm
---
[Documentation](https://swarm-guide.readthedocs.io/en/latest/)  