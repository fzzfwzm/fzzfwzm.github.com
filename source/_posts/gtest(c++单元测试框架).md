title: gtest(c++单元测试框架)学习使用
date: 2014-07-12 14:54:29 
categories: 实习记录 
---
### gtest 介绍
开源，多平台 c++ 单元测试框架
[下载地址](http://code.google.com/p/googletest/)

#### 配置使用
我的环境：win7+vs2010，(此非教程，仅为配置和学习记录)           
1.下载后解压，找到msvc目录，如下:(上传此图片仅作测试七牛云储存)  
![](http://blogpict.qiniudn.com/gtest_1_msvc.png)     
2.然后用vs打开sln文件，编译工程
3.用编译gtest的同版本的vs新建一个win32工程，作为测试工程  
4.在项目->属性->配置属性->c/c++->常规 添加包含目录，包含gtest解压文件后的inlcude目录                       
5 添加动态链接库路径，包含之前编译过的gtest可执行程序目录，
 例如：..\gtest-1.7.0\msvc\gtest\Debug 
  链接器，输入，附加依赖项中加入gtestd.lib 
 ![](http://blogpict.qiniudn.com/gtest_3_depend.PNG)         
6 更改运行时库为/MTD
![](http://blogpict.qiniudn.com/gtest_2_rtime.PNG)

7 简单测试代码如下
```` cpp
#include<cstdlib>
#include "gtest/gtest.h"
#include "CustomString.h"

TEST(StringTest,stringSize)
{
	CustomString<char> a("123");
	EXPECT_EQ(3, a.size());
}


int main(int argc, char **argv)
{
	
	testing::InitGoogleTest(&argc, argv);
	RUN_ALL_TESTS();
	system("pause");
	return 0;
}
````
8 结果
![](http://blogpict.qiniudn.com/gtest_4_ans.PNG)


