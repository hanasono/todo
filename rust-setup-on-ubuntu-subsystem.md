## end result

https://hanasono.github.io/todo/Emscripten-Generated%20Code.html

really need to have a wasm processor for this

## pre-requisites

* python
* cmake
* java

``sudo apt-get update && sudo apt-get install build-essential``

``sudo apt-get install python``

``sudo apt-get install default-jre``

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
$ ./emsdk install latest
$ ./emsdk install latest
$ source ./emsdk_env.sh
```

installing new sdk takes fairly long


## compile and serve as web

classic hello.rs
```
fn main() {
    println!("Hello World!");
}
```

```
$ rustc --target=asmjs-unknown-emscripten hello.rs -o hello.html
```

this generates an html that uses wasm empowered hello.js

then it could be served by nodejs with static html outpt

```
var connect = require('connect');
var serveStatic = require('serve-static');
connect().use(serveStatic(__dirname)).listen(8080, function(){
    console.log('Server running on 8080...');
});
```
