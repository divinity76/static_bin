
```bash
docker build -t mysqldump .
docker cp $(docker create mysqldump:latest):/mysqldump .

file mysqldump
mysqldump: ELF 64-bit LSB executable, x86-64, version 1 (GNU/Linux), statically linked, BuildID[sha1]=45f33e7053e827e829a17a1d1f5eee1b6172946f, for GNU/Linux 3.2.0, stripped

ldd mysqldump
	not a dynamic executable
```

