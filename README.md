# C / C++ to WASM

## Autores
[Juan Carlos Quirino](github.com/quirinoc)
[Francisco Marquez](github.com/FranciscoMarquez1)

### Tutorial de como utilizar C y C++ para compilar a WASM

Descargar emsdk
```sh
$ git clone https://github.com/emscripten-core/emsdk.git
$ cd emsdk
$ ./emsdk install latest
$ ./emsdk activate latest
```

Activar entorno
```sh
$ git clone https://github.com/emscripten-core/emsdk.git
$ cd emsdk
$ ./emsdk install --build=Release sdk-incoming-64bit binaryen-master-64bit
$ ./emsdk activate --build=Release sdk-incoming-64bit binaryen-master-64bit
$ source ./emsdk_env.sh --build=Release
```

# Server

Todos los archivos se corren con el servidor de python
```sh
python3 -m http.server 8080
```

## Ejemplo 1 Hello World de C a WASM

helloc.c
```c
#include <stdio.h>
int main(int argc, char ** argv) {
  printf("Hello, world!\n");
}
```
Compilar con:
```sh
emcc hello.c -o helloc.html
```
Correr helloc para mostrar salida

## Ejemplo 2 Hello World de C++ a WASM

helloc.c
```c
#include <iostream>

int main(){
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```
Compilar con:
```sh
em++ hello.cpp -o hellocpp.html
```
Correr hellocpp para mostrar salida

## Ejemplo 3 Calcular secuencia de Fibonacci en C a WASM

helloc_fib.c
```c
#include <stdio.h>

int fib(int n){
    if(n == 0 || n == 1)
        return 1;
    else
        return fib(n - 1) + fib(n - 2);
}

int main(){
    printf("Hello world!\n");
    int res = fib(5);
    printf("fib(5) = %d\n", res);
    return 0;
}
```
Compilar con:
```sh
emcc helloc_fib.c -o helloc_fib.html
```
Correr helloc_fib.html para mostrar salida

