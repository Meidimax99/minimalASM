# Minimal ASM
This is a minimal project to get some riscv Assembly running on qemu. 

# Usage
You can use `make` to build and link the project and `make qemu` to also start it in qemu. Since there is no output using a UART implemented, there will not be much to see.
To debug and single-step your assembly program, you can use the `make gdb-qemu` rule. This stars qemu and halts the execution until you resume it with a remote debugger.
To connect GDB, open another terminal and enter `gdb kernel` to start the debugging session with the kernel executable.
In the debugger use `target remote:26000` to connect to the debugging session.
While still in the debugger you can then press "CTRL + x + a" to open the TUI interface. There you can switch to the asm layout using `layout asm`.
Now you can single-step through your assembly program using the si (short for "single-step") command. The first few instructions will probably be some initcode from Qemu. 