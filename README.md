Visual Studio Code project for Linux kernel sources SO2 edition
===============================================================

This is tested on a linux, not sure if this works on Windows.

Clone the repo as the `.vscode` folder in your workspace directory.
- for https
```
git clone https://github.com/NethDR/vscode-linux-kernel-so2.git .vscode
```
- for ssh
```
git clone git@github.com:NethDR/vscode-linux-kernel-so2.git .vscode
```

Make sure to export the path to the linux kernel root as the `KDIR` env variable:

```
echo "export KDIR=/path/to/linux/kernel" >> ~/.bashrc
```

Alternatively, you can modify the `tasks.json` file directly and replace the `${env:KDIR}` appearances with the path.



To make intellisense work, you need to generate a `compile_commands.json` file.

First, make sure the kernel is built (if you ran the `make boot` command during any lab, that should have done it)

Now, make sure your module compiles correctly (you need to provide a `Kbuild` file and at least a [dummy implementation] of the module).

Open your `Kbuild` file in the editor and press `F6`, and select `Generate compile_commands.json`.

Done.

[dummy implementation]: https://linux-kernel-labs.github.io/refs/heads/master/so2/lab1-intro.html#an-example-of-a-kernel-module