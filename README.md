# staticmysqldump
static linux mysqldump binary

from mariadb mysqldump revision f1e13fdc8d9e78f4529aa60b6a9b49c6ff063c66 : https://github.com/MariaDB/server/blob/f1e13fdc8d9e78f4529aa60b6a9b49c6ff063c66/client/mysqldump.c

./staticmysqldump --version
staticmysqldump  Ver 10.17 Distrib 10.5.2-MariaDB, for Linux (x86_64)

created with static libopenssl 1.1.1d from the instructions at https://stackoverflow.com/a/56394968/1067003

don't remember exactly how i made it, but roughly:
```sh
mkdir build
cd build
export CFLAGS='-static'
export CPPFLAGS='-static'
export LDFLAGS='-static'
cmake .. -Dwith-ssl=system -Dopenssl-dir=static_openssl_1.1.1d_path
cd client
make -j $(nproc)
```
(not exactly that, but something close to that)
