# 02 编写MBR  

    nasm -o mbr.bin mbr.S

    bximage -hd=60M -imgmode=flat -mode=create -q hd60M.img

    dd if=mbr.bin of=hd60M.img bs=512 count=1 conv=notrunc

    bochs -f bochsrc-sample.txt

![](https://raw.githubusercontent.com/ejunjsh/myos/master/exercises/ch02/ScreenShot.png)