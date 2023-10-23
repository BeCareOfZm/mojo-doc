为什么选择mojo
===============

When we started Modular, we had no intention of building a new programming language. But as we were building our platform to unify the world’s ML/AI infrastructure, we realized that programming across the entire stack was too complicated. Plus, we were writing a lot of MLIR by hand and not having a good time.

当我们建立Modular时，我们并没有意图构建一种新的编程语言。但是当我们构建统一的ML/AI基础平台时，我们意识到编程使用的全部技术栈是太复杂的，因此，在我们写了大量的MLIR之后并没有感觉很好。

.. note::
    MLIR 即Multi-Level Intermediate Representation， 目的是做一个通用、可复用的编译器框架, 目前主要用于机器学习领域

What we wanted was an innovative and scalable programming model that could target accelerators and other heterogeneous systems that are pervasive in the AI field. This meant a programming language with powerful compile-time metaprogramming, integration of adaptive compilation techniques, caching throughout the compilation flow, and other features that are not supported by existing languages.

我们想要一个创新且可拓展的编程模型，目标在于针对AI领域中的加速器和其他异构系统，那就意味着是一种在编译期间就很强大的元编程语言，集成自适应的编译技术，缓存整个编译流程，和其他开发语言不存在的其他功能

And although accelerators are important, one of the most prevalent and sometimes overlooked “accelerators” is the host CPU. Nowadays, CPUs have lots of tensor-core-like accelerator blocks and other AI acceleration units, but they also serve as the “fallback” for operations that specialized accelerators don’t handle, such as data loading, pre- and post-processing, and integrations with foreign systems. So it was clear that we couldn’t lift AI with just an “accelerator language” that worked with only specific processors.

尽管加速器是重要的，最普遍但是有时被忽略的加速器是主机CPU。如今，大多数CPU都具有类似tensor-core的加速块和其他的加速单元。它们会在指定加速器无法处理时作为"后备的"加速器。例如数据加载、预处理和后期处理，和外部系统的集成。很显然无法仅使用一种特定处理器加速语言来提升AI

Applied AI systems need to address all these issues, and we decided there was no reason it couldn’t be done with just one language. Thus, Mojo was born.

应用AI系统需要解决所有这些问题，和我们没理由认为仅靠一种编程语言解决这些问题，于是，Mojo诞生了


.. rubric:: 下一代编译技术语言

When we realized that no existing language could solve the challenges in AI compute, we embarked on a first-principles rethinking of how a programming language should be designed and implemented to solve our problems. Because we require high-performance support for a wide variety of accelerators, traditional compiler technologies like LLVM and GCC were not suitable (and any languages and tools based on them would not suffice). Although they support a wide range of CPUs and some commonly used GPUs, these compiler technologies were designed decades ago and are unable to fully support modern chip architectures. Nowadays, the standard technology for specialized machine learning accelerators is MLIR.

当我们意识到根本不存在语言能解决在AI计算领域的挑战，我开始基于第一原则重新思考程序语言是怎样被设计和实施去解决我们的问题。因为我们要求有各种各样的加速器提供高性能，传统LLVM和GCC编译器已经不在适合了(任何基于他们开发的语言和工具都是不足以胜任的)。即时他们支持各种CPUS和一些常用的GPU，这些编译器在数十年前被设计，并不能完全支持现代芯片架构。如今，专门机器学习加速器的标准编译技术是MLIR。

.. note::
    LLVM 即Low Level Virtual Machine， 以C++编写而成

    GCC 即GNU Compiler Collection， 是由GNU开发的编程语言编译器