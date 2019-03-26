下载文件
```
wget -c https://github.com/biod/sambamba/archive/v0.6.9.tar.gz
tar -zxvf sambamba-0.6.9.tar.gz
cd sambamba
make
```
这个时候可能会报错
```
python3 ./gen_ldc_version_info.py  > utils/ldc_version_info_.d
Makefile:68: recipe for target 'utils/ldc_version_info_.d' failed
make: *** [utils/ldc_version_info_.d] Error 1
```
这是因为没有安装ldc这个库，那么就先来安装ldc这个库
```
wget -c https://github.com/ldc-developers/ldc/releases/download/v1.15.0-beta2/ldc2-1.15.0-beta2-linux-x86_64.tar.xz
tar -Jxvf ldc2-1.15.0-beta2-linux-x86_64.tar.xz
cd ldc2-1.15.0-beta2-linux-x86_64/lib
echo "export PATH=`pwd`:$PATH" >>~/.bashrc
source ~/.bashrc
```
然后再来安装sambamba
```
make
cd bin
echo "export PATH=`pwd`:$PATH" >>~/.bashrc
source ~/.bashrc
```
