# Photon JIT - A JIT Assembler for Nim

Photon JIT is a JIT Assembler for Nim.

The project is lifted out of my [Laser research repo](https://github.com/numforge/laser)

## Usage

For now very few opcodes are implemented, but they are just enough to have a usable and fast BrainFuck VM.

```bash
git clone https://github.com/mratsim/photon-jit
cd photon-jit
mkdir build
nim c -d:release -o:build/ex02 examples/ex02_jit_brainfuck_vm.nim

# And now run one of the examples
build/ex02 examples/ex02_jit_brainfuck_src/mandelbrot.bf
```

## Future ambitions

The targeted use-case is to produce high performance compute kernels for
scientific computing and machine learning, in particular specialized kernels
for very small matrices where techniques for big matrices (GEMM) incur
too much overhead. This is key to optimize convolutions on CPU for deep learning.

This means that:

- Photon JIT should be made thread-safe
- Photon JIT should support caching
- Photon JIT should have a low overhead

Additional domains considered are:
- parsers
- emulators (dynarec)
- interpreters and virtual machines
