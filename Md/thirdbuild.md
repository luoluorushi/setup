### curl
1. 设置环境变量

```
export CFLAGS=-mmacosx-version-min=10.9
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/Cellar/openssl/1.0.2o_2/lib/ 
```

```
./configure --prefix=/Users/luoluorushi/Tmp/curl2 --with-ssl=/usr/local/Cellar/openssl/1.0.2o_2 CC=clang --without-winidn --without-libidn2 --with-zlib --disable-ldap --disable-ldaps
```
### boost

```
./b2 -a cxxflags="-stdlib=libc++ -std=c++11 -mmacosx-version-min=10.9"
```
