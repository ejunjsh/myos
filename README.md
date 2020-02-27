# myos

my os practice

## precondition

all exercises is running in macos and please install `bochs` and `nasm` before

    brew install bochs nasm

from `ch05`, need `i386-elf-binutils` and `i386-elf-gcc` to build kernel

    brew tap nativeos/i386-elf-toolchain 
    brew install i386-elf-binutils i386-elf-gcc

## build

    make clean all
    cd command
    sh compile.sh
    cd -
    bochs -f bochsrc-sample.txt

## screen shot

![](https://raw.githubusercontent.com/ejunjsh/myos/master/ScreenShot.png)

## reference

[操作系统真相还原](https://book.douban.com/subject/26745156/)