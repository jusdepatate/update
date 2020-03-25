# `update`

This tiny CLI tools will `git pull` & recompile software automatically.

This tool is not perfect, feel free to open issues and Pull Requests

## Configuration
Edit `$BUILDFOLDER` and `$CPU_CORES` with your needs, by default they are respectivly set at `$HOME/buid` and `$(nproc)`

In `$BUILDFOLDER` you can create a file named with the software you want to install + `-compilation` containing commands to execute to compile the software.
<br>Examples:
- `warzone2100-compilation`
```
./autogen.sh
./configure --with-distributor=jusdepatate
cmake -H. -Bbuild -DCMAKE_BUILD_TYPE=RelWithDebInfo -DCMAKE_INSTALL_PREFIX:PATH=/usr/ -GNinja
sudo cmake --build build --target install
```

## Arguments
For now there's only 2 command arguments:
* `-h` | `--help` - shows help and outputs useful variables (`$BUILDFOLDER` & `$CPU_CORES`)
* `-f` | `--force` - force `git pull` & compilation (**can also be passed as a variable** ex: `FORCE=1 update all`)

You can pass one or more softwares to build, be sure git repo is cloned in your `$BUILDFOLDER`
