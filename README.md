# FileManagement 


[![Travis](https://img.shields.io/travis/Sandiagal/DoujinFix.svg?style=flat-square&label=Travis+CI)](https://travis-ci.org/Sandiagal/DoujinFix)
[![AppVeyor Build Status](https://img.shields.io/appveyor/ci/Sandiagal/DoujinFix.svg?style=flat-square&label=AppVeyor&logo=appveyor)](https://ci.appveyor.com/project/Sandiagal/doujinfix/branch/master)
[![LICENSE](https://img.shields.io/github/license/Sandiagal/DoujinFix.svg?style=flat-square)](https://github.com/Sandiagal/DoujinFix/blob/master/LICENSE)
[![Code Quality](https://api.codacy.com/project/badge/Grade/bafffe84e9ac4c8dbb085fbf212b7097)](https://www.codacy.com/app/Sandiagal/DoujinFix?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Sandiagal/DoujinFix&amp;utm_campaign=Badge_Grade )

[download-badge]: https://img.shields.io/github/downloads/Sandiagal/DoujinFix/total.svg?style=flat-square "Download status"

一款集合了同人志文件名标准化和文件替换功能的便于批量整理同人志的软件。

![001](assets/001.jpg)

## 简介

该软件是一款集合了同人志文件名标准化、图像压制和文件替换功能的便于批量整理同人志的软件。

由于国内的二次创作领域存在诸多“吃力不讨好”的现象，同人志在分享时存在名称中乱加标签的问题，加之专用名词的不统一，不规范的问题，给同人志的整理和收藏带来了不小的困难。此外，部分同人志的图片质量过好体积巨大，不利于整理，故经常需要进行压制。但图片的分享存在编码和质量不统一的问题，在压制后需要对体积压缩结果进行对比，费时费力。对此，为了能更方便的整理同人志，需要一款软件来解决上述问题。

以下将按照“名称标准化”和“压缩图像替换”的顺序介绍该软件。

如果想了解该软件的更多信息，或者报告Bug，可以联系编者。

邮箱：sandiagal2525@gmail.com

## 名称标准化

### 内容介绍

要解释什么是名称标准化，就要先解释什么是“标准”。按照所见即所得的思路，目前最规范而全面的标准应该来自于 [E-Hentai Galleries](https://ehwiki.org/wiki/Renaming)。其格式可以概括为：

>   (即卖会名) \[社团名 (作者名)] 标题 (原作名) \[语言] \[译者]\[特殊标示]
>
>   (例大祭7) \[武蔵堂 (ムサシノセカイ)] マッシュルーム・サンバ (東方Project) \[英訳] \[DL版]

前面几项可以顾名思义，有则标注，无则缺省。而末尾的几项则需要一定经验性的解释。“\[语言]”只有在不使用同人志常用语言（日语、英语和汉语）时才会标注。“\[译者]”在主标题中一般只标注使用语言，例如“英訳”和“中国翻訳”；而在副标题才中会注明组织，例如“雅哥个人汉化”。“\[特殊标示]”则包括"ページ欠落"和"DL版"等非固定标示。

但是对于不同的发布渠道和收藏来说，其实用不到这么全面的格式。比如只针对特定语言的渠道，就不需要专门标注“\[语言]”；追求完整系列的人，也不会收集"ページ欠落"的作品。此外，部分发布渠道还会将“\[译者]”提到最前，以示对其工作的尊敬。而对个人而言，“(即卖会名)”的标签有些赘余。原本它可以便于搜索和记录作者的制作时间。但在实际中却存在多种体系，比如“Comiket”和“例大祭”等。全部使用一套体系还好，但混合使用则达不到按照时间排列的效果。

以上命名标准本身并无问题，但一旦混合出现，就难免造成麻烦。要收集大量同人志不可能只关注一个渠道，而不同渠道发布的同人志显然都有各自的标准。而且还有部分渠道的标准过于独特，自立门户。所以将这些同人志放在一个文件夹里，未免有些过于难堪。所以我们需要一款能够将不同同人志的名称修改到统一标准的软件。

### 功能说明

- 命名格式

   - 目前提供以下3种标准
   - 特别标示 \[社团名 (作者名)] 标题 (原作名) \[译者]
   - 特别标示 (即卖会名) \[社团名 (作者名)] 标题 (原作名) \[语言] \[译者]
   - 特别标示 (即卖会名) \[译者] \[社团名 (作者名)] 标题 (原作名) \[语言]

-   基本调整

   - 邻接连续空格只保留一个。
   - 每一项内容之间严格保持一个半角空格的间隔。
   - 所有类型的括号统一为半角形式。
   - 去掉“DL版”、“無修正”、“中国語”、“中国翻訳”、“オリジナル”等标识。
   - 将“～”和“(Various)”分别调整为“~”和“(よろず)”。
   - 无毒、CE和空気系等译者的各种署名分别统一为“无毒汉化组”、“CE家族社”和“空気系☆漢化”。

- 原作映射

   - “(原作名)”全部映射到原作发布时的官方名称。比如“東方”映射为“東方Project”、“KanColle”映射为“艦隊これくしょん -艦これ-”。
   - 若官方名称完全由片假名构成，则映射为对应的英文，比如“ラブライブ”映射为“Love Live!”、“アイドルマスター”映射为“THE IDOLM@STER”。
   - 具体映射关系可以自定义，关系表位于软件根目录下的“parodyMap.txt”中。每两行每一组，从第一行映射到第二行。若存在多组映射关系，则选取匹配度最大的一组，比如“オンライン”更匹配“ラグナロクオンライン”，而不是“ソードアート・オンライン”。

- 序号优化

   - 每一张图片的名称都_尽量_修改为三位数字，比如“00019_18”修改为“019”、“IMG_9”修改为“009”。
   - 保留无毒、CE等译者的特定格式，但去掉重复数字，比如“05_MJK_12_T345_005”修改为“MJK_12_T345_005”。

- 特别标示

   - 在名称上添加特殊标示，以便提示_手动_处理有以下该软件无法解决的问题。
   - 未知译者★：存在“中国翻訳”而缺失“\[译者]”时，用户需要自行查阅相关资料来添加“\[译者]”。
   - 低质图像▼：大部分图片的分辨率过低时，提醒用户可能下载了压缩档，需要更新图源。

- 运行模式

   - 极速运算：满速运行算法，界面会卡顿。
   - 流畅交互：限速运行算法，界面很流畅。
 
特别说明以上功能专门为“同人志”设计，请勿用在“同人声音”、“同人游戏”等文件。如果处理对象为“漫画”，则会将“\[杂志名]”按照“即卖会名”处理。

### 使用方法

- 1、指定“源头目录路径”

  ![slide](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/2.jpg) 
  
该目录下应该存放多个文件夹，其名称需要符合上述3个标准下的同人志。

- 2、指定“目标处理格式”

  ![slide](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/3.jpg) 

- 3、点击“名称标准化”

  ![slide](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/4.jpg)

处理进度位于“名称标准化”按钮右侧，处理结果实时显示于下方文字区。

品红色表示处理成功；黑色表示文件名已经标准，不用处理；橙色表示处理失败，失败信息将显示于下方；蓝色是处理开始于结束的标记，最下方将显示处理成功文件的个数。

如果对处理结果不满意，可以点击“名称标准化”按钮右侧的“撤销”按钮。

## 图像压制

### 内容介绍

部分同人志的图片质量过好体积巨大，不利于整理，故经常需要进行压制。	软件内实际并没有压制图像的功能，由于市面上压制图像的软件很多，所以笔者觉得没有必要单独编写压制的程序，故此部分将调用外部软件进行处理，一般用户忽略该单元即可。

## 文件替换

### 内容介绍

同人志图片的分享存在编码和质量不统一的问题，在采用特定压制算法后体积并不一定会缩小。为了获得实际缩小的图片，需要对体积压缩结果进行对比。然后用符合标准图片替换原始图片，以达到压缩整体文件的目的。

### 注意事项

该单元操作无法撤销，如果担心意外损失，请自行备份源文件，或不要使用该功能。

请保证每个同人志文件夹内只有图片文件，为了便于处理，程序会自动删除带有".torrent", "Thumbs.db", ".xehdone", ".url"的文件。为了避免意外损失，程序会在文件数量不一致时停止。

### 使用方法

- 1、必须先经过“文件名标准化”和“图像处理”处理。

- 2、指定“目标目录路径”

  ![](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/5.jpg) 

“目标目录路径”为“图像压制”后图像存放的目录，该路径下内文件格式应当与源头目录路径下文件格式完全相同。

- 3、设置“%阈值”

  ![](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/6.jpg) 

当压制后的图片大小缩小了3%以上时，才认为“图像压制”的结果足够好，可以用于“文件替换”。

- 4、点击“文件替换”

  ![](https://raw.githubusercontent.com/Sandiagal/DoujinFix/master/old_version/2.4/image/7.jpg) 

处理进度位于“文件替换”按钮右侧，第一栏是总体文件处理进度，第二栏是单一文件夹内处理进度；处理结果实时显示于下方文字区。

品红色表示处理成功；并在下方显示处理成功文件数和减少的体积；蓝色是处理开始于结束的标记，最下方将显示总处理成功文件的个数和减少的总体积。

“重开”按钮用于开启下一轮文件处理。


