`godefv/math` is a pure C++ template library, which does not support running on GPU. 

The issue when targeting GPUs is that kernels need to be compiled for GPUs, and C++ does not target GPUs.
But C++ is a nice language and we want to use it. That's why the SYCL standard has been created.

The aim of this repository is to show how to use SYCL to run `godefv/math` on GPU.
`triSYCL` is the only open source implementation I have found at this time, and it seems good enough.

Actually, SYCL implementations targetting GPUs need to compile C++ for GPUs, so that C++ becomes a valid language for GPUs.
This achievement can be reached by using the SPIR standard, which I believe has been made toward this purpose. 
SPIR is a standard for binary representations of code, so that any C++ compiler having an intermediate binary representation can convert it to SPIR and then to any device specific format (CPUs, GPUs, etc).

Unfortunately, it seems that only LLVM does that for now. Actually, LLVM IR might have inspired SPIR. And LLVM does not support C++ Concepts yet.

To conclude, I need to wait for a compiler with an intermediate binary representation convertible to SPIR, which also support SYCL, C++17 and C++ Concepts. And I need a SYCL implementation which accepts this compiler as a back-end.

