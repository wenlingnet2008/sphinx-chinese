## 纯PHP编写的xdb词典
(SCWS - http://www.ftphp.com/scws 所采用)导入导出工具！！

### 1. 词典导出：dump_xdb_file.php
```bash
$ php dump_xdb_file.php <要导出的.xdb文件> [存入的文本文件]
```

   第二参数省略则直接输出到标准输出。

### 2. 词典生成：make_xdb_file.php 
需要安装 mbstring 扩展，目前只支持utf8
```bash
$ php make_xdb_file.php <要生成的.xdb> [导入的文本文件]
```

### 3. 词典格式说明
关于文本文件的说明，每行一条记录，每条记录由
word、TF、IDF、Attr组成，其中TF是词频系数，IDF是逆词频率系数，而Attr是北大标注法的词性
可参考 http://www.xunsearch.com/scws/docs.php#attr ，这四个字段之间用制表符(\t)或者空格符( )隔开。


```bash
#<词>  <词频(TF)>  <词重(IDF)>  <词性(北大标注)>
新词条 12.0        2.2          n
```

--
hetal 20170428 ,修正导出的排序问题，同时修正导出时词性显示问题，默认只支持utf8编码
hightman.20100304: 修正导出时的一个 bug 导致一堆出错信息..
hightman 特别制作于 2009.7.1
