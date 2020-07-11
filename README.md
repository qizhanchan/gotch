# GoTch - Libtorch Go Binding


## Overview

- **GoTch** is a C++ Libtorch Go binding for developing and implementing deep
    learning projects in Go.

- It is currently in heavy development mode and is considered **unstable** until
    version v1.0.0 is marked. Hence, one can use it with own risk. 

- This package is to create a thin wrapper of Libtorch to make use of
    its tensor APIs and CUDA support while implementing as much
    idiomatic Go as possible. 

## Dependencies

- **Libtorch** C++ library of [Pytorch](https://pytorch.org/)

## How to use

### 1. Libtorch installation

- Make sure that a libtorch version 1.5.0 (either CPU or CUDA support) is
    installed in your system (default at "/opt/libtorch" in Linux/Mac OS). 

### 2. Import **GoTch** package

```go
    package main

    import(
        "fmt"
        
        "github.com/sugarme/gotch"
    )

    func main(){
        
        var d gotch.Cuda
        fmt.Printf("Cuda device count: %v\n", d.DeviceCount())
        fmt.Printf("Cuda is available: %v\n", d.IsAvailable())
        fmt.Printf("Cudnn is available: %v\n", d.CudnnIsAvailable())

    }
```

- Other examples can be found at `example` folder

## [Documentations](docs/README.md)

## [Examples](example/README.md)


### 3. Notes on running examples

- Clean Cgo cache to get a fresh build as [mention here](https://github.com/golang/go/issues/24355)

```bash
    # Either
    go clean -cache -testcache .
    go run [EXAMPLE FILES]

    # Or
    go build -a

    go run [EXAMPLE FILES]

```


## Acknowledgement

- This projects has been inspired and used many concepts from [tch-rs](https://github.com/LaurentMazare/tch-rs)
    Libtorch Rust binding. 



