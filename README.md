Blockchain tutorial:
===================

[Source Link](https://jeiwan.cc/posts/building-blockchain-in-go-part-1/)  
[Source Code](https://github.com/Jeiwan/blockchain_go)
[Forked Source Code](https://github.com/Sharykhin/blockchain_go)

Usage:
------

Remove my.db if it exists:

```
go run *.go createwallet
go run *.go createwallet
go run *.go listaddresses
go run *.go createblockchain -address {address1}
go run *.go getbalance -address {address1}
go run *.go send -from {address1} -to {address2} -amount 5
```
