# **Satoshi**

A blockchain architecture for file backups.


## The idea



When a file gets appended to the blockchain:

     readFile | Turn contents into base64 | encrypt | deflate 


When a file gets exported:

     readBlockchain | inflate | decrypt | parse base64


___

## Function

### The _blockchain_

It could be a compressed and encoded JSON file (with a .satoshi extension), serializing each block with its pertinent metadata. As such, for the Satoshi client to operate on a blockchain it must first decompress, decrypt and finally, appropiately parse the JSON structure within.

A blockchain can be previewed, fully expanded, its name can change, but the data of each block must not mutate, otherwise the integrity and trust factor will get corrupted, and the blockchain will be left useless.

Multiple blockchains can be instantiated, starting from a file or directory.


### The _block_

It consists of data, any given file content, and some metadata which may vary depending on the filetype. On request, a block can be temporarily shown or fully exported, in which case it'll get its original filename. Previews will get garbage-collected upon app close. Block expansions don't mutate the blockchain.

Directory blocks could be implemented, its expansion consisting of recursive file expansions.


## Form

An electron framework could be a nice option, in case the project collaborators decide that Satoshi needs a GUI. Another option could be a pure Node CLI interface.


