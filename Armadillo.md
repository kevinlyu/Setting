# Ubuntu Install Armadillo
安裝 Armadillo 之前需要先安裝一些 denpency 的 package
- CMake
- LAPACK, BLAS, ARPACK and ATLAS 

詳細可以查看官方的 [github](https://github.com/lsolanka/armadillo)

## Install depency 
官方主要推薦的是 LAPACK 與 BLAS

` sudo apt-get install libopenblas-dev liblapack-devlanguage
`

## Install Armadillo

先到 [官方](http://arma.sourceforge.net/) 下載
```
tar -Jxvf armadillo-7.600.1.tar.xz

# 接著編譯
cmake .
make

＃ 安裝
sudo make install

#  If you don't have root/administrator/superuser privileges, 
#  type the following command:
#   make install DESTDIR=my_usr_dir
```
