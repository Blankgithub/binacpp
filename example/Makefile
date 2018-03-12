



libcurl_dir=../lib/libcurl-7.56.0
libcurl_include=${libcurl_dir}/include
libcurl_lib=${libcurl_dir}/lib

jsoncpp_dir=../lib/jsoncpp-1.8.3
jsoncpp_include=${jsoncpp_dir}/include
jsoncpp_src=${jsoncpp_dir}/src


libwebsockets_dir=../lib/libwebsockets-2.4.0
libwebsockets_include=${libwebsockets_dir}/include
libwebsockets_lib=${libwebsockets_dir}/lib

libbinacpp_dir=../lib/libbinacpp
libbinacpp_include=${libbinacpp_dir}/include
libbinacpp_lib=${libbinacpp_dir}/lib



%: %.cpp
	@echo -n "\nMaking $@\n\n\n"
	g++ -I$(jsoncpp_include)  -I$(libbinacpp_include) \
	$@.cpp \
	-L$(libbinacpp_lib) \
	-I/usr/local/opt/openssl/include -L/usr/local/opt/openssl/lib \
	-lcurl -ljsoncpp  -lcrypto -lwebsockets -lbinacpp -o $@

	cat run.template.sh  | sed s/%executable%/$@/ > $@.run.sh
	chmod 755 $@.run.sh


