在Linux上进行上传下载时很容易就会用到压缩和解压操作，其中用的较多的算是tar命令了，其他命令也可以了解下。

### gzip/gunzip命令

**gzip 文件：**以.gz格式压缩文件。压缩完成后文件名默认是以.gz结尾的（但是注意Linux中是没有后缀名一说的）。

**gunzip 压缩文件：**解压.gz格式的压缩文件。

**注意：**gzip只能压缩文件，不能压缩目录，所以对于目录通常是先打包成一个文件，如tar文件，然后再压缩成gz文件，如“xxx.tar.gz”。并且压缩文件或者解压文件之后原文件会被删除，不会保留原文件（跟Windows不同）。

### bzip2命令

**bzip2 选项 文件：**以.bz2格式压缩文件，压缩后的文件名默认以.bz2结尾。它实际上是gzip命令的一个升级版，不仅提供了保留原文件的选项，它的压缩比也比.gzip高很多，所以适用于压缩那些比较大的文件。

**bunzip2 选项 压缩文件：**以.bz2格式解压文件。

压缩或解压选项：

* **-k：**保留原文件。gzip命令产生压缩文件后或解压后不会保留原文件。

**注意：**bzip2只能压缩文件，不能压缩目录，所以对于目录通常也是先打包成一个文件再进行压缩。

### tar命令

**tar 选项 压缩后文件名 目录：**打包压缩一个目录。如以.tar.gz结尾的压缩文件，其中tar表示生成的打包文件，gz表示将打包的文件进行压缩。

常用压缩格式：

* **tar -czf 压缩后文件名 目录：**以.gz格式打包压缩一个目录。
* **tar -cjf 压缩后文件名 目录：**以.bz2格式打包压缩一个目录。

常用压缩选项：

* **-c：**打包并生成一个打包文件。
* **-v：**显示详细信息。
* **-f：**指定文件名。
* **-z：**以.gz格式压缩文件。
* **-j：**以.bz2格式压缩文件。

常用解压格式：

* **tar -xvf 压缩文件名：**解压一个压缩文件。除了zip格式的压缩文件，其实在新版本Linux中，大多压缩格式，tar命令已经可以自动识别了，不用手动指定压缩格式，直接进行解压即可。
* **tar -xzvf 压缩文件名：**以.gz格式解压一个压缩文件。
* **tar -xjvf 压缩文件名：**以.bz2格式解压一个压缩文件。
* **注：**默认解压后的文件或目录存放在当前目录中。

常用解压选项：

* **-x：**解包文件。
* **-v：**显示详细信息。
* **-f：**指定需要解压的文件。
* **-z：**以.gz格式解压文件。
* **-j：**以.bz2格式解压文件。

### zip/unzip

命令

**zip 选项 压缩后文件名 文件或目录：**以.zip格式压缩文件或目录。相较于.gz格式的压缩，.zip压缩完成后会保留原文件，但是压缩比是低于.gz的。

选项：

* **-r：**压缩目录。

**unzip 压缩文件名：**以.zip格式解压文件。

**注：**在Windows上打包压缩成zip格式的文件，上传到Linux上也可以使用unzip命令解压，但是里面如果有中文的话可能会乱码。
