# sml-rfc：产品特性管理

有许多修改，如BUG FIXES和文档改进等需求，可以通过GITHUB的Pull requests (PR) 实现，但是，有一些很重大的改进，我们需要深入思考、仔细设计，并且取得社区的一致性认可。

"RFC" (request for comments)  流程，尝试提供一种可控的方式，用于帮助新的需求进入到产品中，所有的产品参与者，可以通过参与RFC，了解和掌握产品的发展方向。

## 什么时候应当参与RFC

当你认同，且认为你需要对产品提出重大的改进时，你可以提出一个RFC。RFC会根据修改的方向和范围，对社区和产品造成影响，考虑以下情况：

- 对数据处理流程进行变动
- 对产品的存储机制做出修改
- 对产品的系统架构进行改进
- 对产品的使用接口进行改造

有一些改动，并不需要提交一个专门的RFC，通过ISSUE提交即可，考虑以下情况：

- 代码的重构，调整，优化，在功能和接口不变的前提下的调整
- 用于产品的质量控制代码，如日志埋点、性能度量、日志输出，或者是平台的兼容性支持
- 严格遵循产品规划 (Road Map) 的代码改动

BUGFIX并不需要通过RFC流程，但是考虑到一些BUGFIX的改动，会涉及到对原有设计的修改，甚至是接口的修改，此时应慎重对待。

随着实践和经验积累，RFC的定义可能会发生一些调整，在RFC定义时，我们已经参考了成熟产品的RFC描述，但这未必能保证RFC流程的合理性。

当您提交一个PR，且PR涉及到功能变动时，请谨慎考虑您是否已经提交了一个RFC。

## 提交RFC前的注意事项

一份简单草率的RFC，很可能会导致它无法被社区所接受。缺乏建设性的功能需求，曾经被拒绝的功能，与规划冲突的的需求，都会被拒绝。

为了更好的提出一份RFC，我们建议您可以与社区成员进行积极沟通，社区成员往往对产品的发展方向有更深刻的理解和更全面的资讯，目前，受限于
目前的成熟状态，我们只提供了产品定义，但暂时无法制定过于具体的里程碑，这一点可能会给您造成困惑，如果可以，请就产品定义和下一阶段里程碑
与社区成员进行深入沟通。

我们会努力尝试建立良好的沟通机制，以便我们更好地交流。我们会保持谦卑和温和的态度，这将会也应当是我们社区的风格。

请记住：对产品保持持续的影响力，在于您努力于社区保持一致，推动着产品不断发展。

## RPC具体流程

简单而言，如果您提交一份RFC PR成功，那就意味着您的RFC已经获得通过，RFC将处于活跃的状态，直到获得足够的资源安排，RFC将会被实现。

- Fork https://github.com/SmartBDE/sml-rfc
- 拷贝 0000-template.md 到 text/0XXX-my-feature.md (这里 'my-feature' 是功能描述，请不要使用数字编号或无意义的文字)。
- 填写RFC中需要填写的内容，请采用客观公正的方式描述相关内容。
- 提交一个pull request，如果您对如何提交pull request不熟悉，请参考github的说明。我们会对您的提交进行回复。
- 请持续关注pull request的情况，一个得到更多关注的pull request，会获得更快的推进进度。
- 我们可能会需要您的进一步协助，通过沟通或其他方式，帮助我们实现该功能。
- 社区的成员将会对该RFC进行讨论，对PR进行评价，或者用其他方式深入理解该RFC。
- 当您觉得RFC还需要改进时，请您注意修改的范围，当RFC被公开化以后，对它的修改应当慎重，以免引起不必要的误会，您有必要在PR里面补充修改的相关说明。
- 当RFC PR的每一个细节都得到充分的讨论，RFC进入到最后的提交确认环节，此时，社区拥有最后一次对RFC进行讨论和评论的机会，社区的成员会收到提醒，以便确认RFC的最后提交。RFC的提交者拥有最终决定RFC是否进入提交阶段的权力，如果提交者最终决定提交，RFC的维护者会把PR整合到代码库中。
- 我们会碰到社区成员意见不统一的情况，考虑到RFC进入最后提交确认环节前，只需要澄清RFC，而RFC确认提交环节，则意味着社区的成员会参与到实现中，此时，我们采用社区成员核心成员约定人数达到一定数目后即可通过的方法，决定RFC是否进入代码库。

## RFC生命周期管理

一旦RFC被整合到代码库，这意味着RFC处于激活状态，只要有成员实现了该功能，并发起PR，那么社区成员必须把该实现整合到产品中。

然而，RFC被激活并不以为着RFC的优先级被限定，也不意味着有人被安排到该功能的实现中，社区的成员并没有责任限定在某个时间内完成该功能，虽然RFC的提交者并没有被要求该RFC的实现由提交者负责，但最快的方法是由自己去实现该功能。

对已经激活的RFC的修改，我们通常认为是不恰当的，但是，考虑到产品的衍化过程中，也会对激活的RFC造成影响，我们建议通过PR来完成RFC的更新。原则上，RFC不应该有大幅度的修改，只有小修补才可以被接受。请为重大修改建立新的RFC。

## RFC的评审

当收到RFC时，我们会安排社区成员讨论和跟进RFC，也会通过PR的记录，反馈讨论的结果。RFC的评审意见遵循公开公正的原则，所有的信息都会在PR记录中反映，我们希望每一个RFC都经过充分的讨论和慎重的思考，无论该功能是否被激活或拒绝。

## RFC的实现

一些被激活的RFC，代表着重要的功能和产品方向，社区成员会优先安排这些功能的实现。其他的一些被激活的RFC则需要等待某些开发者乐意开展该工作。每一个被激活的RFC，如果是由社区成员负责跟进的话，都会有一个对应的ISSUE被创建，以便记录和讨论，考虑到ISSUE可以进行优先级管理，我们将对正在开展的开发进行合理的优先级调整。

在您尚未决定成为社区成员前，社区成员往往意味着保持固定的项目投入和活跃度，我们也非常欢迎您通过FORK和PR来提交该RFC的实现。为了避免您的工作和我们安排重复，我们建议您和我们保持沟通，如通过ISSUE发表您的意见。

## 本文档的设计

非常感谢 PonyLang RFC的流程，Ponglang RFC充分参考了Rust和Ember项目的实践经验，对此致以深切的感谢。
