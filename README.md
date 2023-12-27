# IOS版本的fftw单精度傅里叶变换库
编译平台mac
##编译傅里叶变换库教程
下载 FFTW 源代码：
从 FFTW 的官方网站下载源代码（FFTW 官方网站）
http://www.fftw.org/download.html
https://github.com/FFTW/fftw3

### 切换到 FFTW 源代码目录
cd /path/to/fftw/source

#### 创建用于 iOS 架构的构建目录
mkdir build_ios
cd build_ios

cmake .. \
  -DCMAKE_SYSTEM_NAME=iOS \
  -DCMAKE_OSX_ARCHITECTURES=arm64 \
  -DCMAKE_OSX_SYSROOT=iphoneos \
  -DCMAKE_C_COMPILER=/usr/bin/clang \    
  -DCMAKE_CXX_COMPILER=/usr/bin/clang++ \           
  -DBUILD_SHARED_LIBS=OFF \
  -DENABLE_FLOAT=ON

make -j8

//获取生成的静态库文件：
编译完成后，您可以在 build_ios 目录中找到生成的静态库文件（.a 文件）。
