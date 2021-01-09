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
[IPFS Whitepaper](https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf)  
[Creating IPFS Node](https://docs.ipfs.io/how-to/command-line-quick-start/#initialize-the-repository)  
[How IPFS deals with files](https://www.youtube.com/watch?v=Z5zNPwMDYGg&feature=youtu.be) -Youtube  
[Js-IPFS Files Docs](https://github.com/ipfs/js-ipfs/blob/master/docs/core-api/FILES.md)  
[Protoschool tutorials](https://proto.school/)

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
    <br/>
    Getting from Databases:  
    - KeyValue: db.get()  
    - Log: db.iterator()  
    - Feed: db.iterator()  
    - Docs: db.get()  
    - Docs: db.query()  
    - Counter: db.value()  

[3Box](https://3box.io/) - Shared Backend for Web3 using Ethereum, IPFS, and OrbitDB  
[3box tutorial](https://github.com/RachBLondon/dapp-store)

## IPFS Notes

### Files API
The DAG APi allows you to use  unqiue and primitive data structures offered by IPLD within IPFS.  Its method in js-ipfs takes the format ipfs.dag.someMethod()
DAG Api is the most generic approach to adding data to the IPFS node. The files API on the otherhand prepare files to pbe placed in the network and ensures that IPFS knows how to access them. It is made of two parts: Regular Files API and Mutable File System
MFT provides an API to replicate file systems such as ``` mkdir ls cp``` mimicking how you organize directories on a computer. In Regular Files API it uses aa bare bones approach to mangage files in IPFS. MFT uses ``` ipfs.files.someMethod()``` while Regular Files API uses ``` ipfs.someMethod()```
```ipfs.add(data, [options])```
Thus we can for example:
``` const result = await ipfs.add(catPic)```
The value of the variable result is an object in the format"
``` {
path: String,
cid: CID,
size: Number,
mode: Number
}
```
We can also use AddAll to do this with multiple files ```ipfs.addAll([catPic, dogPic, giraffePic])```
this returns an async iterable allowing us to iterate over the values one by one.

To retrive an file from IPFS you can use CID. For example, ```ipfs.cat(ipfsPath, [options])``` ipfsPath in one context can be the cid. Note Buffer is a raw collection of bytes that makes no assumptions about encoding. 
```
const bufferedContents = await toBuffer(ipfs.cat('QmWCscor6qWPdx53zEQmZvQvuWQYxx1ARRCXwYVE4s9wzJ')) // returns a Buffer
const stringContents = bufferedContents.toString() // returns a string
```
Making add calls more human friendly:

```
ipfs.addAll([
    {
        path: 'adorable-kitty.jpg',
        content: catPic1
    },
    {
        path: 'cat-drinking-milk.jpg',
        content: catPic2
    }
], { wrapWithDirectory: true })
```
This director we made is immutable it does not act as a normal directory, and we can not add new files to it.
Note: two directories with identical CID are guaranteed to have identical contents. To look at the content of a director you can use ```ipfs.ls(ipfsPath)```
If we use a director we now have 4 ways to find the file using cat. We can go by the cid. the full ipfs path ipfs/... the cid of the director and the files relative path or the ipfs full path of the directory and the files relative path from there. Wrapwithdirectory allows us to use human_readable filenames in ipfs paths making it a possible reason to wrap files in directories. When we are using ipfs path and just not cid for reference we need to include /ipfs/ at the start at there are other networking protcols that use the same CID

If you need other metadata about a file or a directory you can get it by calling ```ipfs.get(ipfsPath)```
Get will run on a directory and on any subdirectories recursively.
## Swarm
---
[Documentation](https://swarm-guide.readthedocs.io/en/latest/)  

## Arweave
[Arweave Whitepaper](https://www.arweave.org/yellow-paper.pdf)

## Sia

[Sia](https://sia.tech/)