##  Build ImageMagick for Android

### Make the toolchains

```
$ ./build/tools/make-standalone-toolchain.sh --platform=android-19 --ndk-dir=/pathto/ndk/android-ndk-r9c --install-dir=/tmp/ig/arm-19-toolchain
$ ./build/toolsmake-standalone-toolchain.sh --platform=android-19 --ndk-dir=/pathto/ndk/android-ndk-r9c --install-dir=/tmp/ig/x86-19-toolchain --arch=x86
$ ./build/tools/make-standalone-toolchain.sh --platform=android-19 --ndk-dir=/pathto/ndk/android-ndk-r9c --install-dir=/tmp/ig/mips-19-toolchain --arch=mips

```

### Setting up environment

```
$ export PATH=.:/tmp/ig/arm-19-toolchain/bin:$PATH
$ export C_INCLUDE_PATH=/tmp/ig/arm-19-toolchain/sysroot/usr/include
$ export CPLUS_INCLUDE_PATH=/tmp/ig/arm-19-toolchain/sysroot/usr/include

```

### Download ImageMagick source code

Extract it to /tmp/ig/imgic-6.8.8/, i.e.


### Build fftw

Download fftw source code and extract to somewhere.

```
$ ./configure --host=arm-linux-androideabi --disable-shared --prefix=/tmp/ig/imgic-6.8.8/fftw --libdir=/tmp/ig/imgic-6.8.8/fftw --includedir=/tmp/ig/imgic-6.8.8/fftw
$ make
$ make install
```

### Build libjpeg

Download libjpeg source code and extract to somewhere.

```
$ ./configure --host=arm-linux-androideabi --disable-shared --prefix=/tmp/ig/imgic-6.8.8/jpeg --libdir=/tmp/ig/imgic-6.8.8/jpeg --includedir=/tmp/ig/imgic-6.8.8/jpeg
$ make
$ make install
```

### Build libpng

Download libpng source code and extract to somewhere.

```
$ ./configure --host=arm-linux-androideabi --disable-shared --prefix=/tmp/ig/imgic-6.8.8/jpeg --libdir=/tmp/ig/imgic-6.8.8/jpeg --includedir=/tmp/ig/imgic-6.8.8/jpeg
$ make
$ make install
```

### Setting up pkgconfig path

```
export PKG_CONFIG_PATH=/tmp/ig/imgic-6.8.8/fftw/pkgconfig:/tmp/ig/imgic-6.8.8/png/pkgconfig

```

### Build ImageMagick

```
$ ./configure --host=arm-linux-androideabi --prefix=/tmp/ig/imgic-out --disable-shared --disable-opencl --disable-largefile --without-perl --without-x --disable-openmp --without-bzlib --without-freetype --without-rsvg --enable-delegate-build
$ make 
$ make install
```

Binaries and libraries will output in /tmp/ig/imgic-out




