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

<br></br>
<br></br>
<span style="font-size:16px; color:gray;">~~�����ָ������Ը��ֵ�README�ļ��ı�д˳��չ����ʵ��д��ʱ���ǰ���ʱ����Ǻ�~~  </span>

�������ã�(������)

## **Data Preparation**
![С������Ҫѧϰ�Ļ��кܶ࣬downloadһ�����ݼ��͹����������hh](../OVD_files/TOOL_img/large_scale.png)

### 2D
- [ ] ScanNet 3D (point clouds with GT semantic labels) <span style="font-size:12px; color:gray;">~~�����˲�����~~</span>

- [ ] ScanNet 2D (RGB-D images with camera poses) <span style="font-size:12px; color:gray;">~~�����˲����� 
�ҷ����� ������������֮��û��check�Ƿ��ѹ�ɹ� ��ֱ��ɾ����hh ������������������...~~</span>

- [x] Matterport 3D (point clouds with GT semantic labels) 
  ֻ����һ���ɹ�

- [ ] Matterport 2D (RGB-D images with camera poses) <span style="font-size:12px; color:gray;">û��ѹ�ɹ�  ��ͬ������ �г�����</span>

### 3D
- [ ] ScanNet - Multi-view fused OpenSeg features, train/val (234.8G) �����¸о�����

- [ ] Matterport - Multi-view fused OpenSeg features, train/val (198.3G) <span style="font-size:12px; color:gray;"> ~~����ɾ��һ�������� </span>
  
- [ ] Matterport - Multi-view fused OpenSeg features, test set (66.7G) ��ѹ����������������鿴����

- [x] Replica - Multi-view fused OpenSeg features (9.0G)

- [ ] nuScenes - Multi-view fused OpenSeg features (coming) 
<span style="font-size:12px; color:gray;">�����й��������ݼ��� ����Ŀǰ��������ʵ����Ϊ���ݼ�̫�� ��������ʱ��Ҳ���Թ��� ��Ȼ���ǿ����о�һ�����ݵ�pre process��ɶ���ӵ�����ô������Ҳ�ܲ�����</span>


?�����������Լ��Ľű��ϵ�(-c)���ػ��ǻ���������ļ��ṹ���������޷���ѹ����� ����remake... ������˺ü�ƪ���Ӷ�û�н��׼���Ƹ�����hh
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

**Trial1��** ���ýű������öϵ����أ� ���ص�����ļ��У� �������Ѿ���ʼ�����ǲ��Ƕϵ������ ���������� ����matterport_3d���������ģ� ~~ֱ�������أ��о����ֻ��������С���ݼ�ѽ��  
**Trial2��** ѹ����transfer������   
**Trial3��** ��û��ʼֱ��ȥ���������ٴ��䣿����    �ߣ���������������~~
```bash
# no -c 
wget https://cvg-data.inf.ethz.ch/openscene/data/scannet_processed/scannet_2d.zip 
```



### Unzip ��ѹ����Ŀǰ�����˴��� ���������������һ�����ع���
`tar -xvzf` �� `tar -xvf` ����
- ʹ�� `-z` ʱ������������ `.tar.gz` �� `.tgz` �ļ���
- ��ʹ�� `-z` ʱ��������������ͨ�� `.tar` �ļ���

`jar` �� `tar` ����
- jar ������Ҫ���ڴ��� Java ��صĹ鵵�ļ���֧�� .zip ��ʽ��
- tar ����ͨ�����ڴ��� Unix/Linux ϵͳ�е� tar �鵵�ļ���֧�� Gzip ѹ����ʽ��

1. **`tar -xvzf`**��
   - `-x`����ѹ����
   - `-v`����ʾ��ϸ�����verbose�����г����ڽ�ѹ���ļ���
   - `-z`��ͨ�� `gzip` ���н�ѹ���������� `.tar.gz` �� `.tgz` �ļ���
   - `-f`���������Ҫ�������ļ�����

2. **`tar -xvf`**��
   - `-x`��`-v` �� `-f` ѡ��ĺ�����������ͬ��
   - ���������� `-z` ѡ����������δ���� `gzip` ѹ���� `.tar` �ļ���

```bash
# gunzip file.tar.gz
# the - symbol before options is optional
tar -xvf file.tar
jar xvf xxx.zip
```

