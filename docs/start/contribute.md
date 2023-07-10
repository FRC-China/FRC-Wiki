# 如何参与[^ref1]

## 写在前面

**FRC China Wiki** 项目组全体成员十分欢迎您为本项目贡献页面。

这篇文章将主要叙述参与 **FRC China Wiki** 编写的写作过程。请您在撰稿或者修正 Wiki 页面以前，仔细阅读以下内容，以帮助您完成更高质量的内容。

## 贡献指南

请您在提交拉取请求（Pull Request，以下称为 PR）前再次阅读如何参与的有关内容，尤其应再次确认对于目录和引用的变更和信息格式规范。

如果有关内容尚未完成，请考虑先新建 Issue 或本次作为 Draft PR 提交。如有讨论需求请在 Discussion 中新建 Idea 讨论 Thread。

如果内容已经完成，您无需新建 Issue ，但仍需要核对格式手册中文档的基本格式要求，并依据 Reviewer 提出的建议进行修改。

在提交 PR 前，确保您已知晓：

- 请在回应建议、问题或 PR 之前仔细阅读本指南，并详细说明自己的看法，以免引起不必要的误会。

- 请跟进您的 PR。如您的 PR 长时间没有回应修改请求，可能会被直接关闭。

- 我们欢迎您审核其他 PR，但请以友好的方式发表评论。负面评论会打击社区贡献者的贡献热情，因此不建议这样做。当你在 PR 中发现问题时，欢迎进一步的 PR，但不欢迎你对贡献者（PR 作者）发表负面评价。

- 请记住，您在一个社区中，您需要学会接受其他人的贡献，以及他们贡献的内容，甚至可能和他们协作。如果您不同意这个观点，您可以创建分支并自己进行更改。另一方面，你的想法可能不够完善，所以要听取别人的意见。

当你的被接受 PR 数量达到 10 个的时候可以向我们申请成为主要 Maintainer。作为主要 Maintainer，你拥有 Approve 他人 PR 的一票决定权。

## 参与协作

在开始编写一段内容之前，请查阅 [Issues](https://github.com/FRC-China/FRC-wiki/issues)，确认没有别人在做相同的工作之后，开个 [新 issue](https://github.com/FRC-China/FRC-wiki/issues/new) 记录待编写的内容。

**请尽量使用 Discussion 或 Issue 与他人沟通。这样可以使你们的思路与想法被保存下来，以供他人参考或改进！**

在这里引用维基百科的一句话：

> 不要害怕编辑，勇于更新页面！[^ref2]

!!! info "提示"
    由于本 Repo 较为特殊的部署方式，你的 PR 在被 Merge 后将最多需要 3 小时生效，请耐心等待。

    也正因此本地预览对于发现错误变得极为重要。

### 在 GitHub 上编辑

参与 **FRC China Wiki** 的编写 **需要** 一个 GitHub 账号（可以前往 [GitHub 的账号注册页面](https://github.com/signup) 页面注册），但 **不需要** 高超的 GitHub 技巧，即使你是一名新手，只要按照下面所述的步骤操作，也能够 **非常出色** 地完成编辑。

在你的更改被合并到 **FRC China Wiki** 的主仓库之前，你对 **FRC China Wiki** 的内容所作出的修改均不会出现在 **FRC China Wiki** 的主站上，所以无需担心你的修改会破坏 **FRC China Wiki** 上正在显示的内容。
    
如果还是不放心，可以查看 [GitHub 的官方教程](https://skills.github.com/)。

### 使用 Git 在本地进行编辑

大致流程如下：

1.  将主仓库 Fork 到自己的仓库中；
2.  将 Fork 后的分支仓库克隆（clone）到本地；
3.  在本地进行修改后提交（Commit）这些更改；
4.  将这些更改推送（push）到你克隆的分支仓库；
5.  提交 PR 至主仓库。

#### 向 PR 追加更改

在 Clone 下来的本地分支仓库中继续进行修改，并提交（Commit）以及推送（Push）这些更改即可。你的更改会被自动追加在 PR 中。

#### 通过本地进行预览

1. 在您的计算机上安装 Python
2. 在本项目根文件夹下打开终端，输入 `pip install -r requirements.txt`
3. 在终端中输入 `mkdocs serve`

请务必在提交之前做一下以上步骤，确保您的更改没有问题。

### 对于目录和引用的变更

通常情况下，如果您需要添加一个新页面，或者修改已有页面在目录中的链接，您就需要对 [`mkdocs.yml`](https://github.com/FRC-China/FRC-Wiki/blob/main/mkdocs.yml) 文件作出改动。

添加新页面可以参考既有的格式。但除非是进行重构或修正名词，否则 **我们不建议对既有页面的引用链接进行修改**，PR 中不必要的修改也将被驳回。

### Commit 信息格式规范

对于提交时需要填写的 Commit 信息，请遵守以下几点基本要求：

1.  Commit 摘要请简要描述这一次 Commit 改动的内容。注意 Commit 摘要的长度不要超过 50 字符，超出的部分会自动置于正文中。
2.  如果需要进一步描述本次 Commit 内容，请在正文中详细说明。

对于 Commit 摘要，请使用 [Conventions Commits 1.0.0](https://www.conventionalcommits.org/zh-hans/v1.0.0/) 规范进行书写。由于这是中文维基，Commit 信息可以使用中文书写。

### PR 信息格式规范

对于 PR，请遵守以下几点要求：

1.  标题请写明本次 PR 的目的（做了 **什么** 工作，修复了 **什么** 问题）。
2.  内容请简要叙述修改的内容。如果修复了一个 issue 的问题，请在内容中添加 `fix #xxxx` 字段，其中 `xxxx` 代表 issue 的编号。

对于 PR 的标题，推荐使用如下格式书写，修改内容部分中英文皆可：

```text
<修改类型>(<区域>): <修改的内容> (<对应 issue 的编号>)
```

修改类型分为如下几类：

-   `feat`：用于添加内容的情况。
-   `fix`：用于修正现有内容错误的情况。
-   `refactor`：用于对一个页面进行重构（较大规模的更改）的情况。
-   `revert`：用于回退之前更改的情况。

示例：

-   `fix(ds/persistent-seg): 修改代码注释使描述更清晰`
-   `fix: tools/judger/index 不在目录中 (#3709)`
-   `feat(math/poly/fft): better proof`
-   `refactor(ds/stack): 整理页面内容`

## 参考资料与注释

[^ref1]: [如何参与 - OI-Wiki](https://oi-wiki.org/intro/htc/)

[^ref2]: [维基百科：新手入门/编辑](https://zh.wikipedia.org/wiki/Wikipedia:%E6%96%B0%E6%89%8B%E5%85%A5%E9%96%80/%E7%B7%A8%E8%BC%AF)