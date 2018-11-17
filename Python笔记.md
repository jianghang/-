## Python笔记

1. python3 安装Scrapy报如下错误：

		build/temp.macosx-10.6-intel-3.6/_openssl.c:498:10: fatal error: 'openssl/opensslv.h' file not found
		
	同时这个错误是安装cryptography这个依赖包的报错，那可以先安装cryptography这个包，使用如下命令：
	
		pip install cryptography --global-option=build_ext --global-option="-L/usr/local/opt/openssl/lib" --global-option="-I/usr/local/opt/openssl/include"
		
	使用上面的命令的前提是已经安装了openssl，如果没有安装openssl可以使用如下命令安装：
	
		brew install openssl