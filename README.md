# **Satoshi**

A blockchain architecture for file backups.


## The idea is to 



When a file gets appended to the blockchain:

     readFile | Turn contents into base64 | encrypt | compress 


When a file gets exported:

     readBlockchain | decompress | decrypt | parse base64


___

## Function

### The _Blockchain_

It could be an encoded and compressed JSON file (with a .satoshi extension), serializing each block with its pertinent metadata. As such, for the Satoshi client to operate on a blockchain it must first decompress, decrypt and finally, appropiately parse the JSON structure within.

A blockchain can be previewed, fully expanded, its name can change, but the data of each block must not mutate, otherwise the integrity and trust factor will get corrupted, and the blockchain will be left useless.

Multiple blockchains can be instantiated, starting from a file, several files or a full directory.


### The _Block_

It consists of data (a file or a directory) and some metadata which may vary depending on the data type. On request, a block can be temporarily shown or fully exported, in which case all it's contents would get their original names. Previews will get garbage-collected upon app close. Block expansions don't mutate the blockchain.

Directory blocks could be implemented, its expansion consisting of recursive file expansions.


## Form

An electron framework could be a nice option, in case the project collaborators decide that Satoshi needs a GUI. Another option could be a pure Node CLI interface.

## Security considerations

* Whole program runs inside an IIFE (no global pollution)
* Use key derivation for weak passwords
* Block Dev Tools if electron-based
* Use up-to-date and standard-compliant methods like crypto.Cipheriv, Buffer.alloc, Buffer.from, fs.Stats, fs.Dir, fs.Dirent, etcetera/
* Use stream events if necessary for better control (for example measuring if it surpasses the bytes threshold specified [something like, I REALLY DON'T KNOW, 50Gbs per block by default?] )
* Prefer _sinchronous_ methods for the sake of blockchain sanity.
* What about RAM?

