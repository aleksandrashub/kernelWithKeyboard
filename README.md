![Снимок экрана_20240422_153757](https://github.com/aleksandrashub/kernelWithKeyboard/assets/115869636/50cd24e5-4ce7-465a-bfe7-9d723cdc6abd)

Ядро с поддержкой клавиатуры

Как запустить ядро.
1. Перемещаем все файлы в одну папку
2. Далее cd /название папки с файлами\
3.nasm -f elf32 kernel.asm -o kasm.o
4. gcc -fno-stack-protector -m32 -c kernel.c -o kc.o
5.ld -m elf_i386 -T link.ld -o kernel kasm.o kc.o
6. Запускаем на эмуляторе с помощью команды qemu-system-i386 -kernel kernel
7. Пробуйте ввести текст
   
