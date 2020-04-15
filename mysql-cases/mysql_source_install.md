# 目标
解决系统软件管理工具(yum/apt)安装后，会分散在系统既定目录下不便于统一管理；
# 环境
1. 系统版本及内核：`Ubuntu 16.04.6 LTS 4.13.16-041316-generic x86_64 x86_64 x86_64 GNU/Linux`
2. MySQL版本：[percona-server-5.7.25-28.tar.gz](https://www.percona.com/downloads/Percona-Server-5.7/Percona-Server-5.7.25-28/source/tarball/percona-server-5.7.25-28.tar.gz)
3. 依赖库：`yum: gcc gcc-c++ pcre pcre-devel openssl openssl-devel/ zlib zlib-devel cmake ncurses ncurses-devel bison bison-devel/ perl perl-devel autoconf[apt-get: gcc g++ libpcre3-dev openssl libcurl4-openssl-dev/ cmake ncurses-base libncurses5-dev bison libbison-dev/ perl libperl-dev autoconf/ libreadline-dev zlib1g zlib1g-dev libpam0g=1.1.8-3.2ubuntu2.1 libpam0g-dev]`
# 步骤
1. 依赖安装：

a. `apt-get install  gcc g++ libpcre3-dev openssl libcurl4-openssl-dev`
```
# apt-get install  gcc g++ libpcre3-dev openssl libcurl4-openssl-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
g++ is already the newest version (4:5.3.1-1ubuntu1).
gcc is already the newest version (4:5.3.1-1ubuntu1).
openssl is already the newest version (1.0.2g-1ubuntu4.15).
The following additional packages will be installed:
  libcurl3 libpcre16-3 libpcre32-3 libpcrecpp0v5
Suggested packages:
  libcurl4-doc libcurl3-dbg libidn11-dev libkrb5-dev libldap2-dev librtmp-dev libssl-dev
  pkg-config zlib1g-dev
The following NEW packages will be installed:
  libcurl3 libcurl4-openssl-dev libpcre16-3 libpcre3-dev libpcre32-3 libpcrecpp0v5
0 upgraded, 6 newly installed, 0 to remove and 6 not upgraded.
Need to get 1,269 kB of archives.
After this operation, 5,342 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial/main amd64 libpcrecpp0v5 amd64 2:8.38-3.1 [15.2 kB]
Get:2 http://*/ubuntu xenial-updates/main amd64 libcurl3 amd64 7.47.0-1ubuntu2.13 [186 kB]
Get:3 http://*/ubuntu xenial-updates/main amd64 libcurl4-openssl-dev amd64 7.47.0-1ubuntu2.13 [263 kB]
Get:4 http://*/ubuntu xenial/main amd64 libpcre16-3 amd64 2:8.38-3.1 [144 kB]
Get:5 http://*/ubuntu xenial/main amd64 libpcre32-3 amd64 2:8.38-3.1 [136 kB]
Get:6 http://*/ubuntu xenial/main amd64 libpcre3-dev amd64 2:8.38-3.1 [525 kB]
Fetched 1,269 kB in 0s (1,464 kB/s)   
Selecting previously unselected package libpcrecpp0v5:amd64.
(Reading database ... 98134 files and directories currently installed.)
Preparing to unpack .../libpcrecpp0v5_2%3a8.38-3.1_amd64.deb ...
Unpacking libpcrecpp0v5:amd64 (2:8.38-3.1) ...
Selecting previously unselected package libcurl3:amd64.
Preparing to unpack .../libcurl3_7.47.0-1ubuntu2.13_amd64.deb ...
Unpacking libcurl3:amd64 (7.47.0-1ubuntu2.13) ...
Selecting previously unselected package libcurl4-openssl-dev:amd64.
Preparing to unpack .../libcurl4-openssl-dev_7.47.0-1ubuntu2.13_amd64.deb ...
Unpacking libcurl4-openssl-dev:amd64 (7.47.0-1ubuntu2.13) ...
Selecting previously unselected package libpcre16-3:amd64.
Preparing to unpack .../libpcre16-3_2%3a8.38-3.1_amd64.deb ...
Unpacking libpcre16-3:amd64 (2:8.38-3.1) ...
Selecting previously unselected package libpcre32-3:amd64.
Preparing to unpack .../libpcre32-3_2%3a8.38-3.1_amd64.deb ...
Unpacking libpcre32-3:amd64 (2:8.38-3.1) ...
Selecting previously unselected package libpcre3-dev:amd64.
Preparing to unpack .../libpcre3-dev_2%3a8.38-3.1_amd64.deb ...
Unpacking libpcre3-dev:amd64 (2:8.38-3.1) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for man-db (2.7.5-1) ...
Setting up libpcrecpp0v5:amd64 (2:8.38-3.1) ...
Setting up libcurl3:amd64 (7.47.0-1ubuntu2.13) ...
Setting up libcurl4-openssl-dev:amd64 (7.47.0-1ubuntu2.13) ...
Setting up libpcre16-3:amd64 (2:8.38-3.1) ...
Setting up libpcre32-3:amd64 (2:8.38-3.1) ...
Setting up libpcre3-dev:amd64 (2:8.38-3.1) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
```
b. `apt-get install  cmake ncurses-base libncurses5-dev bison libbison-dev`
```
# apt-get install  cmake ncurses-base libncurses5-dev bison libbison-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
ncurses-base is already the newest version (6.0+20160213-1ubuntu1).
The following additional packages will be installed:
  cmake-data libarchive13 libjsoncpp1 liblzo2-2 libsigsegv2 libtinfo-dev m4
Suggested packages:
  bison-doc codeblocks eclipse ninja-build lrzip ncurses-doc
The following NEW packages will be installed:
  bison cmake cmake-data libarchive13 libbison-dev libjsoncpp1 liblzo2-2 libncurses5-dev
  libsigsegv2 libtinfo-dev m4
0 upgraded, 11 newly installed, 0 to remove and 6 not upgraded.
Need to get 5,185 kB of archives.
After this operation, 25.1 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial-updates/main amd64 cmake-data all 3.5.1-1ubuntu3 [1,121 kB]
Get:2 http://*/ubuntu xenial/main amd64 liblzo2-2 amd64 2.08-1.2 [48.7 kB]
Get:3 http://*/ubuntu xenial-updates/main amd64 libarchive13 amd64 3.1.2-11ubuntu0.16.04.6 [262 kB]
Get:4 http://*/ubuntu xenial/main amd64 libjsoncpp1 amd64 1.7.2-1 [73.0 kB]
Get:5 http://*/ubuntu xenial-updates/main amd64 cmake amd64 3.5.1-1ubuntu3 [2,623 kB]
Get:6 http://*/ubuntu xenial/main amd64 libsigsegv2 amd64 2.10-4 [14.1 kB]
Get:7 http://*/ubuntu xenial/main amd64 m4 amd64 1.4.17-5 [195 kB]
Get:8 http://*/ubuntu xenial/main amd64 libbison-dev amd64 2:3.0.4.dfsg-1 [338 kB]
Get:9 http://*/ubuntu xenial/main amd64 bison amd64 2:3.0.4.dfsg-1 [259 kB]
Get:10 http://*/ubuntu xenial/main amd64 libtinfo-dev amd64 6.0+20160213-1ubuntu1 [77.4 kB]
Get:11 http://*/ubuntu xenial/main amd64 libncurses5-dev amd64 6.0+20160213-1ubuntu1 [175 kB]
Fetched 5,185 kB in 1s (4,207 kB/s)       
Selecting previously unselected package cmake-data.
(Reading database ... 98308 files and directories currently installed.)
Preparing to unpack .../cmake-data_3.5.1-1ubuntu3_all.deb ...
Unpacking cmake-data (3.5.1-1ubuntu3) ...
Selecting previously unselected package liblzo2-2:amd64.
Preparing to unpack .../liblzo2-2_2.08-1.2_amd64.deb ...
Unpacking liblzo2-2:amd64 (2.08-1.2) ...
Selecting previously unselected package libarchive13:amd64.
Preparing to unpack .../libarchive13_3.1.2-11ubuntu0.16.04.6_amd64.deb ...
Unpacking libarchive13:amd64 (3.1.2-11ubuntu0.16.04.6) ...
Selecting previously unselected package libjsoncpp1:amd64.
Preparing to unpack .../libjsoncpp1_1.7.2-1_amd64.deb ...
Unpacking libjsoncpp1:amd64 (1.7.2-1) ...
Selecting previously unselected package cmake.
Preparing to unpack .../cmake_3.5.1-1ubuntu3_amd64.deb ...
Unpacking cmake (3.5.1-1ubuntu3) ...
Selecting previously unselected package libsigsegv2:amd64.
Preparing to unpack .../libsigsegv2_2.10-4_amd64.deb ...
Unpacking libsigsegv2:amd64 (2.10-4) ...
Selecting previously unselected package m4.
Preparing to unpack .../archives/m4_1.4.17-5_amd64.deb ...
Unpacking m4 (1.4.17-5) ...
Selecting previously unselected package libbison-dev:amd64.
Preparing to unpack .../libbison-dev_2%3a3.0.4.dfsg-1_amd64.deb ...
Unpacking libbison-dev:amd64 (2:3.0.4.dfsg-1) ...
Selecting previously unselected package bison.
Preparing to unpack .../bison_2%3a3.0.4.dfsg-1_amd64.deb ...
Unpacking bison (2:3.0.4.dfsg-1) ...
Selecting previously unselected package libtinfo-dev:amd64.
Preparing to unpack .../libtinfo-dev_6.0+20160213-1ubuntu1_amd64.deb ...
Unpacking libtinfo-dev:amd64 (6.0+20160213-1ubuntu1) ...
Selecting previously unselected package libncurses5-dev:amd64.
Preparing to unpack .../libncurses5-dev_6.0+20160213-1ubuntu1_amd64.deb ...
Unpacking libncurses5-dev:amd64 (6.0+20160213-1ubuntu1) ...
Processing triggers for man-db (2.7.5-1) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for install-info (6.1.0.dfsg.1-5) ...
Setting up cmake-data (3.5.1-1ubuntu3) ...
Setting up liblzo2-2:amd64 (2.08-1.2) ...
Setting up libarchive13:amd64 (3.1.2-11ubuntu0.16.04.6) ...
Setting up libjsoncpp1:amd64 (1.7.2-1) ...
Setting up cmake (3.5.1-1ubuntu3) ...
Setting up libsigsegv2:amd64 (2.10-4) ...
Setting up m4 (1.4.17-5) ...
Setting up libbison-dev:amd64 (2:3.0.4.dfsg-1) ...
Setting up bison (2:3.0.4.dfsg-1) ...
update-alternatives: using /usr/bin/bison.yacc to provide /usr/bin/yacc (yacc) in auto mode
Setting up libtinfo-dev:amd64 (6.0+20160213-1ubuntu1) ...
Setting up libncurses5-dev:amd64 (6.0+20160213-1ubuntu1) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
```
c. `apt-get install  perl libperl-dev autoconf`
```
# apt-get install  perl libperl-dev autoconf
Reading package lists... Done
Building dependency tree       
Reading state information... Done
perl is already the newest version (5.22.1-9ubuntu0.6).
Suggested packages:
  autoconf-archive gnu-standards autoconf-doc libtool gettext
Recommended packages:
  automake | automaken
The following NEW packages will be installed:
  autoconf libperl-dev
0 upgraded, 2 newly installed, 0 to remove and 6 not upgraded.
Need to get 2,869 kB of archives.
After this operation, 17.0 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial/main amd64 autoconf all 2.69-9 [321 kB]
Get:2 http://*/ubuntu xenial-updates/main amd64 libperl-dev amd64 5.22.1-9ubuntu0.6 [2,548 kB]
Fetched 2,869 kB in 0s (4,572 kB/s)    
Selecting previously unselected package autoconf.
(Reading database ... 100557 files and directories currently installed.)
Preparing to unpack .../autoconf_2.69-9_all.deb ...
Unpacking autoconf (2.69-9) ...
Selecting previously unselected package libperl-dev.
Preparing to unpack .../libperl-dev_5.22.1-9ubuntu0.6_amd64.deb ...
Unpacking libperl-dev (5.22.1-9ubuntu0.6) ...
Processing triggers for man-db (2.7.5-1) ...
Setting up autoconf (2.69-9) ...
Setting up libperl-dev (5.22.1-9ubuntu0.6) ...
```
d. `apt-get install libreadline-dev`
```
# apt-get install libreadline-dev 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libreadline6-dev
Suggested packages:
  readline-doc
The following NEW packages will be installed:
  libreadline-dev libreadline6-dev
0 upgraded, 2 newly installed, 0 to remove and 6 not upgraded.
Need to get 125 kB of archives.
After this operation, 692 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial/main amd64 libreadline6-dev amd64 6.3-8ubuntu2 [124 kB]
Get:2 http://*/ubuntu xenial/main amd64 libreadline-dev amd64 6.3-8ubuntu2 [992 B]
Fetched 125 kB in 0s (421 kB/s)         
Selecting previously unselected package libreadline6-dev:amd64.
(Reading database ... 100637 files and directories currently installed.)
Preparing to unpack .../libreadline6-dev_6.3-8ubuntu2_amd64.deb ...
Unpacking libreadline6-dev:amd64 (6.3-8ubuntu2) ...
Selecting previously unselected package libreadline-dev:amd64.
Preparing to unpack .../libreadline-dev_6.3-8ubuntu2_amd64.deb ...
Unpacking libreadline-dev:amd64 (6.3-8ubuntu2) ...
Processing triggers for install-info (6.1.0.dfsg.1-5) ...
Setting up libreadline6-dev:amd64 (6.3-8ubuntu2) ...
Setting up libreadline-dev:amd64 (6.3-8ubuntu2) ...
```
e. `apt-get install zlib1g zlib1g-dev`
```
# apt-get install zlib1g zlib1g-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
zlib1g is already the newest version (1:1.2.8.dfsg-2ubuntu4.1).
The following NEW packages will be installed:
  zlib1g-dev
0 upgraded, 1 newly installed, 0 to remove and 6 not upgraded.
Need to get 168 kB of archives.
After this operation, 425 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial-updates/main amd64 zlib1g-dev amd64 1:1.2.8.dfsg-2ubuntu4.1 [168 kB]
Fetched 168 kB in 0s (738 kB/s)    
Selecting previously unselected package zlib1g-dev:amd64.
(Reading database ... 100652 files and directories currently installed.)
Preparing to unpack .../zlib1g-dev_1%3a1.2.8.dfsg-2ubuntu4.1_amd64.deb ...
Unpacking zlib1g-dev:amd64 (1:1.2.8.dfsg-2ubuntu4.1) ...
Processing triggers for man-db (2.7.5-1) ...
Setting up zlib1g-dev:amd64 (1:1.2.8.dfsg-2ubuntu4.1) ...
```
f. `apt-get install libpam0g=1.1.8-3.2ubuntu2.1 libpam0g-dev` 
```
默认pam lib版本
The following packages have unmet dependencies:
 libpam0g-dev : Depends: libpam0g (= 1.1.8-3.2ubuntu2.1) but 1.1.8-3.2ubuntu2.2 is to be installed
E: Unable to correct problems, you have held broken packages.
```
```
# apt-get install libpam0g=1.1.8-3.2ubuntu2.1 libpam0g-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Suggested packages:
  libpam-doc
The following NEW packages will be installed:
  libpam0g-dev
The following packages will be DOWNGRADED:
  libpam0g
0 upgraded, 1 newly installed, 1 downgraded, 0 to remove and 6 not upgraded.
Need to get 165 kB of archives.
After this operation, 381 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://*/ubuntu xenial-updates/main amd64 libpam0g amd64 1.1.8-3.2ubuntu2.1 [55.6 kB]
Get:2 http://*/ubuntu xenial-updates/main amd64 libpam0g-dev amd64 1.1.8-3.2ubuntu2.1 [109 kB]
Fetched 165 kB in 0s (557 kB/s)   
Preconfiguring packages ...
dpkg: warning: downgrading libpam0g:amd64 from 1.1.8-3.2ubuntu2.2 to 1.1.8-3.2ubuntu2.1
(Reading database ... 100680 files and directories currently installed.)
Preparing to unpack .../libpam0g_1.1.8-3.2ubuntu2.1_amd64.deb ...
Unpacking libpam0g:amd64 (1.1.8-3.2ubuntu2.1) over (1.1.8-3.2ubuntu2.2) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Setting up libpam0g:amd64 (1.1.8-3.2ubuntu2.1) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Selecting previously unselected package libpam0g-dev:amd64.
(Reading database ... 100680 files and directories currently installed.)
Preparing to unpack .../libpam0g-dev_1.1.8-3.2ubuntu2.1_amd64.deb ...
Unpacking libpam0g-dev:amd64 (1.1.8-3.2ubuntu2.1) ...
Processing triggers for man-db (2.7.5-1) ...
Setting up libpam0g-dev:amd64 (1.1.8-3.2ubuntu2.1) ...
```

2. 编译安装
```
:~/db# ls
percona-server-5.7.25-28.tar.gz
:~/db# tar zxf percona-server-5.7.25-28.tar.gz 
:~/db# cd percona-server-5.7.25-28/
:~/db/percona-server-5.7.25-28# ls
BUILD                                doc                  libservices   scripts
build-ps                             Docs                 man           sql
client                               Doxyfile-perfschema  mysql-test    sql-common
cmake                                extra                mysys         storage
CMakeLists.txt                       include              mysys_ssl     strings
cmd-line-utils                       INSTALL              packaging     support-files
config.h.cmake                       internal             plugin        testclients
configure.cmake                      libbinlogevents      policy        unittest
COPYING                              libbinlogstandalone  rapid         VERSION
COPYING.innodb-deadlock-count-patch  libevent             README        vio
COPYING.show_temp_51                 libmysql             README.MySQL  win
dbug                                 libmysqld            regex         zlib
:~/db/percona-server-5.7.25-28# mkdir bld
:~/db/percona-server-5.7.25-28# cd bld/
:~/db/percona-server-5.7.25-28/bld# ls
:~/db/percona-server-5.7.25-28/bld# cmake --clean-first  ../  -DDOWNLOAD_BOOST=1 -DWITH_BOOST=/usr/local/boost -DCMAKE_INSTALL_PREFIX=/usr/local/mysql-5.7.25-28 -WITH_DEBUG=1 -WITH_LZ4=bundled  -WITH_PROTOBUF=bundled -DWITH_PAM=ON
```
1. `cmake --clean-first  ../  -DDOWNLOAD_BOOST=1 -DWITH_BOOST=/usr/local/boost -DCMAKE_INSTALL_PREFIX=/usr/local/mysql-5.7.25-28 -WITH_DEBUG=1 -WITH_LZ4=bundled  -WITH_PROTOBUF=bundled -DWITH_PAM=ON`
  <details>
    <summary>cmake过程</summary>
  
  ```
    # cmake --clean-first  ../  -DDOWNLOAD_BOOST=1 -DWITH_BOOST=/usr/local/boost -DCMAKE_INSTALL_PREFIX=/usr/local/mysql-5.7.25-28 -WITH_DEBUG=1 -WITH_LZ4=bundled  -WITH_PROTOBUF=bundled -DWITH_PAM=ON 
    -- Running cmake version 3.5.1
    -- Found Git: /usr/bin/git (found version "2.7.4") 
    -- Configuring with MAX_INDEXES = 64U
    -- CMAKE_GENERATOR: Unix Makefiles
    -- Looking for SHM_HUGETLB
    -- Looking for SHM_HUGETLB - found
    -- Looking for sys/types.h
    -- Looking for sys/types.h - found
    -- Looking for stdint.h
    -- Looking for stdint.h - found
    -- Looking for stddef.h
    -- Looking for stddef.h - found
    -- Check size of void *
    -- Check size of void * - done
    -- SIZEOF_VOIDP 8
    -- Performing Test HAVE_C_SHIFT_OR_OPTIMIZATION_BUG
    -- Performing Test HAVE_C_SHIFT_OR_OPTIMIZATION_BUG - Failed
    -- Performing Test HAVE_CXX_SHIFT_OR_OPTIMIZATION_BUG
    -- Performing Test HAVE_CXX_SHIFT_OR_OPTIMIZATION_BUG - Failed
    -- Performing Test HAVE_C_FLOATING_POINT_FUSED_MADD
    -- Performing Test HAVE_C_FLOATING_POINT_FUSED_MADD - Failed
    -- Performing Test HAVE_CXX_FLOATING_POINT_FUSED_MADD
    -- Performing Test HAVE_CXX_FLOATING_POINT_FUSED_MADD - Failed
    -- Performing Test HAVE_C_FP_CONTRACT_FLAG
    -- Performing Test HAVE_C_FP_CONTRACT_FLAG - Success
    -- Performing Test HAVE_CXX_FP_CONTRACT_FLAG
    -- Performing Test HAVE_CXX_FP_CONTRACT_FLAG - Success
    -- Performing Test GNU03_SUPPORTED
    -- Performing Test GNU03_SUPPORTED - Success
    -- MySQL 5.7.25-28
    -- Packaging as: percona-server-5.7.25-28-Linux-x86_64
    -- Local boost dir /usr/local/boost/boost_1_59_0
    -- Local boost zip /usr/local/boost/boost_1_59_0.tar.gz
    -- Found /usr/local/boost/boost_1_59_0/boost/version.hpp 
    -- BOOST_VERSION_NUMBER is #define BOOST_VERSION 105900
    -- BOOST_INCLUDE_DIR /usr/local/boost/boost_1_59_0
    -- Performing Test HAVE_LLVM_LIBCPP
    -- Performing Test HAVE_LLVM_LIBCPP - Failed
    -- Looking for pthread.h
    -- Looking for pthread.h - found
    -- Looking for pthread_create
    -- Looking for pthread_create - not found
    -- Looking for pthread_create in pthreads
    -- Looking for pthread_create in pthreads - not found
    -- Looking for pthread_create in pthread
    -- Looking for pthread_create in pthread - found
    -- Found Threads: TRUE  
    -- Looking for floor
    -- Looking for floor - not found
    -- Looking for floor in m
    -- Looking for floor in m - found
    -- Looking for gethostbyname_r
    -- Looking for gethostbyname_r - found
    -- Looking for bind
    -- Looking for bind - found
    -- Looking for crypt
    -- Looking for crypt - not found
    -- Looking for crypt in crypt
    -- Looking for crypt in crypt - found
    -- Looking for setsockopt
    -- Looking for setsockopt - found
    -- Looking for dlopen
    -- Looking for dlopen - not found
    -- Looking for dlopen in dl
    -- Looking for dlopen in dl - found
    -- Looking for sched_yield
    -- Looking for sched_yield - found
    -- Looking for clock_gettime
    -- Looking for clock_gettime - found
    -- Looking for timer_create
    -- Looking for timer_create - not found
    -- Looking for timer_create in rt
    -- Looking for timer_create in rt - found
    -- Looking for atomic_thread_fence
    -- Looking for atomic_thread_fence - not found
    -- Looking for atomic_thread_fence in atomic
    -- Looking for atomic_thread_fence in atomic - not found
    -- Looking for backtrace
    -- Looking for backtrace - found
    -- Looking for include file alloca.h
    -- Looking for include file alloca.h - found
    -- Looking for include file arpa/inet.h
    -- Looking for include file arpa/inet.h - found
    -- Looking for include file crypt.h
    -- Looking for include file crypt.h - found
    -- Looking for include file dlfcn.h
    -- Looking for include file dlfcn.h - found
    -- Looking for include file execinfo.h
    -- Looking for include file execinfo.h - found
    -- Looking for include file fpu_control.h
    -- Looking for include file fpu_control.h - found
    -- Looking for include file grp.h
    -- Looking for include file grp.h - found
    -- Looking for include file ieeefp.h
    -- Looking for include file ieeefp.h - not found
    -- Looking for include file langinfo.h
    -- Looking for include file langinfo.h - found
    -- Looking for include file malloc.h
    -- Looking for include file malloc.h - found
    -- Looking for include file netinet/in.h
    -- Looking for include file netinet/in.h - found
    -- Looking for include file poll.h
    -- Looking for include file poll.h - found
    -- Looking for include file pwd.h
    -- Looking for include file pwd.h - found
    -- Looking for include file strings.h
    -- Looking for include file strings.h - found
    -- Looking for include file sys/cdefs.h
    -- Looking for include file sys/cdefs.h - found
    -- Looking for include file sys/ioctl.h
    -- Looking for include file sys/ioctl.h - found
    -- Looking for include file sys/mman.h
    -- Looking for include file sys/mman.h - found
    -- Looking for include file sys/resource.h
    -- Looking for include file sys/resource.h - found
    -- Looking for include file sys/select.h
    -- Looking for include file sys/select.h - found
    -- Looking for include file sys/socket.h
    -- Looking for include file sys/socket.h - found
    -- Looking for include files curses.h, term.h
    -- Looking for include files curses.h, term.h - found
    -- Looking for include file termios.h
    -- Looking for include file termios.h - found
    -- Looking for include file termio.h
    -- Looking for include file termio.h - found
    -- Looking for include file unistd.h
    -- Looking for include file unistd.h - found
    -- Looking for include file sys/wait.h
    -- Looking for include file sys/wait.h - found
    -- Looking for include file sys/param.h
    -- Looking for include file sys/param.h - found
    -- Looking for include file fnmatch.h
    -- Looking for include file fnmatch.h - found
    -- Looking for include file sys/un.h
    -- Looking for include file sys/un.h - found
    -- Looking for include file vis.h
    -- Looking for include file vis.h - not found
    -- Looking for include file sasl/sasl.h
    -- Looking for include file sasl/sasl.h - not found
    -- Looking for include file sys/devpoll.h
    -- Looking for include file sys/devpoll.h - not found
    -- Looking for include file sys/epoll.h
    -- Looking for include file sys/epoll.h - found
    -- Looking for TAILQ_FOREACH
    -- Looking for TAILQ_FOREACH - found
    -- Looking for _aligned_malloc
    -- Looking for _aligned_malloc - not found
    -- Looking for backtrace
    -- Looking for backtrace - found
    -- Looking for printstack
    -- Looking for printstack - not found
    -- Looking for index
    -- Looking for index - found
    -- Looking for clock_gettime
    -- Looking for clock_gettime - found
    -- Looking for cuserid
    -- Looking for cuserid - found
    -- Looking for directio
    -- Looking for directio - not found
    -- Looking for ftruncate
    -- Looking for ftruncate - found
    -- Looking for compress
    -- Looking for compress - not found
    -- Looking for crypt
    -- Looking for crypt - found
    -- Looking for dlopen
    -- Looking for dlopen - found
    -- Looking for fchmod
    -- Looking for fchmod - found
    -- Looking for fcntl
    -- Looking for fcntl - found
    -- Looking for fdatasync
    -- Looking for fdatasync - found
    -- Looking for fdatasync
    -- Looking for fdatasync - found
    -- Looking for fedisableexcept
    -- Looking for fedisableexcept - found
    -- Looking for fseeko
    -- Looking for fseeko - found
    -- Looking for fsync
    -- Looking for fsync - found
    -- Looking for gethostbyaddr_r
    -- Looking for gethostbyaddr_r - found
    -- Looking for gethrtime
    -- Looking for gethrtime - not found
    -- Looking for getnameinfo
    -- Looking for getnameinfo - found
    -- Looking for getpass
    -- Looking for getpass - found
    -- Looking for getpassphrase
    -- Looking for getpassphrase - not found
    -- Looking for getpwnam
    -- Looking for getpwnam - found
    -- Looking for getpwuid
    -- Looking for getpwuid - found
    -- Looking for getrlimit
    -- Looking for getrlimit - found
    -- Looking for getrusage
    -- Looking for getrusage - found
    -- Looking for initgroups
    -- Looking for initgroups - found
    -- Looking for issetugid
    -- Looking for issetugid - not found
    -- Looking for getuid
    -- Looking for getuid - found
    -- Looking for geteuid
    -- Looking for geteuid - found
    -- Looking for getgid
    -- Looking for getgid - found
    -- Looking for getegid
    -- Looking for getegid - found
    -- Looking for lstat
    -- Looking for lstat - found
    -- Looking for madvise
    -- Looking for madvise - found
    -- Looking for malloc_info
    -- Looking for malloc_info - found
    -- Looking for memrchr
    -- Looking for memrchr - found
    -- Looking for mlock
    -- Looking for mlock - found
    -- Looking for mlockall
    -- Looking for mlockall - found
    -- Looking for mmap64
    -- Looking for mmap64 - found
    -- Looking for poll
    -- Looking for poll - found
    -- Looking for posix_fallocate
    -- Looking for posix_fallocate - found
    -- Looking for posix_memalign
    -- Looking for posix_memalign - found
    -- Looking for pread
    -- Looking for pread - found
    -- Looking for pthread_condattr_setclock
    -- Looking for pthread_condattr_setclock - found
    -- Looking for pthread_sigmask
    -- Looking for pthread_sigmask - found
    -- Looking for readlink
    -- Looking for readlink - found
    -- Looking for realpath
    -- Looking for realpath - found
    -- Looking for setfd
    -- Looking for setfd - not found
    -- Looking for sigaction
    -- Looking for sigaction - found
    -- Looking for sleep
    -- Looking for sleep - found
    -- Looking for stpcpy
    -- Looking for stpcpy - found
    -- Looking for stpncpy
    -- Looking for stpncpy - found
    -- Looking for strlcpy
    -- Looking for strlcpy - not found
    -- Looking for strndup
    -- Looking for strndup - found
    -- Looking for strnlen
    -- Looking for strnlen - found
    -- Looking for strlcat
    -- Looking for strlcat - not found
    -- Looking for strsignal
    -- Looking for strsignal - found
    -- Looking for fgetln
    -- Looking for fgetln - not found
    -- Looking for strsep
    -- Looking for strsep - found
    -- Looking for tell
    -- Looking for tell - not found
    -- Looking for vasprintf
    -- Looking for vasprintf - found
    -- Looking for memalign
    -- Looking for memalign - found
    -- Looking for nl_langinfo
    -- Looking for nl_langinfo - found
    -- Looking for ntohll
    -- Looking for ntohll - not found
    -- Looking for memset_s
    -- Looking for memset_s - not found
    -- Looking for clock_gettime
    -- Looking for clock_gettime - found
    -- Looking for epoll_create
    -- Looking for epoll_create - found
    -- Looking for inet_ntop
    -- Looking for inet_ntop - found
    -- Looking for kqueue
    -- Looking for kqueue - not found
    -- Looking for timeradd
    -- Looking for timeradd - found
    -- Looking for timerclear
    -- Looking for timerclear - found
    -- Looking for timercmp
    -- Looking for timercmp - found
    -- Looking for timerisset
    -- Looking for timerisset - found
    -- Looking for include file sys/time.h
    -- Looking for include file sys/time.h - found
    -- Looking for include file sys/times.h
    -- Looking for include file sys/times.h - found
    -- Looking for times
    -- Looking for times - found
    -- Looking for gettimeofday
    -- Looking for gettimeofday - found
    -- Looking for lrand48
    -- Looking for lrand48 - found
    -- Looking for TIOCGWINSZ
    -- Looking for TIOCGWINSZ - found
    -- Looking for FIONREAD
    -- Looking for FIONREAD - found
    -- Looking for FIONREAD
    -- Looking for FIONREAD - not found
    -- Looking for SIGEV_THREAD_ID
    -- Looking for SIGEV_THREAD_ID - found
    -- Looking for SIGEV_PORT
    -- Looking for SIGEV_PORT - not found
    -- Looking for log2
    -- Looking for log2 - found
    -- Looking for isinf
    -- Looking for isinf - found
    -- Performing Test HAVE_CXX_ISINF
    -- Performing Test HAVE_CXX_ISINF - Success
    -- Looking for timer_create
    -- Looking for timer_create - found
    -- Looking for timer_settime
    -- Looking for timer_settime - found
    -- Looking for kqueue
    -- Looking for kqueue - not found
    -- Looking for EVFILT_TIMER
    -- Looking for EVFILT_TIMER - not found
    -- Check if the system is big endian
    -- Searching 16 bit integer
    -- Check size of unsigned short
    -- Check size of unsigned short - done
    -- Using unsigned short
    -- Check if the system is big endian - little endian
    -- Check size of char *
    -- Check size of char * - done
    -- Check size of long
    -- Check size of long - done
    -- Check size of short
    -- Check size of short - done
    -- Check size of int
    -- Check size of int - done
    -- Check size of long long
    -- Check size of long long - done
    -- Check size of off_t
    -- Check size of off_t - done
    -- Check size of time_t
    -- Check size of time_t - done
    -- Check size of struct timespec
    -- Check size of struct timespec - done
    -- Check size of uint
    -- Check size of uint - done
    -- Check size of ulong
    -- Check size of ulong - done
    -- Check size of u_int32_t
    -- Check size of u_int32_t - done
    -- Performing Test HAVE_VISIBILITY_HIDDEN
    -- Performing Test HAVE_VISIBILITY_HIDDEN - Success
    -- Checking stack direction : -1
    -- Looking for include files time.h, sys/time.h
    -- Looking for include files time.h, sys/time.h - found
    -- Looking for O_NONBLOCK
    -- Looking for O_NONBLOCK - found
    -- Performing Test HAVE_PAUSE_INSTRUCTION
    -- Performing Test HAVE_PAUSE_INSTRUCTION - Success
    -- Performing Test HAVE_BUILTIN_UNREACHABLE
    -- Performing Test HAVE_BUILTIN_UNREACHABLE - Success
    -- Performing Test HAVE_BUILTIN_EXPECT
    -- Performing Test HAVE_BUILTIN_EXPECT - Success
    -- Performing Test HAVE_BUILTIN_STPCPY
    -- Performing Test HAVE_BUILTIN_STPCPY - Success
    -- Performing Test HAVE_GCC_ATOMIC_BUILTINS
    -- Performing Test HAVE_GCC_ATOMIC_BUILTINS - Success
    -- Performing Test HAVE_GCC_SYNC_BUILTINS
    -- Performing Test HAVE_GCC_SYNC_BUILTINS - Success
    -- Looking for netinet/in6.h
    -- Looking for netinet/in6.h - not found
    -- Check size of struct sockaddr_in6
    -- Check size of struct sockaddr_in6 - done
    -- Check size of struct in6_addr
    -- Check size of struct in6_addr - done
    -- Performing Test HAVE_SOCKADDR_STORAGE_SS_FAMILY
    -- Performing Test HAVE_SOCKADDR_STORAGE_SS_FAMILY - Success
    -- Performing Test HAVE_SOCKADDR_IN_SIN_LEN
    -- Performing Test HAVE_SOCKADDR_IN_SIN_LEN - Failed
    -- Performing Test HAVE_SOCKADDR_IN6_SIN6_LEN
    -- Performing Test HAVE_SOCKADDR_IN6_SIN6_LEN - Failed
    -- Performing Test HAVE_PTHREAD_THREADID_NP
    -- Performing Test HAVE_PTHREAD_THREADID_NP - Failed
    -- Performing Test HAVE_IMPLICIT_DEPENDENT_NAME_TYPING
    -- Performing Test HAVE_IMPLICIT_DEPENDENT_NAME_TYPING - Failed
    -- Looking for chown
    -- Looking for chown - found
    -- Looking for include file numa.h
    -- Looking for include file numa.h - not found
    -- Looking for include file numaif.h
    -- Looking for include file numaif.h - not found
    -- NUMA library missing or required version not available
    -- Check size of socklen_t
    -- Check size of socklen_t - failed
    -- Looking for crc32
    -- Looking for crc32 - found
    -- Looking for compressBound
    -- Looking for compressBound - found
    -- Looking for deflateBound
    -- Looking for deflateBound - found
    -- Performing Test HAVE_STRINGOP_OVERFLOW
    -- Performing Test HAVE_STRINGOP_OVERFLOW - Failed
    -- Performing Test HAVE_NO_UNUSED_CONST_VAR
    -- Performing Test HAVE_NO_UNUSED_CONST_VAR - Success
    -- Check size of mbstate_t
    -- Check size of mbstate_t - done
    -- Performing Test HAVE_LANGINFO_CODESET
    -- Performing Test HAVE_LANGINFO_CODESET - Success
    -- Looking for wcsdup
    -- Looking for wcsdup - found
    -- Check size of wchar_t
    -- Check size of wchar_t - done
    -- Check size of wint_t
    -- Check size of wint_t - done
    -- Found Curses: /usr/lib/x86_64-linux-gnu/libcurses.so  
    -- Looking for tputs in /usr/lib/x86_64-linux-gnu/libcurses.so
    -- Looking for tputs in /usr/lib/x86_64-linux-gnu/libcurses.so - found
    -- Looking for 3 include files stdio.h, ..., readline/history.h
    -- Looking for 3 include files stdio.h, ..., readline/history.h - found
    -- READLINE_INCLUDE_DIR /usr/include/readline
    -- READLINE_LIBRARY /usr/lib/x86_64-linux-gnu/libreadline.so
    -- Performing Test READLINE_HAVE_HIST_ENTRY
    -- Performing Test READLINE_HAVE_HIST_ENTRY - Success
    -- Performing Test READLINE_USE_LIBEDIT_INTERFACE
    -- Performing Test READLINE_USE_LIBEDIT_INTERFACE - Success
    -- Performing Test READLINE_USE_NEW_READLINE_INTERFACE
    -- Performing Test READLINE_USE_NEW_READLINE_INTERFACE - Success
    -- Cannot find system sasl libraries.
    -- WITH_PROTOBUF=bundled
    -- Performing Test HAVE_NO_SIGN_COMPARE
    -- Performing Test HAVE_NO_SIGN_COMPARE - Success
    -- Performing Test HAVE_NO_UNUSED_TYPEDEFS
    -- Performing Test HAVE_NO_UNUSED_TYPEDEFS - Success
    -- Performing Test HAVE_NO_IGNORED_QUALIFIERS
    -- Performing Test HAVE_NO_IGNORED_QUALIFIERS - Success
    -- Performing Test HAVE_NO_RETURN_TYPE
    -- Performing Test HAVE_NO_RETURN_TYPE - Success
    -- Performing Test HAVE_NO_UNUSED_FUNCTION
    -- Performing Test HAVE_NO_UNUSED_FUNCTION - Success
    -- Performing Test HAVE_MAYBE_UNINITIALIZED
    -- Performing Test HAVE_MAYBE_UNINITIALIZED - Success
    -- Performing Test HAVE_UNUSED_BUT_SET
    -- Performing Test HAVE_UNUSED_BUT_SET - Success
    -- protobuf version is 2.6
    -- Found CURL: /usr/lib/x86_64-linux-gnu/libcurl.so (found version "7.47.0") 
    -- CURL_LIBRARY = /usr/lib/x86_64-linux-gnu/libcurl.so
    -- Performing Test HAVE_SYS_THREAD_SELFID
    -- Performing Test HAVE_SYS_THREAD_SELFID - Failed
    -- Performing Test HAVE_SYS_GETTID
    -- Performing Test HAVE_SYS_GETTID - Success
    -- Performing Test HAVE_PTHREAD_SETNAME_NP
    -- Performing Test HAVE_PTHREAD_SETNAME_NP - Failed
    -- Performing Test HAVE_PTHREAD_GETTHREADID_NP
    -- Performing Test HAVE_PTHREAD_GETTHREADID_NP - Failed
    -- Performing Test HAVE_INTEGER_PTHREAD_SELF
    -- Performing Test HAVE_INTEGER_PTHREAD_SELF - Success
    -- Performing Test HAVE_STRINGOP_TRUNCATION
    -- Performing Test HAVE_STRINGOP_TRUNCATION - Failed
    -- Creating LDAP authentication SASL client library.
    -- Currently LDAP SASL client authentication plug-in is build with only system installed cyrus SASL library.
    -- Looking for include file sasl/sasl.h
    -- Looking for include file sasl/sasl.h - not found
    -- Looking for include file lber.h
    -- Looking for include file lber.h - not found
    -- Required SASL library is missing. Skipping the LDAP SASL client authentication plugin.
    -- Library perconaserverclient depends on OSLIBS -lpthread;/usr/lib/x86_64-linux-gnu/libz.so;m;rt;dl
    -- MERGE_CONVENIENCE_LIBRARIES TARGET perconaserverclient
    -- MERGE_CONVENIENCE_LIBRARIES LIBS clientlib;dbug;strings;vio;mysys;mysys_ssl;/usr/lib/x86_64-linux-gnu/libz.so;yassl;taocrypt;dl
    -- MERGE_CONVENIENCE_LIBRARIES MYLIBS clientlib;dbug;strings;vio;mysys;mysys_ssl;yassl;taocrypt
    -- Looking for include file endian.h
    -- Looking for include file endian.h - found
    -- Looking for le64toh
    -- Looking for le64toh - found
    -- Looking for le32toh
    -- Looking for le32toh - found
    -- Looking for le16toh
    -- Looking for le16toh - found
    -- Check size of long long
    -- Check size of long long - done
    -- Check size of long
    -- Check size of long - done
    -- Check size of int
    -- Check size of int - done
    -- Check if the system is big endian
    -- Searching 16 bit integer
    -- Using unsigned short
    -- Check if the system is big endian - little endian
    -- Using cmake version 3.5.1
    -- Performing Test HAVE_UNUSED_BUT_SET_VARIABLE
    -- Performing Test HAVE_UNUSED_BUT_SET_VARIABLE - Success
    -- Disabling -Wunused-but-set-variable warning for building NDB
    -- Performing Test HAVE_STRICT_ALIASING
    -- Performing Test HAVE_STRICT_ALIASING - Success
    -- Disabling -Wstrict-aliasing warning for building NDB
    -- Not building NDB
    -- Building with MyRocks storage engine = 1
    -- Performing Test HAVE_UNUSED_VARIABLE
    -- Performing Test HAVE_UNUSED_VARIABLE - Success
    -- Performing Test HAVE_IMPLICIT_FALLTHROUGH
    -- Performing Test HAVE_IMPLICIT_FALLTHROUGH - Failed
    -- Performing Test HAVE_STDCXX11
    -- Performing Test HAVE_STDCXX11 - Success
    -- Looking for sched_getcpu
    -- Looking for sched_getcpu - found
    -- Performing Test HAVE_SSE42
    -- Performing Test HAVE_SSE42 - Success
    -- Looking for include file linux/falloc.h
    -- Looking for include file linux/falloc.h - found
    -- Looking for fallocate
    -- Looking for fallocate - found
    -- Performing Test HAVE_CAST_FUNCTION_TYPE
    -- Performing Test HAVE_CAST_FUNCTION_TYPE - Failed
    -- Looking for include file libaio.h
    -- Looking for include file libaio.h - not found
    -- Looking for io_queue_init in aio
    -- Looking for io_queue_init in aio - not found
    -- Performing Test HAVE_NO_BUILTIN_MEMCMP
    -- Performing Test HAVE_NO_BUILTIN_MEMCMP - Success
    -- Looking for nanosleep
    -- Looking for nanosleep - found
    -- Performing Test HAVE_FALLOC_PUNCH_HOLE_AND_KEEP_SIZE
    -- Performing Test HAVE_FALLOC_PUNCH_HOLE_AND_KEEP_SIZE - Success
    -- Performing Test HAVE_IB_GCC_SYNC_SYNCHRONISE
    -- Performing Test HAVE_IB_GCC_SYNC_SYNCHRONISE - Success
    -- Performing Test HAVE_IB_GCC_ATOMIC_THREAD_FENCE
    -- Performing Test HAVE_IB_GCC_ATOMIC_THREAD_FENCE - Success
    -- Performing Test HAVE_IB_GCC_ATOMIC_COMPARE_EXCHANGE
    -- Performing Test HAVE_IB_GCC_ATOMIC_COMPARE_EXCHANGE - Success
    -- Performing Test HAVE_IB_ATOMIC_PTHREAD_T_GCC
    -- Performing Test HAVE_IB_ATOMIC_PTHREAD_T_GCC - Success
    -- Performing Test HAVE_IB_LINUX_FUTEX
    -- Performing Test HAVE_IB_LINUX_FUTEX - Success
    -- Looking for asprintf
    -- Looking for asprintf - found
    -- Building with TokuDB storage engine = 1
    -- Performing Test TOKUDB_OK
    -- Performing Test TOKUDB_OK - Success
    -- Performing Test HAVE_C__Wno_missing_field_initializers
    -- Performing Test HAVE_C__Wno_missing_field_initializers - Success
    -- Performing Test HAVE_CXX__Wno_missing_field_initializers
    -- Performing Test HAVE_CXX__Wno_missing_field_initializers - Success
    -- Performing Test HAVE_C__Wno_vla
    -- Performing Test HAVE_C__Wno_vla - Success
    -- Performing Test HAVE_CXX__Wno_vla
    -- Performing Test HAVE_CXX__Wno_vla - Success
    -- Looking for include file bits/functexcept.h
    -- Looking for include file bits/functexcept.h - not found
    -- Looking for include file byteswap.h
    -- Looking for include file byteswap.h - found
    -- Looking for include file fcntl.h
    -- Looking for include file fcntl.h - found
    -- Looking for include file inttypes.h
    -- Looking for include file inttypes.h - found
    -- Looking for include file libkern/OSAtomic.h
    -- Looking for include file libkern/OSAtomic.h - not found
    -- Looking for include file libkern/OSByteOrder.h
    -- Looking for include file libkern/OSByteOrder.h - not found
    -- Looking for include file limits.h
    -- Looking for include file limits.h - found
    -- Looking for include file machine/endian.h
    -- Looking for include file machine/endian.h - not found
    -- Looking for include file malloc/malloc.h
    -- Looking for include file malloc/malloc.h - not found
    -- Looking for include file malloc_np.h
    -- Looking for include file malloc_np.h - not found
    -- Looking for include file pthread.h
    -- Looking for include file pthread.h - found
    -- Looking for include file pthread_np.h
    -- Looking for include file pthread_np.h - not found
    -- Looking for include file stdlib.h
    -- Looking for include file stdlib.h - found
    -- Looking for include file string.h
    -- Looking for include file string.h - found
    -- Looking for include file syscall.h
    -- Looking for include file syscall.h - found
    -- Looking for include file sys/endian.h
    -- Looking for include file sys/endian.h - not found
    -- Looking for include file sys/file.h
    -- Looking for include file sys/file.h - found
    -- Looking for include file sys/malloc.h
    -- Looking for include file sys/malloc.h - not found
    -- Looking for include file sys/prctl.h
    -- Looking for include file sys/prctl.h - found
    -- Looking for include file sys/statvfs.h
    -- Looking for include file sys/statvfs.h - found
    -- Looking for include file sys/syscall.h
    -- Looking for include file sys/syscall.h - found
    -- Looking for include file sys/sysctl.h
    -- Looking for include file sys/sysctl.h - found
    -- Looking for include file sys/syslimits.h
    -- Looking for include file sys/syslimits.h - not found
    -- Looking for M_MMAP_THRESHOLD
    -- Looking for M_MMAP_THRESHOLD - found
    -- Looking for CLOCK_REALTIME
    -- Looking for CLOCK_REALTIME - found
    -- Looking for O_DIRECT
    -- Looking for O_DIRECT - found
    -- Looking for F_NOCACHE
    -- Looking for F_NOCACHE - not found
    -- Looking for MAP_ANONYMOUS
    -- Looking for MAP_ANONYMOUS - found
    -- Looking for PR_SET_PTRACER
    -- Looking for PR_SET_PTRACER - found
    -- Looking for PR_SET_PTRACER_ANY
    -- Looking for PR_SET_PTRACER_ANY - found
    -- Looking for malloc_size
    -- Looking for malloc_size - not found
    -- Looking for malloc_usable_size
    -- Looking for malloc_usable_size - found
    -- Looking for valloc
    -- Looking for valloc - found
    -- Looking for nrand48
    -- Looking for nrand48 - found
    -- Looking for random_r
    -- Looking for random_r - found
    -- Looking for mincore
    -- Looking for mincore - found
    -- Looking for dlsym
    -- Looking for dlsym - not found
    -- Looking for dlsym
    -- Looking for dlsym - found
    -- Looking for backtrace
    -- Looking for backtrace - found
    -- Looking for pthread_rwlockattr_setkind_np
    -- Looking for pthread_rwlockattr_setkind_np - found
    -- Looking for pthread_yield
    -- Looking for pthread_yield - found
    -- Looking for pthread_yield_np
    -- Looking for pthread_yield_np - not found
    -- Checking prototype pthread_yield for PTHREAD_YIELD_RETURNS_VOID - False
    -- Performing Test PTHREAD_YIELD_RETURNS_INT
    -- Performing Test PTHREAD_YIELD_RETURNS_INT - Success
    -- Performing Test HAVE_GNU_TLS
    -- Performing Test HAVE_GNU_TLS - Success
    -- Performing Test HAVE_C_-Wno-missing-field-initializers
    -- Performing Test HAVE_C_-Wno-missing-field-initializers - Success
    -- Performing Test HAVE_CXX_-Wno-missing-field-initializers
    -- Performing Test HAVE_CXX_-Wno-missing-field-initializers - Success
    -- Performing Test HAVE_C_-Wstrict-null-sentinel
    -- Performing Test HAVE_C_-Wstrict-null-sentinel - Failed
    -- Performing Test HAVE_CXX_-Wstrict-null-sentinel
    -- Performing Test HAVE_CXX_-Wstrict-null-sentinel - Success
    -- Performing Test HAVE_C_-Winit-self
    -- Performing Test HAVE_C_-Winit-self - Success
    -- Performing Test HAVE_CXX_-Winit-self
    -- Performing Test HAVE_CXX_-Winit-self - Success
    -- Performing Test HAVE_C_-Wswitch
    -- Performing Test HAVE_C_-Wswitch - Success
    -- Performing Test HAVE_CXX_-Wswitch
    -- Performing Test HAVE_CXX_-Wswitch - Success
    -- Performing Test HAVE_C_-Wtrampolines
    -- Performing Test HAVE_C_-Wtrampolines - Success
    -- Performing Test HAVE_CXX_-Wtrampolines
    -- Performing Test HAVE_CXX_-Wtrampolines - Success
    -- Performing Test HAVE_C_-Wlogical-op
    -- Performing Test HAVE_C_-Wlogical-op - Success
    -- Performing Test HAVE_CXX_-Wlogical-op
    -- Performing Test HAVE_CXX_-Wlogical-op - Success
    -- Performing Test HAVE_C_-Wno-error=missing-format-attribute
    -- Performing Test HAVE_C_-Wno-error=missing-format-attribute - Success
    -- Performing Test HAVE_CXX_-Wno-error=missing-format-attribute
    -- Performing Test HAVE_CXX_-Wno-error=missing-format-attribute - Success
    -- Performing Test HAVE_C_-Wno-error=address-of-array-temporary
    -- Performing Test HAVE_C_-Wno-error=address-of-array-temporary - Failed
    -- Performing Test HAVE_CXX_-Wno-error=address-of-array-temporary
    -- Performing Test HAVE_CXX_-Wno-error=address-of-array-temporary - Failed
    -- Performing Test HAVE_C_-Wno-error=tautological-constant-out-of-range-compare
    -- Performing Test HAVE_C_-Wno-error=tautological-constant-out-of-range-compare - Failed
    -- Performing Test HAVE_CXX_-Wno-error=tautological-constant-out-of-range-compare
    -- Performing Test HAVE_CXX_-Wno-error=tautological-constant-out-of-range-compare - Failed
    -- Performing Test HAVE_C_-Wno-error=maybe-uninitialized
    -- Performing Test HAVE_C_-Wno-error=maybe-uninitialized - Success
    -- Performing Test HAVE_CXX_-Wno-error=maybe-uninitialized
    -- Performing Test HAVE_CXX_-Wno-error=maybe-uninitialized - Success
    -- Performing Test HAVE_C_-Wno-ignored-attributes
    -- Performing Test HAVE_C_-Wno-ignored-attributes - Failed
    -- Performing Test HAVE_CXX_-Wno-ignored-attributes
    -- Performing Test HAVE_CXX_-Wno-ignored-attributes - Failed
    -- Performing Test HAVE_C_-Wno-error=extern-c-compat
    -- Performing Test HAVE_C_-Wno-error=extern-c-compat - Failed
    -- Performing Test HAVE_CXX_-Wno-error=extern-c-compat
    -- Performing Test HAVE_CXX_-Wno-error=extern-c-compat - Failed
    -- Performing Test HAVE_C_-Wno-pointer-bool-conversion
    -- Performing Test HAVE_C_-Wno-pointer-bool-conversion - Failed
    -- Performing Test HAVE_CXX_-Wno-pointer-bool-conversion
    -- Performing Test HAVE_CXX_-Wno-pointer-bool-conversion - Failed
    -- Performing Test HAVE_C_-fno-rtti
    -- Performing Test HAVE_C_-fno-rtti - Failed
    -- Performing Test HAVE_CXX_-fno-rtti
    -- Performing Test HAVE_CXX_-fno-rtti - Success
    -- Performing Test HAVE_C_-fno-exceptions
    -- Performing Test HAVE_C_-fno-exceptions - Success
    -- Performing Test HAVE_CXX_-fno-exceptions
    -- Performing Test HAVE_CXX_-fno-exceptions - Success
    -- Performing Test HAVE_C_-Wno-error=nonnull-compare
    -- Performing Test HAVE_C_-Wno-error=nonnull-compare - Failed
    -- Performing Test HAVE_CXX_-Wno-error=nonnull-compare
    -- Performing Test HAVE_CXX_-Wno-error=nonnull-compare - Failed
    -- Performing Test HAVE_C_-Wpacked
    -- Performing Test HAVE_C_-Wpacked - Success
    -- Performing Test HAVE_CXX_-Wpacked
    -- Performing Test HAVE_CXX_-Wpacked - Success
    -- Performing Test HAVE_C_-fno-omit-frame-pointer
    -- Performing Test HAVE_C_-fno-omit-frame-pointer - Success
    -- Performing Test HAVE_CXX_-fno-omit-frame-pointer
    -- Performing Test HAVE_CXX_-fno-omit-frame-pointer - Success
    -- Performing Test HAVE_C_-Wno-error=strict-overflow
    -- Performing Test HAVE_C_-Wno-error=strict-overflow - Success
    -- Performing Test HAVE_CXX_-Wno-error=strict-overflow
    -- Performing Test HAVE_CXX_-Wno-error=strict-overflow - Success
    -- Performing Test HAVE_-Wno-error=strict-overflow
    -- Performing Test HAVE_-Wno-error=strict-overflow - Success
    -- Performing Test HAVE_C_-Wextra
    -- Performing Test HAVE_C_-Wextra - Success
    -- Performing Test HAVE_CXX_-Wextra
    -- Performing Test HAVE_CXX_-Wextra - Success
    -- Performing Test HAVE_C_-Wbad-function-cast
    -- Performing Test HAVE_C_-Wbad-function-cast - Success
    -- Performing Test HAVE_CXX_-Wbad-function-cast
    -- Performing Test HAVE_CXX_-Wbad-function-cast - Failed
    -- Performing Test HAVE_C_-Wno-missing-noreturn
    -- Performing Test HAVE_C_-Wno-missing-noreturn - Success
    -- Performing Test HAVE_CXX_-Wno-missing-noreturn
    -- Performing Test HAVE_CXX_-Wno-missing-noreturn - Success
    -- Performing Test HAVE_C_-Wstrict-prototypes
    -- Performing Test HAVE_C_-Wstrict-prototypes - Success
    -- Performing Test HAVE_CXX_-Wstrict-prototypes
    -- Performing Test HAVE_CXX_-Wstrict-prototypes - Failed
    -- Performing Test HAVE_C_-Wmissing-prototypes
    -- Performing Test HAVE_C_-Wmissing-prototypes - Success
    -- Performing Test HAVE_CXX_-Wmissing-prototypes
    -- Performing Test HAVE_CXX_-Wmissing-prototypes - Failed
    -- Performing Test HAVE_C_-Wmissing-declarations
    -- Performing Test HAVE_C_-Wmissing-declarations - Success
    -- Performing Test HAVE_CXX_-Wmissing-declarations
    -- Performing Test HAVE_CXX_-Wmissing-declarations - Success
    -- Performing Test HAVE_C_-Wpointer-arith
    -- Performing Test HAVE_C_-Wpointer-arith - Success
    -- Performing Test HAVE_CXX_-Wpointer-arith
    -- Performing Test HAVE_CXX_-Wpointer-arith - Success
    -- Performing Test HAVE_C_-Wshadow
    -- Performing Test HAVE_C_-Wshadow - Success
    -- Performing Test HAVE_CXX_-Wshadow
    -- Performing Test HAVE_CXX_-Wshadow - Success
    -- Performing Test HAVE_C_-Wcast-align
    -- Performing Test HAVE_C_-Wcast-align - Success
    -- Performing Test HAVE_CXX_-Wcast-align
    -- Performing Test HAVE_CXX_-Wcast-align - Success
    -- Performing Test HAVE_STDCXX0X
    -- Performing Test HAVE_STDCXX0X - Success
    -- MySQL 5.7.25-28
    -- MySQL 5.7.25-28
    -- MySQL 5.7.25-28
    -- MySQL 5.7.25-28
    -- MySQL 5.7.25-28
    -- Looking for CLOCK_REALTIME
    -- Looking for CLOCK_REALTIME - found
    -- tokudb-backup-plugin include backup HotBackup
    -- Building keyring_vault plugin
    -- Performing Test HAVE_PEERCRED
    -- Performing Test HAVE_PEERCRED - Success
    -- Looking for pam_authenticate in pam
    -- Looking for pam_authenticate in pam - found
    -- Looking for getpwnam_r
    -- Looking for getpwnam_r - found
    -- Looking for getgrgid_r
    -- Looking for getgrgid_r - found
    -- Looking for include file security/pam_misc.h
    -- Looking for include file security/pam_misc.h - found
    -- Looking for include file security/openpam.h
    -- Looking for include file security/openpam.h - not found
    -- Performing Test HAVE_UNUSED_TYPEDEFS
    -- Performing Test HAVE_UNUSED_TYPEDEFS - Success
    -- Using Boost headers from /usr/local/boost/boost_1_59_0
    -- Performing Test CXX_HAVE_SIGN_COMPARE
    -- Performing Test CXX_HAVE_SIGN_COMPARE - Success
    -- Performing Test CXX_HAVE_UNUSED_VARIABLE
    -- Performing Test CXX_HAVE_UNUSED_VARIABLE - Success
    -- MYSQLX - Text log of protobuf messages enabled
    -- Performing Test HAVE_UNUSED_PARAMETER
    -- Performing Test HAVE_UNUSED_PARAMETER - Success
    -- Looking for htole64
    -- Looking for htole64 - found
    -- Looking for htole32
    -- Looking for htole32 - found
    -- Looking for htole16
    -- Looking for htole16 - found
    -- Performing Test HAVE_STRUCT_SOCKADDR_SA_LEN
    -- Performing Test HAVE_STRUCT_SOCKADDR_SA_LEN - Failed
    -- Performing Test HAVE_STRUCT_IFREQ_IFR_NAME
    -- Performing Test HAVE_STRUCT_IFREQ_IFR_NAME - Success
    -- Performing Test HAVE_XDR_OPS_X_PUTINT32
    -- Performing Test HAVE_XDR_OPS_X_PUTINT32 - Success
    -- Performing Test HAVE_XDR_OPS_X_GETINT32
    -- Performing Test HAVE_XDR_OPS_X_GETINT32 - Success
    -- Performing Test HAVE___CONST
    -- Performing Test HAVE___CONST - Success
    -- Performing Test HAVE_RPC_INLINE_T
    -- Performing Test HAVE_RPC_INLINE_T - Failed
    -- Performing Test OLD_XDR
    -- Performing Test OLD_XDR - Failed
    -- Performing Test X_GETPOSTN_NOT_USE_CONST
    -- Performing Test X_GETPOSTN_NOT_USE_CONST - Success
    -- Performing Test HAS_INCOMPATIBLE_POINTER_TYPES
    -- Performing Test HAS_INCOMPATIBLE_POINTER_TYPES - Success
    -- Performing Test X_PUTLONG_NOT_USE_CONST
    -- Performing Test X_PUTLONG_NOT_USE_CONST - Failed
    -- RPC_INCLUDE_DIR /usr/include
    -- Googletest was not found. gtest-based unit tests will be disabled. You can run cmake . -DENABLE_DOWNLOADS=1 to automatically download and build required components from source.
    -- If you are inside a firewall, you may need to use an https proxy: export https_proxy=http://example.com:80
    -- Performing Test HAVE_MISLEADING_INDENTATION
    -- Performing Test HAVE_MISLEADING_INDENTATION - Failed
    -- executable target mysqld debug_target /root/db/percona-server-5.7.25-28/debug/sql/mysqld
    -- Library mysqlserver depends on OSLIBS -lpthread;/usr/lib/x86_64-linux-gnu/libz.so;m;rt;crypt;dl
    -- MERGE_CONVENIENCE_LIBRARIES TARGET mysqlserver
    -- MERGE_CONVENIENCE_LIBRARIES LIBS dbug;strings;regex;mysys;mysys_ssl;vio;/usr/lib/x86_64-linux-gnu/libz.so;yassl;taocrypt;crypt;dl;blackhole_embedded;partition_embedded;federated_embedded;heap_embedded;archive_embedded;myisam_embedded;myisammrg_embedded;innobase_embedded;lz4_lib;csv_embedded;ngram_parser_embedded;sql_embedded
    -- MERGE_CONVENIENCE_LIBRARIES MYLIBS dbug;strings;regex;mysys;mysys_ssl;vio;yassl;taocrypt;blackhole_embedded;partition_embedded;federated_embedded;heap_embedded;archive_embedded;myisam_embedded;myisammrg_embedded;innobase_embedded;lz4_lib;csv_embedded;ngram_parser_embedded;sql_embedded
    -- library target mysqlserver debug_target /root/db/percona-server-5.7.25-28/debug/archive_output_directory/libmysqld.a
    -- INSTALL perconaserverclient.pc lib/pkgconfig
    -- CMAKE_BUILD_TYPE: RelWithDebInfo
    -- COMPILE_DEFINITIONS: _GNU_SOURCE;_FILE_OFFSET_BITS=64;__STDC_WANT_LIB_EXT1__=1;HAVE_CONFIG_H;HAVE_LIBEVENT1
    -- CMAKE_C_FLAGS:  -Wall -Wextra -Wformat-security -Wvla -Wwrite-strings -Wdeclaration-after-statement
    -- CMAKE_CXX_FLAGS:  -Wall -Wextra -Wformat-security -Wvla -Woverloaded-virtual -Wno-unused-parameter
    -- CMAKE_C_LINK_FLAGS: 
    -- CMAKE_CXX_LINK_FLAGS: 
    -- CMAKE_C_FLAGS_RELWITHDEBINFO: -O3 -D_FORTIFY_SOURCE=2 -g -fabi-version=2 -fno-omit-frame-pointer -fno-strict-aliasing -DDBUG_OFF -DNDEBUG
    -- CMAKE_CXX_FLAGS_RELWITHDEBINFO: -O3 -D_FORTIFY_SOURCE=2 -g -fabi-version=2 -fno-omit-frame-pointer -fno-strict-aliasing -DDBUG_OFF -DNDEBUG
    -- Configuring done
    CMake Warning (dev) at storage/tokudb/PerconaFT/portability/CMakeLists.txt:23 (add_dependencies):
      Policy CMP0046 is not set: Error on non-existent dependency in
      add_dependencies.  Run "cmake --help-policy CMP0046" for policy details.
      Use the cmake_policy command to set the policy and suppress this warning.
      
      The dependency target "build_jemalloc" of target
      "tokuportability_static_conv" does not exist.
    This warning is for project developers.  Use -Wno-dev to suppress it.
    
    -- Generating done
    -- Build files have been written to: /root/db/percona-server-5.7.25-28/bld
  ```
  </details>

2. `make -j40`
3. `make -j40 test`
4. `make install`
5. 进`PREFIX`目录检查MySQL安装

# 测试
1. `su - mysql` 
2. `cd /usr/local/mysql-5.7.25-28/mysql-test`
3. `./mtr ./t/*test -parallel=40 -skip-test-list=skip_test_file`
```
$ cat skip_test_file
events_bugs:skip
myisam_explain_json_non_select_all:skip
myisam_explain_json_non_select_none:skip
ssl_ca:skip
events_1:skip
file_contents:skip
```
<details>
  <summary>mtr test结果</summary>
  
```
[ 97%] tokudb.type_varchar 'non-native-partitioning' w36 [ pass ]   4765
[ 97%] main.join_outer_bka                      w7 [ pass ]   2844
[ 97%] main.join_outer_bka_nixbnl               w33 [ pass ]   1578
[ 97%] main.mysql_upgrade_with_session_user     w32 [ pass ]   3041
[ 97%] main.subquery_nomat_nosj_bka             w11 [ pass ]  19506
[ 97%] main.no_binlog_gtid_empty_statement      w13 [ pass ]     52
[ 98%] main.partition_mgm_err2                  w22 [ pass ]    115
[ 98%] main.no_binlog_gtid_next_temporary_table w27 [ pass ]    216
[ 98%] main.innodb_mrr                          w21 [ pass ]  17819
[ 98%] main.subquery_sj_mat_bka_nixbnl          w14 [ pass ]   6403
[ 98%] main.subquery_sj_firstmatch_bka_nixbnl   w24 [ pass ]   7744
[ 98%] main.subquery_sj_loosescan_bka           w40 [ pass ]   7689
[ 98%] main.subquery_sj_loosescan_bka_nixbnl    w23 [ pass ]   8545
[ 98%] main.mysqldump_restore                   w29 [ pass ]   5871
[ 98%] main.subquery_sj_loosescan               w17 [ pass ]   7973
[ 98%] tokudb.type_temporal_fractional 'native-partitioning' w37 [ pass ]  133084
[ 98%] main.subquery_sj_mat_nosj                w26 [ pass ]   7521
[ 98%] main.subquery_none                       w19 [ pass ]  11031
[ 99%] main.subquery_sj_mat_bka                 w9 [ pass ]   1995
[ 99%] main.mysqlslap                           w34 [ pass ]  12893
[ 99%] main.mysqldump                           w25 [ pass ]  27127
[ 99%] main.backup_locks_binlog_row             w28 [ pass ]  29128
[ 99%] tokudb.type_temporal_fractional 'non-native-partitioning' w3 [ pass ]  18045
[ 99%] main.subquery_nomat_nosj                 w20 [ pass ]   6991
[ 99%] main.subquery_none_bka                   w6 [ pass ]   6964
[ 99%] main.subquery_none_bka_nixbnl            w5 [ pass ]   6998
[ 99%] main.backup_locks_binlog_mixed           w1 [ pass ]  30359
[ 99%] main.mysql_upgrade                       w2 [ pass ]  50184
[ 99%] main.proxy_protocol                      w35 [ pass ]  120102
[ 99%] main.backup_locks_binlog_stmt            w39 [ pass ]  33535
[100%] main.mysqltest                           w15 [ pass ]  46692
--------------------------------------------------------------------------
The servers were restarted 268 times
Spent 4243.478 of 202 seconds executing testcases

Completed: All 1037 tests were successful.

193 tests were skipped, 80 by the test itself.
```

</details>

# 启动
1. MySQL实例初始化
2. MySQL实例启动

# 安装脚本

# 小结

# 常见问题
