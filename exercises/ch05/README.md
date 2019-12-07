    
    nasm -I include -o mbr.bin mbr.S

    nasm -I include -o loader.bin loader.S

    bximage -hd=60M -imgmode=flat -mode=create -q hd60M.img

    dd if=mbr.bin of=hd60M.img bs=512 count=1 conv=notrunc

    dd if=loader.bin of=hd60M.img bs=512 seek=2 count=4 conv=notrunc

    i386-elf-gcc -c -o kernel/main.o  kernel/main.c 
    
    i386-elf-ld kernel/main.o -Ttext 0xc0001500 -e main -o kernel/kernel.bin 
    
    dd if=kernel/kernel.bin of=hd60M.img bs=512 count=200 seek=9 conv=notrunc 

    bochs -f bochsrc-sample.txt