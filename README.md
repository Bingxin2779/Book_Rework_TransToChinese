# Book_Rework_TransToChinese
英文原版书《Rework》中文翻译项目

**此项目为“翻译技术原理与实践”课程讨论题实验项目，模拟英文原版书翻译团队，目的为学习GitHub和Git在翻译项目管理中的用法，仅作学习用途**

## 当前版本

version1.0  2019/10/24更新

## 译者工作流程简述

1. Fork 该仓库到自己的 GitHub 账号
2. Clone 自己的的仓库到本地
3. 添加本主仓库为另一个远程，实现本地仓库与主仓库的同步

   git remote add upstream https://github.com/Bingxin2779/Book_Rework_TransToChinese.git
  
4. 在本地仓库新建分支完成自己的文章翻译/校对并提交到自己的仓库
5. 在自己的仓库中点击 New pull request ，即发起提交请求
6. 如果需要根据校对意见进行修改，则修改后再 Commit -> Pull Request
7. 在开始翻译前同步本主仓库的更改，此时依次运行命令：

    git fetch upstream

    git checkout master 

    git merge upstream/master

由于本人经验不足，无法形成完整、合理的翻译流程，推荐参考[SwiftGGTeam项目的翻译流程详细说明](https://github.com/SwiftGGTeam/translation/blob/master/%E7%BF%BB%E8%AF%91%E6%B5%81%E7%A8%8B%E8%AF%A6%E7%BB%86%E8%AF%B4%E6%98%8E.md)
 
## 工作规范

1. [格式规范](https://github.com/Bingxin2779/Book_Rework_TransToChinese/blob/master/FormatRequirements.md)

2. 内容规范
- [语言风格规范](https://github.com/Bingxin2779/Book_Rework_TransToChinese/blob/master/LanguageStyle.md)
- [术语表](https://github.com/Bingxin2779/Book_Rework_TransToChinese/blob/master/Terminology.md)

## 贡献者

……
……

