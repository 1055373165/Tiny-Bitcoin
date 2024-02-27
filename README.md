Blockchain tutorial:
===================

[Source Link](https://jeiwan.cc/posts/building-blockchain-in-go-part-1/)  


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




# Bug

问题描述：
gob: type not registered for interface: elliptic.p256Curve 
panic: gob: type not registered for interface: elliptic.p256Curve

解决方法：自定义序列化和反序列化
由于 go 1.8 之后 elliptic.p256Curve 直接用作 ecdsa.PrivateKey 中的一部分，且该类型未导出，我们需要找到一个替代方案来序列化和反序列化包含 ecdsa.PrivateKey 的结构。
可以通过将 ecdsa.PrivateKey 转换为一种可序列化的格式来绕过这个问题，例如，将密钥转换为 PEM 或 DER 格式的字符串，然后序列化字符串。在反序列化时，再将字符串转换回 ecdsa.PrivateKey。
