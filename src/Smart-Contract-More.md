# More on Smart Contracts

We will provide more documents soon. Right now, there are several source codes to learn about our contract language:

1. simple Uniswap-like contract: [https://github.com/alephium/alephium/blob/master/flow/src/test/scala/org/alephium/flow/core/VMSpec.scala#L877-L985](https://github.com/alephium/alephium/blob/master/flow/src/test/scala/org/alephium/flow/core/VMSpec.scala#L877-L985)
2. there are more examples in the same file: [https://github.com/alephium/alephium/blob/master/flow/src/test/scala/org/alephium/flow/core/VMSpec.scala](https://github.com/alephium/alephium/blob/master/flow/src/test/scala/org/alephium/flow/core/VMSpec.scala)
3. an integration test for the Uniswap-like exchange based on Rest API: [https://github.com/alephium/alephium/blob/master/app/src/it/scala/org/alephium/app/SmartContractTest.scala](https://github.com/alephium/alephium/blob/master/app/src/it/scala/org/alephium/app/SmartContractTest.scala)
4. all of the built-ins:
   1. [https://github.com/alephium/alephium/blob/master/protocol/src/main/scala/org/alephium/protocol/vm/lang/BuiltIn.scala#L195-L218](https://github.com/alephium/alephium/blob/master/protocol/src/main/scala/org/alephium/protocol/vm/lang/BuiltIn.scala#L195-L218) and
   2. [https://github.com/alephium/alephium/blob/master/protocol/src/main/scala/org/alephium/protocol/vm/lang/BuiltIn.scala#L383-L411](https://github.com/alephium/alephium/blob/master/protocol/src/main/scala/org/alephium/protocol/vm/lang/BuiltIn.scala#L383-L411)