?���Ƕ����ң�������������� ��զ�� ����һȦҲû�ҵ�������� �ؿ���hh
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

### ���ع���-1 **`aria2c`** ʹ������������ص�ʱ�������������...
 `aria2c`��һ���������Ķ�Э��Ͷ�Դ���������ع��ߣ�֧�� HTTP/HTTPS��FTP��BitTorrent �ȶ���Э�顣���ǳ��ʺ��ڸ�Ч���ش��ļ��������ǵ�����Ҫ�Ӷ��Դͬʱ����ʱ��


```bash
aria2c -x 16 -s 16 -o autodl-tmp/os/data/scannet_multiview_openseg.zip https://cvg-data.inf.ethz.ch/openscene/data/scannet_multiview_openseg.zip


------------------------------------------------------------
*** Download Progress Summary as of Sat Oct 26 12:39:51 2024 ***                                 
[#9ae434 5.9GiB/169GiB(3%) CN:16 DL:1.8MiB ETA:24h34m48s]
FILE: /root/autodl-tmp/os/data/scannet_multiview_openseg.zip
------------------------------------------------------------
```
- **���� (5.9GiB/169GiB(3%))**���ļ��ܴ�СΪ 169GB��Ŀǰ�Ѿ������� 5.9GB���൱�� 3% ����ɶȡ�
- **������ (CN:16)**����ʾ��ǰʹ�� 16 �������������������ݡ�
- **�����ٶ� (DL:1.8MiB)**�������ٶ�Ϊ 1.8MB/s��
- **ʣ��ʱ�� (ETA:24h34m48s)**��Ԥ�ƻ��� 24 Сʱ 34 ���� 48 ��������ء�   
     

![���Ǻ���ʲôʱ����ô��ԣ����](../OVD_files/TOOL_img/download.png)
#### ����ѡ�����

- `aria2c`������ `aria2` �������пͻ��ˡ�
  
- `-x 16`���������������Ϊ 16������ζ�� `aria2` �᳢��ͨ�� 16 �����������������ļ����Ӷ���������ٶȡ�

- `-s 16`������ÿ�������������ֿ���Ϊ 16������ζ�� `aria2` ����ļ��ֳ� 16 �����ֲ�ͬʱ������Щ���֡�

- `-o autodl-tmp/os/data/scannet_multiview_openseg.zip`��ָ������ļ������ƺ�·�������ｫ���ص��ļ�����Ϊ `scannet_multiview_openseg.zip`�������� `autodl-tmp/os/data/` Ŀ¼�¡�

#### ��������ѡ��

- `-d <directory>`��ָ�������ļ���Ŀ¼��
- `-j <number>`������ͬʱ���ص��ļ�������
- `--continue`������δ��ɵ����ء�


### ���ع���-2 **`bypy`** ������?...
�������������ס����ס���Ժ���9.9����ȯȥ���㿴����
![���ҹ���ش��ڰٶ����̵����ݼ����Ǳ�Ӳ����hh](../OVD_files/TOOL_img/bypy.png)

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

3. **`�޸���CLIPģ�͵Ļ���·�������ѿռ�`**
   ![�޸���CLIPģ�͵Ļ���·�������ѿռ�](../OVD_files/TOOL_img/CLIP_cache_path.png)

4. ����ѹ�Ƿ�����/�ظ��Ľű�
   �������䣩



## **Unsolved**
���࿨ѵ������λ��������autodl �ҿ������ſ� ��ͬһ��ģ�� ��ͬ���ݼ� ��ͬterminal�� gpu���������ݼ���Ӧ�Ľű����涼һЩ��Ϊ��0 1 2����ʵ�ʵ��õ�ʱ���ֶ����ǵ��õ�gpu0���³�ͻ kill

������ͬһ��ģ�Ͳ������������ݼ�����ѵ�����Ǵ����������� Ŀǰdebug����������õ���gpuûɶ������ˣ�


## **BOX**
�ǵĺö�markdown�﷨��һ��Ҳ�ǲ�ס   
Adds support for Github's - [ ] and - [x] check box syntax to VS Code's built-in markdown preview.  
Adds - [ ] and - [x] checkbox rendering Markdown cells in notebooks.  


- [ ] ����Ҫ�����ֲŻ���Ⱦ����
- [x] �������ֻ�ܺ�̨���ֻ����ֶ�Ŷ




