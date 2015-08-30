This patch makes LuaJIT build with stubbed FFI, allowing it to work on Vita
to build, apply the patch to a luajit tarball using
```
patch -p1 < luajit.patch
```
then build with
```
make CFLAGS="-DLUAJIT_USE_SYSMALLOC -DLJ_FFI_STUB -DLUAJIT_DISABLE_JIT" HOST_CC="gcc -m32" CROSS=arm-vita-eabi- TARGET=arm BUILDMODE=static TARGET_SYS=vita
```
which makes everything sort of work.
finally, ```make install``` as usual.
