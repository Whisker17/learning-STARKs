# STARKs, StarkEx 以及 StarkNet

## 内容提要

- STARKs 通过有效证明计算完整性来实现区块链扩展
- StarkEx 是一个特定于应用程序的扩展引擎
- StarkNet 是一个无需许可的智能合约 2 层网络

## STARKS

STARKs（可扩展的、透明的知识证明）是一个能够证明和验证计算的证明系统。它允许在处理一个大型计算时，通过生成一个计算正确性的证明，然后以极少的步骤验证该证明。

STARKs 可以在区块链的可扩展性中发挥关键作用，它允许大型计算在开销更小的链下完成，仅需要一小部分计算的验证在链上完成。换句话说，通过在链上执行很少的步骤，验证者就能证明在链下进行的更大的计算的完整性。

2 层解决方案通过使用 STARKs 将成千上万的交易批量化并进行计算，然后用一个 STARK 证明在链上验证其有效性。链上过程的成本在批次中的**所有**交易之间分配。这导致了交易具有 Ethereum 级别的安全性和每笔交易的低 gas 成本。

低计算成本将迎来以前在链上不可行的一类新应用。这些特性使 STARK 成为改善用户体验和降低 gas 成本的优秀构成部件，同时保持 Ethereum 结算层的安全性。

StarkWare 提供了两种解决方案，以用 STARKs 来扩展 Ethereum。StarkEx 和 StarkNet。

## StarkEx

[StarkEx](https://starkware.co/starkex/) 是一个用于创建需许可的、针对特定应用的扩展解决方案的框架。StarkEx 是一个有用的[应用流程](https://docs.starkware.co/starkex-v4/starkex-deep-dive/regular-flows)工具箱，项目可以用它来实现廉价的链下计算。一个证明执行正确性的 STARK 证明是在链下生成的。这样一个证明可以包括多达 12,000-500,000 个交易（取决于交易类型）。然后，该证明被发送到 STARK 验证器，以便在链上被接受。这意味着对所有交易进行一次验证--每笔交易分摊的 gas 成本低得惊人。

部署在 StarkEx 上的应用的几个例子是 dYdX（永续交易）、Immutable 和 Sorare（NFT 的铸造和交易）、DeversiFi（现货交易）和 Celer（DeFi 池）。

StarkWare 公司正在根据市场和客户的需求不断向 StarkEx 添加更多的应用流。

## StarkNet

[StarkNet](https://starkware.co/starknet/) 是一个无需许可的 2 层网络，任何用户或开发者都可以部署用 Cairo 语言开发的智能合约。

与 Ethereum 智能合约的体验类似，在 StarkNet 生态系统内，你的合约可以与部署在 StarkNet 上的任何其他合约互动，从而实现丰富的可组合协议。StarkNet 合约也可以通过异步消息传递与 Ethereum 合约互动。

与 StarkEx 不同的是，在 StarkEx 中，应用程序负责提交交易，而 StarkNet 的排序器将交易分批发送，并进行处理和证明。(StarkNet 的排序器目前由 StarkWare 运营，未来计划去中心化）。这意味着一旦应用程序部署了他们的 Cairo 合约，他们就不必担心运行额外的运营商基础设施。StarkNet 支持 Rollup 数据可用性模式，这意味着 Rollup 的状态与 STARK 证明一起被写入 Ethereum。

一个巨大的开发者社区正深入参与到 StarkNet 生态系统中，构建应用程序、工具和基础设施。数十种应用已经在 testnet 上上线--DeFi、游戏、投票、人工智能等等。此外，StarkNet 社区正在建立开发者工具，如区块链浏览器、本地测试环境和框架、几种语言的 SDK 等等。此外，大家可以在 [Shamans](https://community.starknet.io/) 的平台上进行了积极的讨论，提出了改进建议，潜在的功能和最佳实践。

## 总结

[StarkEx](https://youtu.be/P-qoPVoneQA) 和 StarkNet 都是基于 STARK 的扩展解决方案。两者都提供可扩展性、低 gas 成本和安全性，但有不同的操作要求和互操作性模式。StarkEx 可能是适合大部分自包含并适合 StarkEx 提供的 API 的应用程序的正确解决方案。StarkNet 可能更适合于需要与其他协议同步交互，或者有超出 StarkEx 提供的需求的协议。

STARKs 已经彻底改变了在 Ethereum 上构建应用程序的方式。StarkEx 和 StarkNet 将继续实现以前不可行的应用，并拓展区块链上可能的极限。
