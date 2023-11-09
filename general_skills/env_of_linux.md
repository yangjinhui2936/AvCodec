## linux下环境变量

**如何查看环境变量？**
可以使用env命令查看当前环境变量，也可以使用echo命令输出环境变量值。
**在Linux下，环境变量是一些系统级别的变量，用于存储关键信息和配置参数。以下是常见的几个环境变量：**
1. PATH：定义可执行文件的搜索路径。当你在终端中输入命令时，操作系统会根据PATH变量中指定的路径来查找可执行文件。
2. HOME：指定当前用户的主目录路径。
3. LD_LIBRARY_PATH：定义共享库（动态链接库）的搜索路径，让可执行文件能够找到所需要的共享库。
4. LANG/LC_ALL：指定系统的语言环境。
5. JAVA_HOME：指定Java开发工具包（JDK）的安装路径。

**如何设置环境变量？**

1. 在终端中使用export命令进行临时设置：
   ```
   export VARIABLE_NAME=value
   ```
2. 编辑用户的`.bashrc`或`.bash_profile`文件，将环境变量添加到文件末尾，并使用source命令使其生效：
   ```
   echo 'export VARIABLE_NAME=value' >> ~/.bashrc
   source ~/.bashrc
   ```
**如果要编译一个可执行文件，需要设置哪些环境变量？**

1. PATH：确保编译器和构建工具可执行文件所在的路径包含在PATH中，这样就可以直接运行它们。
2. C_INCLUDE_PATH/CPLUS_INCLUDE_PATH：如果项目中使用了C/C++头文件，这些路径应该包含在这些变量中，以供编译器查找。
3. LD_LIBRARY_PATH：如果项目中使用了共享库，这些路径应该包含在LD_LIBRARY_PATH中，以供运行时系统查找。

**已经设置的环境变量的生命周期？**
环境变量是在用户登录时或者在启动一个新的终端会话时设置的。当你在终端中进行临时设置时，该设置仅对当前终端会话有效。为了让环境变量永久生效，需要将其添加到用户的配置文件（如`.bashrc`）中，或者在系统级别设置，这样它们将适用于所有用户和进程。

**在C/C++中有哪些常见的环境变量？**

1. `PATH`: `PATH`环境变量用于指定操作系统查找可执行文件的路径。在C/C++中，可以将编译器（如GCC或Clang）的路径添加到`PATH`中，使其在任何目录下都可被调用。
   例如，在Linux或Mac上，可以使用以下命令将GCC编译器路径添加到`PATH`中：
   ```
   export PATH=$PATH:/usr/local/bin
   ```
2. `C_INCLUDE_PATH`和`CPLUS_INCLUDE_PATH`: 这两个环境变量用于指定C和C++编译器在编译过程中要搜索头文件的路径。
   例如，在Linux或Mac上，可以使用以下命令将包含一个名为`my_header.h`的自定义头文件的路径添加到`C_INCLUDE_PATH`中：
   ```
   export C_INCLUDE_PATH=$C_INCLUDE_PATH:/path/to/my/header/directory
   ```
*如果将包含一个名为my_header.h的自定义头文件的路径添加到C_INCLUDE_PATH中，程序中需要引用该头文件时应该如何引用？*
#include "my_header.h"
在上面的示例中，假设my_header.h位于你添加到C_INCLUDE_PATH环境变量中的路径中。编译器将根据C_INCLUDE_PATH中的路径查找并包含该头文件。
请注意，使用双引号""而不是尖括号<>来引用头文件，以指示编译器按照相对路径或包含路径进行查找。如果你使用尖括号<>，则编译器将只在默认系统头文件路径中查找。

3. `LD_LIBRARY_PATH`: `LD_LIBRARY_PATH`环境变量用于指定动态链接器在执行可执行文件时搜索共享库的路径。这对于在运行时加载动态链接库非常有用。

   例如，在Linux或Mac上，可以使用以下命令将共享库的路径添加到`LD_LIBRARY_PATH`中：
   ```
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/path/to/shared/library
   ```
例如：如果执行ffmpeg可执行程序时报错，则可能需要将ffmpeg库的路径添加到LD_LIBRARY_PATH中。
```shell
export LD_LIBRARY_PATH=/path/to/library:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH=/data1/yang/tool/ffmpeg-3.4.4/output/lib:$LD_LIBRARY_PATH
```

这些是在C/C++中常见的一些环境变量，用于设置编译器和构建系统的行为。根据不同的操作系统和构建工具，可能还有其他可用的环境变量。