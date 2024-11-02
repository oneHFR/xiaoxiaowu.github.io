# **Reproduction of OpenScene**

<!-- PROJECT LOGO -->

<p align="center">

  <h1 align="center"><img src="https://pengsongyou.github.io/media/openscene/logo.png" width="40">OpenScene: 3D Scene Understanding with Open Vocabularies CVPR 2023</h1>
  <h3 align="center"><a href="https://arxiv.org/abs/2211.15654">Paper</a> | <a href="https://youtu.be/jZxCLHyDJf8">Video</a> | <a href="https://pengsongyou.github.io/openscene">Project Page</a></h3>
  <div align="center"></div>
</p>
<p align="center">
  <a href="">
    <img src="https://pengsongyou.github.io/media/openscene/teaser.jpg" alt="Logo" width="100%">
  </a>
</p>
<p align="center">
<strong>OpenScene</strong> is a zero-shot approach to perform a series of novel 3D scene understanding tasks using open-vocabulary queries.
</p>
<br>

<!-- TABLE OF CONTENTS -->
<details open="open" style='padding: 10px; border-radius:5px 30px 30px 5px; border-style: solid; border-width: 1px;'>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#data-preparation">Data Preparation</a>
    </li>
    <li>
      <a href="#run">Run</a>
    </li>
    <li>
      <a href="#others">Others</a>
    </li>
        <li>
      <a href="#unsolved">Unsolved</a>
    </li>
    <li>
      <a href="#box">BOX</a>
    </li>
  </ol>
</details>


<span style="font-size:16px; color:gray;">~~下面的指令分类以复现的README文件的编写顺序展开？实际写的时候是按照时间轴呵呵~~  </span>

基本配置：(待补充)

## **Data Preparation**
![小吴你需要学习的还有很多，download一个数据集就够你喝两壶了hh](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/TOOL_img/large_scale.png?raw=true)

### 2D
- [ ] ScanNet 3D (point clouds with GT semantic labels) <span style="font-size:12px; color:gray;">~~下载了不见了~~</span>

- [ ] ScanNet 2D (RGB-D images with camera poses) <span style="font-size:12px; color:gray;">~~下载了不见了 
我发现了 是我昨天下载之后没有check是否解压成功 就直接删掉了hh 啊啊啊啊啊啊啊啊啊...~~</span>

- [x] Matterport 3D (point clouds with GT semantic labels) 
  只有这一个成功

- [ ] Matterport 2D (RGB-D images with camera poses) <span style="font-size:12px; color:gray;">没解压成功  相同的问题 有超出段</span>

### 3D
- [ ] ScanNet - Multi-view fused OpenSeg features, train/val (234.8G) 还在下感觉无望

- [ ] Matterport - Multi-view fused OpenSeg features, train/val (198.3G) <span style="font-size:12px; color:gray;"> ~~给我删了一部分晕了 </span>
  
- [ ] Matterport - Multi-view fused OpenSeg features, test set (66.7G) 解压不正常！！！报错查看下文

- [x] Replica - Multi-view fused OpenSeg features (9.0G)

- [ ] nuScenes - Multi-view fused OpenSeg features (coming) 
<span style="font-size:12px; color:gray;">好像有公开的数据集： 但是目前来看不切实际因为数据集太大 处理数据时间也难以估计 当然还是可以研究一下数据的pre process是啥样子的是怎么个事情也很不错！！</span>


?现在重新用自己的脚本断点(-c)下载还是会出现下载文件结构不完整，无法解压的情况 所以remake... 遍地搜了好几篇帖子都没有解决准备破釜沉舟hh
```bash
root@hostname:~/autodl-tmp/os# unzip matterport_2d.zip
Archive:  matterport_2d.zip
  End-of-central-directory signature not found.  Either this file is not
  a zipfile, or it constitutes one disk of a multi-part archive.  In the
  latter case the central directory and zipfile comment will be found on
  the last disk(s) of this archive.
unzip:  cannot find zipfile directory in one of matterport_2d.zip or
        matterport_2d.zip.zip, and cannot find matterport_2d.zip.ZIP, period.


root@hostname:~/autodl-tmp/os/data# unzip scannet_3d.zip
Archive:  scannet_3d.zip
warning [scannet_3d.zip]:  48103740 extra bytes at beginning or within zipfile
  (attempting to process anyway)
file #1:  bad zipfile offset (local header sig):  48103740
  (attempting to re-compensate)
error: invalid zip file with overlapped components (possible zip bomb)
```

**Trial1：** 不用脚本？不用断点下载？ 下载到别的文件夹？ 我现在已经开始怀疑是不是断点的问题 比如其他的 比如matterport_3d就是正常的？ ~~直接下载呢？感觉这个只能适用于小数据集呀？  
**Trial2：** 压缩包transfer到本地   
**Trial3：** 还没开始直接去本地下载再传输？下下    策！！！！！！！！~~
```bash
# no -c 
wget https://cvg-data.inf.ethz.ch/openscene/data/scannet_processed/scannet_2d.zip 
```



### Unzip 解压环节目前报道了错误 但是问题出现在上一个下载过程
`tar -xvzf` 和 `tar -xvf` 区别
- 使用 `-z` 时，命令适用于 `.tar.gz` 或 `.tgz` 文件。
- 不使用 `-z` 时，命令适用于普通的 `.tar` 文件。

`jar` 和 `tar` 区别
- jar 命令主要用于处理 Java 相关的归档文件，支持 .zip 格式。
- tar 命令通常用于处理 Unix/Linux 系统中的 tar 归档文件，支持 Gzip 压缩格式。

