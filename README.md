# static_bin
semi-static ncdu

created with https://github.com/divinity76/converttostatic

log
```
hans@devad22:~/projects/static_bin$ ../converttostatic/src/linux/converttostatic.php "$(which ncdu)"
Warning: will not bundle dependency "libc.so.6" (known-to-cause-trouble when bundled..)
cpptaring /lib/x86_64-linux-gnu/libncursesw.so.6... done: 0.10s
cpptaring /lib/x86_64-linux-gnu/libtinfo.so.6... done: 0.08s
cpptaring /lib/x86_64-linux-gnu/libdl.so.2... done: 0.01s
cpptaring /lib64/ld-linux-x86-64.so.2... done: 0.13s
cpptaring /usr/bin/ncdu... done: 0.03s
cmd:
g++ -std=c++17 -Wall -Wextra -Wpedantic -Werror -static -s -Os -o 'ncdu' 'ncdu.cpp'
```
