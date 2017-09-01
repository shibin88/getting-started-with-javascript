### Lesson6作业思路

- 作业需求：读取指定路径的文件内容，并将其名称写入到指定路径的TXT文件中


- 异步思路：首先需要调用fs模块的两个子函数，一个是readdir()，一个是writeFile()。

​            相比同步函数readdirSync()，异步readdir()可以构建一个callback用于接收读取指定路径得到的内容和结果；

​            相比同步函数writeFileSync（），异步writeFile()可以判断写入的结果。

​            最初本来是想着按照做菜的思路，构建一个读函数，一个写函数和一个调度函数。但实操过程发现很麻烦，不如在函数末尾直接调用`fs.readdir(dirPathString, readOutcome);`来的清晰。

- 感想

​            真正去构建函数时，才发现思路真的很重要，也很难。知道的函数库足够多，才能实现更多的功能，在需要的时候才能知道去哪里找出自己需要用到的模块。就好比在代码成功运行第一次之后，发现TXT文件是一大长串，借鉴了一下LiuLiyuan同学的作业，才找到了把每个名字回车的办法。我自己也添加了一个小的method，用来把字符串统一改成小写格式，能更美观一些。

- 期待

想要在将来能实现更多的功能：

比方说阅读readdir() 这个模块的介绍时，看到<u>fs.readdir(path[, options], callback)</u>path还可以是URL（网址），如果这样，是不是就可以把path改成网址保证每次写入的文件都是最新最全的呢？

比方说如何把TXT里边的系统文件如：'.git' / '.gitignore'给屏蔽掉呢？


