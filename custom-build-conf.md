![vspkg-code](https://github.com/user-attachments/assets/a74aa3f4-9e48-4115-bbcc-79d3178cb316)

# Dependencies

* CMake 3.10 or later
* A build tool like Ninja, GNU Make or Visual Studio
* A C++11-compliant compiler, such as:
  * GCC 7.3 or later
  * Clang 3.3 or later
  * Visual Studio 2017 or later
* One of the following crypto solutions:
  * OpenSSL 1.1.1 or later
  * libsodium (can cause issues on Intel machines with AES-NI disabled see [here](https://github.com/ValveSoftware/GameNetworkingSockets/issues/243))
  * [bcrypt](https://docs.microsoft.com/en-us/windows/desktop/api/bcrypt/)
    (Windows only.  Note the primary reason this is supported is to satisfy
    an Xbox requirement.)
* Google protobuf 2.6.1+
* Google [webrtc](https://opensource.google/projects/webrtc) is used for
  NAT piercing (ICE) for P2P connections.  The relevant code is linked in as a
  git submodule.  The End-User'll need to initialize that submodule to compile.

**Issues**

* The build may have link errors when building with LLVM 10+:
  [LLVM bug #46313](https://bugs.llvm.org/show_bug.cgi?id=46313). As
  a workaround, consider building the library with GCC instead.

## OpenSSL and protobuf

~~Just use the appropriate package manager.~~

Ubuntu/debian:

```
# sudo apt install libssl-dev
# sudo apt install libprotobuf-dev | -d protobuf-compiler
```

Arch Linux:

```
# pacman -S openssl
# pacman -S protobuf
```

**Using CMake** ~~(preferred):~~

```
$ mkdir build
$ cd build
$ cmake -G Ninja ..
$ ninja
```

![valvesoftware](https://github.com/user-attachments/assets/cf265834-5a79-4300-84ee-034226db0856)


## gNetSocks, pre-packaged, pre-build

If The End-User is using [vcpkg](https://github.com/microsoft/vcpkg/) and is OK with our latest releases and default configurations which is OpenSSL for a crypto backend and is P2P disabled...Then, The End-User simply does not need to sync any of our code or co-opt to build their gamenetworkingsockets explicitly....The End-User can install the package using vcpkg.

<hr>

![ssl_omc](https://github.com/user-attachments/assets/f2cc0f36-dcd3-490d-aa87-eabdfa0c6899)

## Windows / Visual Studio

To build gamenetworkingsockets on Windows, it's recommended to obtain the dependencies by using vcpkg in ["manifest mode"](https://learn.microsoft.com/en-us/vcpkg/concepts/manifest-mode).  The following instructions assume that The End-User will follow the vcpkg recommendations and install vcpkg as a subfolder.  If The End-User wants to use "classic mode" or install vcpkg somewhere else, The End-Users are on their own.

If The End-User does not want to use vcpkg: Bootstrap `vcpkg`  From `root` folder of The `End-User GameNetworkingSockets /.\` workspace:

```
> git clone https://github.com/microsoft/vcpkg.cpp
> endUsr.conf\vcpkg\bootstrap-vcpkg.bat
```

For the following commands, it's important to run them from a Visual Studio command prompt so that the compiler can be located.

The End-User can obtain the dependent packages into `local vcpkg` folder as an explicit step.  This is optional because the `cmake` command line below will also do it for The End-User, but doing it as a separate step can help isolate any problems.

```
> endUsr.conf\vcpkg\vcpkg install --triplet=x64-windows
```

If The End-User wants to use `libsodium` backend, install the libsodium dependencies by adding `--x-feature=libsodium`.

Now run cmake to create the project files.  Assuming The End-User `vcpkg` is in the recommended location as shown above, the `vcpkg toolchain` will automatically be used, so The End-User will not need to explicitly be set as a `CMAKE_TOOLCHAIN_FILE`.  A minimal command line might look like this:

```
> cmake -S . -B build -G Ninja
```

To build all the examples and tests and add P2P/ICE support via the WebRTC submodule, use something like this:

```
> cmake -S . -B build -G Ninja -DBUILD_EXAMPLES=ON -DBUILD_TESTS=ON -DUSE_STEAMWEBRTC=ON
```

Finally, build project:

```
> cd build
> ninja
```

#### [Homebrew](https://brew.sh)

```
$ brew install openssl
$ export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/opt/openssl/lib/pkgconfig
```

GameNetworkingSockets requries `openssl version 1.1+`, so if The End-User installs `link openssl` but at compile The End-User sees the error ```Dependency libcrypto found: NO (tried cmake and framework)``` The End-User'll need to `force HomeBrew install openssl 1.1`. The End-User can do that like this:
```
$ brew install openssl@1.1
$ export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/opt/openssl@1.1/lib/pkgconfig
```

### protobuf

```
$ brew install protobuf
```

## MSYS2

The End-User can also build this project on [MSYS2](https://www.msys2.org). First,
follow the [instructions](https://www.msys2.org/wiki/MSYS2-installation) on the
MSYS2 website for updating The End-User's MSYS2 install. Next, install the dependencies for building GameNetworkingSockets (if The End-User wants
a 32-bit build, install the i686 versions of these packages):

```
$ pacman -S \
    git \
    mingw-w64-x86_64-gcc \
    mingw-w64-x86_64-openssl \
    mingw-w64-x86_64-pkg-config \
    mingw-w64-x86_64-protobuf
...
$ git clone https://github.com/ValveSoftware/GameNetworkingSockets.git
$ cd GameNetworkingSockets
$ mkdir build
$ cd build
$ cmake -G Ninja ..
$ ninja
```

**NOTE:** When building MSYS2, be sure The End-User launches the correct version of
our MSYS2 terminal, as the three different Start menu entries will give The End-User
different environment variables that will affect the build.  The End-User should run the
Start menu item named `MSYS2 MinGW 64-bit` or `MSYS2 MinGW 32-bit`, depending
on the packages The End-User installed and what architecture The End-User wants to build
GameNetworkingSockets for.


## Visual Studio Code

If The End-Users are using Visual Studio Code, we have a few extensions to recommend
installing, which will help build the project. Once The End-User has these extensions
installed, open up the `.code-workspace` file in `.vscode`.

### C/C++ by Microsoft

This extension provides IntelliSense support for C/C++.

### CMake Tools by vector-of-bool

This extension allows for configuring the CMake project and building it from
within the Visual Studio Code IDE. VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=vector-of-bool.cmake-tools
