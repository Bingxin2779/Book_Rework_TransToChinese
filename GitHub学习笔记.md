# git学习

学习GitHub和git最大的感想是，入门的时候感觉很难很难，完全体会不到其方便之处，但是一旦上手，就觉得非常好用。门里门外，完全不是一种天地。

学习git时我看了很多文字攻略，发现看不懂，又去B站和YouTube找了视频看，但还是觉得很难。我觉得可能是因为没有理解其中的思想，因此学习具体操作既零散、又浮于表面。

最后学通，一是有一个非常有趣的[交互式学习平台](https://learngitbranching.js.org/)，把git的体系用形象化的树形图展示出来，每输入一条指令都能看到仓库产生的变化，对理解git的思想和操作方式有很大帮助；二是在于真正在项目里体验。看再多攻略也不如自己折腾一个项目，多报错几次就会了。

# GitHub管理翻译项目尝试

我们在翻译技术小组第三次讨论题中共同探索了GitHub和git的用法，一起模拟了一个翻译项目，我在其中担任项目经理的角色，负责建立项目。

## 模拟项目设置

项目链接：https://github.com/Bingxin2779/Book_Rework_TransToChinese.git

本次模拟了一个**图书翻译项目**，翻译英文原版书《Rework》，翻译结果作为电子书线上发布（可使用GitBook）。

团队共6人，项目经理1人，负责建立项目、分派工作、监督进度；译员3人，校对2人。

主仓库中的文件如下图，从上到下依次包括：
- 中文翻译结果
- 翻译格式规范
- 翻译语言风格规范
- 项目介绍
- 英文原文
- 翻译结果目录及索引
- 术语表

![图1](https://uploader.shimo.im/f/PdgrsGbYfeEgyWKE.png!original)

## 操作概述 

每位成员均需完成的准备工作有：注册GitHub账号，下载Git并安装。

1. 首先，项目经理在GitHub建立项目，在README中撰写项目说明。

![图2](https://uploader.shimo.im/f/GnEXf0f5ge0CRKkB.png!thumbnail)

![图3](https://uploader.shimo.im/f/ikaogLwXw9sE1yVU.png!thumbnail)

2. 将仓库克隆到本地，在本地仓库中上传所需的各项文件，搭建项目框架，然后使用Git进行commit快照，然后push同步到远程仓库。

![图4](https://uploader.shimo.im/f/AfW6ZuxX2k8vSpZf.png!thumbnail)

3. 译者

- 参照仓库中的翻译规范和要求在自己fork下来的仓库中翻译
- 翻译完的内容pull request到远程主仓库的临时分支，pr时将Assignees设为自己；
4. 项目经理
- 查看pr请求，为翻译好的内容指定Reviewer并merge
- merge后to_review branch内容更新；
5. 校对
- 从to_review branch查看pr状态，需要自己校对的部分显示“review required”，然后认领任务，在自己fork下来的仓库校对，校对时使用评论功能（鼠标移动到行首时出现蓝色加号，可以添加comment）
- 校对后点击页面右上角的“Review changes”，如果需要译者修改就勾选“Request changes”，如果不需要译者修改就勾选“Approve”，然后点击“Submit review”
- 等待译者修改完毕再次提交后，要再去校对，直到你发现的所有问题都被修复，选择“Approve”。
6. 项目经理
- 查看pr列表，选择有“Approved”标识的pr，将上述在临时分支中更改的内容merge到主仓库。

## GitHub管理翻译项目的思路总结及优势

- GitHub项目的核心是一个托管在远程服务器上的主仓库（直观来说就是在GitHub的Web网页上），里面存有所有的源文件、标准规范文件、结果文件等等，每个人都能实时看到里面的变化，实现了最基本的信息沟通的便捷性和透明性。
- 同时，每个人可以fork和clone主仓库，分别在各自的仓库中工作，并且可以随时通过Git命令保持本地仓库和主仓库的同步，实现了多线程工作和信息同步两者的一致。
- 成员完成工作后，通过pull request提交工作成果，负责人再通过merge合并大家的成果，工作区、暂存区、主仓库明确区分，避免了不同步骤中文件的混乱。
- 每一次pull request操作自带Assignee、Reviews、Lable等标签，可以用作每一份待翻译文件的状态码，标志负责的译员、审校，大家也可以实时看到工作安排，降低沟通成本和记录成本。
- 使用Git版本控制协议管理工作过程，每次内容增删改、文件合并都有记录并且可以随时查看、恢复，方便回溯。

# 优秀项目学习

[translation](https://github.com/SwiftGGTeam/translation.git)：SwiftGG翻译团队翻译规范

[The Swift Programming Language](https://github.com/SwiftGGTeam/the-swift-programming-language-in-chinese.git)：中文版 Apple 官方 Swift 教程

[android-training-course-in-chinese](https://github.com/Bingxin2779/android-training-course-in-chinese.git)：Android官方培训课程中文版

上面第一个是一个团队的翻译管理仓库，不是具体的项目，但是规范了在他们所有项目中都需要遵守的规范；第二和第三个是具体的翻译项目。

GitHub上的翻译项目都有不同的管理方式，我觉得自己建立项目的时候一方面要广泛学习优秀项目，另一方面要充分考虑自己项目的规模、是否众包、发布方式等因素，具体制定符合自己需求的体系。

# 其他学习资料

[专为设计师而写的GitHub快速入门教程](http://developer.51cto.com/art/201407/446249_all.htm)

[“不可不学是编程，不可不用是git” | git篇](https://mp.weixin.qq.com/s?__biz=MzI0MjMyNDcwMQ==&mid=2247483713&idx=1&sn=c69fdb391a180bebe717f0129831b1fd&scene=21#wechat_redirect)

[“不可不学是编程，不可不用是git” | github篇](https://cloud.tencent.com/developer/article/1198828)

[Markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed)

