![Снимок экрана_20240422_153757](https://github.com/aleksandrashub/kernelWithKeyboard/assets/115869636/50cd24e5-4ce7-465a-bfe7-9d723cdc6abd)

Ядро с поддержкой клавиатуры

ПО для сборки:
-Qemu KVM
-NASM
-GCC
-GNU linker
Собрать кросс-компилятор gcc для i386 архитектуры процессора


Как запустить ядро.
1. Устанавливаем необходимое программное обеспечение для сборки проекта: nasm, qemu kvm, gcc. Для установки i386elfgcc:
   wget http://newos.org/toolchains/i386-elf-4.9.1-Linux-x86_64.tar.xz
   mkdir /usr/local/i386elfgcc
   tar -xf i386-elf-4.9.1-Linux-x86_64.tar.xz -C /usr/local/i386elfgcc --strip-components=1
   export PATH=$PATH:/usr/local/i386elfgcc/bin
3. Перемещаем все файлы в одну папку
4. Далее cd /название папки с файлами
5. Прописываем команды:
   nasm -f elf32 kernel.asm -o kasm.o
   gcc -fno-stack-protector -m32 -c kernel.c -o kc.o
   ld -m elf_i386 -T link.ld -o kernel kasm.o kc.o
6. Запускаем на эмуляторе с помощью команды:
   qemu-system-i386 -kernel kernel
7. Пробуйте ввести текст
   
