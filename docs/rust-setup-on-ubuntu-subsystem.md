## pre-requisites

* python
* cmake

``sudo apt-get update && sudo apt-get install build-essential``

``sudo apt-get install python``

## install rust with rustup

```
curl https://sh.rustup.rs -sSf | sh
```

>This will download and install the official compiler for the Rust programming language, and its package manager, Cargo.
>
>It will add the cargo, rustc, rustup and other commands to Cargo's bin directory, located at: ``/home/hanasono/.cargo/bin``
>
>This path will then be added to your PATH environment variable by modifying the profile file located at: ``/home/hanasono/.profile``

## install emscripten

```
$ wget https://s3.amazonaws.com/mozilla-games/emscripten/releases/emsdk-portable.tar.gz
$ tar -xvf emsdk-portable.tar.gz
$ cd emsdk_portable/
$ ./emsdk update
$ ./emsdk install sdk-incoming-64bit
```

installing new sdk takes fairly long