1. **`tar -xvzf`**：
   - `-x`：解压缩。
   - `-v`：显示详细输出（verbose），列出正在解压的文件。
   - `-z`：通过 `gzip` 进行解压缩，适用于 `.tar.gz` 或 `.tgz` 文件。
   - `-f`：后面跟着要操作的文件名。

2. **`tar -xvf`**：
   - `-x`、`-v` 和 `-f` 选项的含义与上述相同。
   - 这个命令不包含 `-z` 选项，因此适用于未经过 `gzip` 压缩的 `.tar` 文件。

```bash
# gunzip file.tar.gz
# the - symbol before options is optional
tar -xvf file.tar
jar xvf xxx.zip
```

?但是对于我，出现了这个报错 那咋办 查了一圈也没找到解决方法 重开！hh
```bash
java.util.zip.ZipException: invalid stored block lengths
	at java.base/java.util.zip.InflaterInputStream.read(InflaterInputStream.java:165)
	at java.base/java.util.zip.ZipInputStream.read(ZipInputStream.java:197)
	at java.base/java.util.zip.ZipInputStream.closeEntry(ZipInputStream.java:143)
	at jdk.jartool/sun.tools.jar.Main.extractFile(Main.java:1456)
	at jdk.jartool/sun.tools.jar.Main.extract(Main.java:1363)
	at jdk.jartool/sun.tools.jar.Main.run(Main.java:409)
	at jdk.jartool/sun.tools.jar.Main.main(Main.java:1680)

# try to fix it but ...
error:  invalid compressed data to inflate
file 5834:  bad zipfile offset (local header sig):  134739918053
file 5835:  bad zipfile offset (local header sig):  134794873562
file 5836:  bad zipfile offset (local header sig):  134817195917
```

### 下载工具-1 **`aria2c`** 使用这个并发下载的时候我真的流泪了...
 `aria2c`是一个轻量级的多协议和多源命令行下载工具，支持 HTTP/HTTPS、FTP、BitTorrent 等多种协议。它非常适合于高效下载大文件，尤其是当你需要从多个源同时下载时。


```bash
aria2c -x 16 -s 16 -o autodl-tmp/os/data/scannet_multiview_openseg.zip https://cvg-data.inf.ethz.ch/openscene/data/scannet_multiview_openseg.zip


------------------------------------------------------------
*** Download Progress Summary as of Sat Oct 26 12:39:51 2024 ***                                 
[#9ae434 5.9GiB/169GiB(3%) CN:16 DL:1.8MiB ETA:24h34m48s]
FILE: /root/autodl-tmp/os/data/scannet_multiview_openseg.zip
------------------------------------------------------------
```
- **进度 (5.9GiB/169GiB(3%))**：文件总大小为 169GB，目前已经下载了 5.9GB，相当于 3% 的完成度。
- **连接数 (CN:16)**：表示当前使用 16 个并行连接在下载数据。
- **下载速度 (DL:1.8MiB)**：下载速度为 1.8MB/s。
- **剩余时间 (ETA:24h34m48s)**：预计还需 24 小时 34 分钟 48 秒完成下载。   
     

![不是孩子什么时候那么富裕过？](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/TOOL_img/download.png?raw=true)
#### 命令选项解析

- `aria2c`：调用 `aria2` 的命令行客户端。
  
- `-x 16`：设置最大连接数为 16。这意味着 `aria2` 会尝试通过 16 个并发连接来下载文件，从而提高下载速度。

- `-s 16`：设置每个服务器的最大分块数为 16。这意味着 `aria2` 会把文件分成 16 个部分并同时下载这些部分。

- `-o autodl-tmp/os/data/scannet_multiview_openseg.zip`：指定输出文件的名称和路径。这里将下载的文件保存为 `scannet_multiview_openseg.zip`，并放在 `autodl-tmp/os/data/` 目录下。

#### 其他常用选项

- `-d <directory>`：指定下载文件的目录。
- `-j <number>`：设置同时下载的文件数量。
- `--continue`：继续未完成的下载。


### 下载工具-2 **`bypy`** 这个真的?...
但是朋友请你记住！记住！以后买9.9加速券去咸鱼看看！
![大半夜下载存在百度网盘的数据集还是被硬控了hh](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/TOOL_img/bypy.png?raw=true)

## **Run**

## **Others**
1. **`dos2unix`**  
   converts a text file from Windows (CRLF) line endings to Unix (LF) line endings.
```bash
dos2unix [file].sh
```

2. **`du -sh`**  
   The command `du -sh` shows the total disk usage of a directory in a human-readable format, like KB or MB.
```bash
du -sh
```

3. **`修改了CLIP模型的缓存路径到付费空间`**
   ![修改了CLIP模型的缓存路径到付费空间](https://github.com/oneHFR/xiaoxiaowu.github.io/blob/main/OVD_files/TOOL_img/CLIP_cache_path.png?raw=true)

4. 检查解压是否完整/重复的脚本
   （待补充）



## **Unsolved**
【多卡训练】各位有遇到过autodl 我开了三张卡 跑同一个模型 不同数据集 不同terminal下 gpu在三个数据集对应的脚本里面都一些改为了0 1 2但是实际调用的时候发现都还是调用的gpu0导致冲突 kill

是这种同一个模型不能这样分数据集并行训练还是代码有问题呢 目前debug代码里面调用的我gpu没啥问题怪了！


## **BOX**
是的好多markdown语法我一点也记不住   
Adds support for Github's - [ ] and - [x] check box syntax to VS Code's built-in markdown preview.  
Adds - [ ] and - [x] checkbox rendering Markdown cells in notebooks.  


- [ ] 后面要加文字才会渲染出来
- [x] 这个不是只能后台体现还能手动哦




