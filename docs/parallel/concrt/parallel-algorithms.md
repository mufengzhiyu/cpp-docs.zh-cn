---
title: "并行算法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cbabb499d67a2248ebaefa5cbc787afe2c6cfc08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="parallel-algorithms"></a>并行算法
并行模式库 (PPL) 提供了同时对集合的数据执行工作的算法。 这些算法类似于所提供的 c + + 标准库。  
  

 并行算法由并发运行时中的现有功能组成。 例如， [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for)算法使用[concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)对象来执行并行循环迭代。 `parallel_for`算法分区工作给定可用数量的计算资源以最佳方式。  

  
##  <a name="top"></a> 部分  
  
- [Parallel_for 算法](#parallel_for)  
  
- [Parallel_for_each 算法](#parallel_for_each)  
  
- [Parallel_invoke 算法](#parallel_invoke)  
  
- [Parallel_transform 和 parallel_reduce 算法](#parallel_transform_reduce)  
  
    - [Parallel_transform 算法](#parallel_transform)  
  
    - [Parallel_reduce 算法](#parallel_reduce)  
  
    - [示例： 执行映射和降低并行](#map_reduce_example)  
  
- [分区工作](#partitions)  
  
- [并行排序](#parallel_sorting)  
  
    - [选择排序算法](#choose_sort)  
  
##  <a name="parallel_for"></a>Parallel_for 算法  

 [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for)算法重复地以并行方式执行相同的任务。 其中每个任务是由迭代值参数化。 当必须不共享该循环迭代之间的资源的循环正文时，此算法很有用。  
  
 `parallel_for`算法对任务进行分区的并行执行以最佳方式。 当工作负载不平衡时，此算法还会使用工作窃取算法和范围窃取来平衡这些分区。 当某个循环迭代以协作方式停滞时，运行时重新分配到其他线程或多个处理器的当前线程分配的迭代的范围。 同样，当某个线程完成一个迭代范围，运行时重新分配给该线程从其他线程的工作。 `parallel_for`算法还支持*嵌套并行*。 当一个并行循环包含另一个并行循环时，运行时将协调之间循环体进行并行执行更高效地处理资源。  
  
 `parallel_for` 算法有多个重载版本。 第一个版本采用起始值、 结束值和工作函数 （lambda 表达式、 函数对象或函数指针）。 第二个版本依据采用起始值、 结束值、 值到步骤，并且工作函数。 此函数的第一个版本用作步长值 1。 其余版本采用分区程序对象，使您能够指定 `parallel_for` 如何在线程之间对范围进行分区。 部分中的更详细地介绍了分区程序[分区工作](#partitions)本文档中。  
  
 你可以将许多转换`for`循环，以使用`parallel_for`。 但是，`parallel_for`算法不同于`for`语句通过以下方式：  
  
-   `parallel_for`算法`parallel_for`不在预先确定的顺序执行这些任务。  
  
-   `parallel_for`算法不支持任意终止条件。 `parallel_for`算法会停止时的迭代变量的当前值是一个小于`last`。  
  
-   `_Index_type`类型参数必须是整数类型。 此整型可以签名或未签名。  
  
-   循环迭代必须转发。 `parallel_for`算法引发类型的异常[std::invalid_argument](../../standard-library/invalid-argument-class.md)如果`_Step`参数是小于 1。  
  
-   异常处理机制`parallel_for`算法不同于`for`循环。 如果多个异常会同时出现在并行循环正文，运行时将传播到调用的线程异常之一`parallel_for`。 此外，当某个循环迭代抛出异常，运行时不会立即停止总体循环。 相反，循环处于取消状态，运行时将放弃任何尚未启动的任务。 有关异常处理和并行算法的详细信息，请参阅[异常处理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)。  
  
 尽管`parallel_for`算法不支持任意终止条件，你可以使用取消来停止所有任务。 有关取消的详细信息，请参阅[PPL 中的取消](cancellation-in-the-ppl.md)。  
  
> [!NOTE]
>  从负载平衡和功能，如取消支持的结果可能不克服并行执行循环体的好处的计划成本，尤其当循环体时相对较小。 您可以在并行循环中使用分区程序来尽量减少此开销。 有关详细信息，请参阅[分区工作](#partitions)本文档后面部分。  
  
### <a name="example"></a>示例  
 下面的示例演示的基本结构`parallel_for`算法。 此示例向控制台输出并行 [1，5] 范围内的每个值。  
  
 [!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]  
  
 该示例产生下面的示例输出：  
  
```Output  
1 2 4 3 5  
```  
  
 因为`parallel_for`算法作用并行每个项，在其中值打印到控制台的顺序将会不同。  
  
 有关完整示例，使用`parallel_for`算法，请参阅[如何： 编写 parallel_for 循环](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)。  
  
 [[返回页首](#top)]  
  
##  <a name="parallel_for_each"></a>Parallel_for_each 算法  

 [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)算法对迭代容器，如提供的 c + + 标准库，并行执行任务。 它使用相同的分区逻辑，`parallel_for`算法使用。  
  
 `parallel_for_each`算法类似于 c + + 标准库[for_each](../../standard-library/algorithm-functions.md#for_each)算法，只不过`parallel_for_each`算法并发执行的任务。 像其他并行算法，`parallel_for_each`不会按特定顺序执行这些任务。  
  
 尽管`parallel_for_each`算法适用于向前迭代器和随机访问迭代器，它将与随机访问迭代器更好地执行。  
  
### <a name="example"></a>示例  
 下面的示例演示的基本结构`parallel_for_each`算法。 此示例将打印到控制台中的每个值[std:: array](../../standard-library/array-class-stl.md)并行的对象。  
  
 [!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]  
  
 该示例产生下面的示例输出：  
  
```Output  
4 5 1 2 3  
```  
  
 因为`parallel_for_each`算法作用并行每个项，在其中值打印到控制台的顺序将会不同。  
  
 有关完整示例，使用`parallel_for_each`算法，请参阅[如何： 编写 parallel_for_each 循环](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)。  
  
 [[返回页首](#top)]  
  
##  <a name="parallel_invoke"></a>Parallel_invoke 算法  

 [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)算法以并行方式执行一组任务。 它不返回每个任务完成之前。 当你具有你想要在同一时间执行的多个独立任务时，此算法很有用。  
  
 `parallel_invoke`算法使用作为其参数的工作函数 （lambda 函数、 函数对象或函数指针） 的一系列。 `parallel_invoke`算法被重载以采用两个到十个参数之间。 传递给每个函数`parallel_invoke`必须采用零个参数。  
  
 像其他并行算法，`parallel_invoke`不会按特定顺序执行这些任务。 主题[任务并行](../../parallel/concrt/task-parallelism-concurrency-runtime.md)说明如何`parallel_invoke`算法与任务和任务组。  
  
### <a name="example"></a>示例  
 下面的示例演示的基本结构`parallel_invoke`算法。 此示例同时调用`twice`上三个本地变量的函数，并输出到控制台的结果。  
  
 [!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]  
  
 该示例产生下面的输出：  
  
```Output  
108 11.2 HelloHello  
```  
  
 有关完整示例，请使用`parallel_invoke`算法，请参阅[如何： 使用 parallel_invoke 来编写并行排序例程](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)和[如何： 使用 parallel_invoke 来执行并行操作](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)。  
  
 [[返回页首](#top)]  
  
##  <a name="parallel_transform_reduce"></a>Parallel_transform 和 parallel_reduce 算法  

 [Concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)和[concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)算法是 c + + 标准库算法的并行版本[std:: transform](../../standard-library/algorithm-functions.md#transform)和[std:: accumulate](../../standard-library/numeric-functions.md#accumulate)分别。 并发运行时版本的行为方式类似的 c + + 标准库版本，只不过操作顺序不确定，因为它们并行执行。 当您使用的集足够大，可从并行处理中获得性能和可扩展性优势时，请使用这些算法。  
  
> [!IMPORTANT]
>  因为这些迭代器会生成稳定的内存地址，所以 `parallel_transform` 算法和 `parallel_reduce` 算法仅支持随机访问、双向和向前迭代器。 而且这些迭代器必须生成非 `const` 左值。  
  
###  <a name="parallel_transform"></a>Parallel_transform 算法  
 您可以使用 `parallel transform` 算法执行许多数据并行化操作。 例如，你可以：  
  
-   调整图像的亮度，并执行其他图像处理操作。  
  
-   在两个向量之间求和或取点积，并对向量执行其他数值计算。  
  
-   执行三维射线跟踪，其中每次迭代引用一个必须呈现的像素。  
  
 下面的示例显示用于调用 `parallel_transform` 算法的基本结构。 此示例对求反每个元素的 std::[向量](../../standard-library/vector-class.md)两种方式的对象。 第一种方法是使用 lambda 表达式。 第二种方式使用[std::negate](../../standard-library/negate-struct.md)，它派生自[std::unary_function](../../standard-library/unary-function-struct.md)。  
  
 [!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]  
  
> [!WARNING]
>  本示例演示 `parallel_transform` 的基本用法。 由于工作函数不会执行大量工作，因此本示例中不会有显著的性能提升。  
  
 `parallel_transform` 算法有两个重载。 第一个重载采用一个输入范围和一个一元函数。 该一元函数可以是采用一个参数的 lambda 表达式、一个函数对象或从 `unary_function` 派生的一个类型。 第二个重载采用两个输入范围和一个二元函数。 该二元函数可以是采用两个自变量、 函数对象或从派生的类型的 lambda 表达式[std:: binary_function](../../standard-library/binary-function-struct.md)。 下面的示例阐释了这些差异。  
  
 [!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]  
  
> [!IMPORTANT]
>  您为 `parallel_transform` 的输出提供的迭代器必须与输入迭代器完全重叠或根本不重叠。 如果输入迭代器和输出迭代器部分重叠，则此算法的行为是未指定的。  
  
###  <a name="parallel_reduce"></a>Parallel_reduce 算法  
 当您具有满足关联属性的操作序列时，`parallel_reduce` 算法很有用。 （此算法不要求可交换属性。）以下是可以使用 `parallel_reduce` 执行的一些操作：  
  
-   将矩阵的序列相乘以生成一个矩阵。  
  
-   用矩阵序列乘以一个向量来生成一个向量。  
  
-   计算字符串序列的长度。  
  
-   将一个元素列表（例如字符串）组合为一个元素。  
  
 下面的基本示例演示如何使用 `parallel_reduce` 算法将一个字符串序列组合为一个字符串。 与 `parallel_transform` 的示例一样，此基本示例中不会有性能提升。  
  
 [!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]  
  
 在许多情况下，你可以认为的`parallel_reduce`作为使用速记`parallel_for_each`一起使用的算法[concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md)类。  
  
###  <a name="map_reduce_example"></a>示例： 执行映射和降低并行  

 A*映射*操作将函数应用于序列中的每个值。 A*减少*操作将合并为一个值序列的元素。 你可以使用 c + + 标准库[std:: transform](../../standard-library/algorithm-functions.md#transform)和[std:: accumulate](../../standard-library/numeric-functions.md#accumulate)函数来执行映射和化简操作。 但是，对于许多问题，您可以使用 `parallel_transform` 算法并行执行映射操作，并使用 `parallel_reduce` 算法并行执行化简操作。  

  
 下面的示例将按串行方式计算质数和所需的时间与按并行方式计算质数和所需的时间进行比较。 映射阶段会将非质数值转换为 0，而化简阶段将对这些值求和。  
  
 [!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]  
  
 有关执行映射和化简并行操作的另一个示例，请参阅[如何： 执行映射和减少操作并行](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)。  
  
 [[返回页首](#top)]  
  
##  <a name="partitions"></a>分区工作  
 若要并行化的数据源上的操作，一个必要步骤，是到*分区*到可由多个线程同时访问的多个部分的源。 分区程序将指定并行算法应如何在线程之间对范围进行分区。 如本文档前面所述，PPL 使用的是默认分区机制，该默认分区机制创建初始工作负荷并在工作负荷不平衡时使用工作窃取算法和范围窃取来平衡这些分区。 例如，当某个循环迭代完成一个迭代范围时，运行时会将其他线程的工作重新分配给该线程。 但是，在某些方案中，你可能希望指定另一个更适用于你的问题的分区机制。  
  
 `parallel_for`、`parallel_for_each` 和 `parallel_transform` 算法提供采用一个附加参数 `_Partitioner` 的重载版本。 此参数定义了用于划分工作的分区程序类型。 以下是 PPL 定义的分区程序种类：  
  
 [concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)  
 将工作划分为一个固定数量的范围（通常是可用于在循环中工作的辅助线程的数量）。 此分区程序类型与 `static_partitioner` 类似，但通过将范围映射到辅助线程的方式改善了缓存的关联。 当在相同数据集中多次执行一个循环（例如一个循环内的循环）且数据适合缓存时，此分区程序类型可提高性能。 此分区程序不完全参与取消。 它也不使用协作停滞语义，因此不能与具有前向依赖关系的并行循环一起使用。  
  
 [concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)  
 将工作划分为一个初始数量的范围（通常是可用于在循环中工作的辅助线程的数量）。 当您不调用采用 `_Partitioner` 参数的重载的并行算法时，运行时默认使用此类型。 每个范围可以划分为子范围，从而实现负载平衡。 当一个工作范围完成时，运行时会将其他线程工作的子范围重新分配给该线程。 如果您的工作负荷不在另外一个类别下或者您需要完全支持取消或协作停滞，请使用该分区程序。  
  
 [concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)  
 将工作划分到范围中，使每个范围至少拥有给定区块大小所指定的迭代的数目。 此分区程序类型加入了负载平衡；然而，运行时未将范围划分为子范围。 对于每个辅助，运行时将在 `_Chunk_size` 迭代完成后检查取消情况并执行负载平衡。  
  
 [concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)  
 将工作划分为一个固定数量的范围（通常是可用于在循环中工作的辅助线程的数量）。 此分区程序类型可以提高性能，因为它不使用工作窃取，开销较小。 当一个并行循环的每次迭代执行固定和统一数量的工作而且您不需要支持取消或前向协作停滞时，请使用此分区程序类型。  
  
> [!WARNING]
>  `parallel_for_each`和`parallel_transform`算法都支持使用随机访问迭代器的容器 (如 std::[向量](../../standard-library/vector-class.md)) 为静态、 简单和关联分区程序。 采用双向和向前迭代器的容器的使用会导致编译时错误。 默认分区程序 `auto_partitioner` 支持所有这三种迭代器类型。  
  
 通常，除 `affinity_partitioner` 外，这些分区程序的使用方式相同。 大多数分区程序类型不会维持状态，而且不会由运行时进行修改。 因此，如下例所示，您可以在调用站点创建这些分区程序对象。  
  
 [!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]  
  
 但是，必须将 `affinity_partitioner` 对象作为非 `const` 左值引用传递，以便算法可以存储状态，以供未来循环重用。 下面的示例演示对数据集多次并行执行相同操作的基本应用程序。 因为数组有可能适合缓存，使用 `affinity_partitioner` 可以提高性能。  
  
 [!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]  
  
> [!CAUTION]
>  在修改依赖于协作停滞语义的现有代码以使用 `static_partitioner` 或 `affinity_partitioner` 时应谨慎。 这些分区程序类型不使用负载平衡或范围窃取，因此可能会更改应用程序的行为。  
  
 确定在任何给定方案中是否使用分区程序的最佳方式是：体验并度量操作在有代表性的负载和计算机配置下要花多长时间完成。 例如，静态分区可能会有仅几个核心的多核计算机上的明显加快，但它可能会导致具有相对较多的内核的计算机上的系统速度变慢。  
  
 [[返回页首](#top)]  
  
##  <a name="parallel_sorting"></a>并行排序  

 PPL 提供三种排序算法： [concurrency:: parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort)， [concurrency:: parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)，和[concurrency:: parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)。 当您具有可受益于并行排序的数据集时，这些排序算法很有用。 具体而言，当您具有大型数据集时或使用需要消耗大量计算资源的比较操作对数据进行排序时，并行排序很有用。 每种算法都会就地对元素排序。  

  
 `parallel_sort` 和 `parallel_buffered_sort` 算法都是基于比较的算法。 即，它们按值来比较元素。 `parallel_sort` 算法没有其他内存要求，适用于通用排序。 `parallel_buffered_sort`算法可以执行更好`parallel_sort`，但需要 o （n） 空间。  
  
 `parallel_radixsort` 算法是基于哈希的。 即，它使用整数键来对元素排序。 通过使用键，此算法可以直接计算元素的目标，而不是使用比较。 如`parallel_buffered_sort`，此算法需要 o （n） 空间。  
  
 下表总结了三种并行排序算法的重要属性。  
  
|算法|描述|排序机制|排序稳定性|内存要求|时间复杂性|迭代器访问|  
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|  
|`parallel_sort`|通用的基于比较的排序。|基于比较（升序）|不稳定|无|O((N/P)log(N/P) + 2N((P-1)/P))|随机|  
|`parallel_buffered_sort`|需要 O(N) 空间，基于比较的更快的通用排序。|基于比较（升序）|不稳定|需要额外的 o （n） 空间|O((N/P)log(N))|随机|  
|`parallel_radixsort`|需要 O(N) 空间，基于整数键的排序。|基于哈希|稳定版|需要额外的 o （n） 空间|O(N/P)|随机|  
  
 下图用图形更形象地说明了三种并行排序算法的重要属性。  
  
 ![排序算法比较](../../parallel/concrt/media/concrt_parallel_sorting.png "concrt_parallel_sorting")  
  
 这些并行排序算法遵循取消和异常处理的规则。 有关取消和异常处理并发运行时中的详细信息，请参阅[取消并行算法](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms)和[异常处理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)。  
  
> [!TIP]
>  这些并行排序算法支持移动语义。 可以定义一个移动赋值运算符，以使交换操作的出现更有效。 有关移动语义和移动赋值运算符的详细信息，请参阅[右值引用声明符： & &](../../cpp/rvalue-reference-declarator-amp-amp.md)，和[移动构造函数和移动赋值运算符 （c + +）](../../cpp/move-constructors-and-move-assignment-operators-cpp.md)。 如果您不提供移动赋值运算符或交换函数，排序算法将使用复制构造函数。  
  
 下面的基本示例演示如何使用 `parallel_sort` 对 `vector` 值的 `int` 进行排序。 默认情况下，`parallel_sort`使用[std:: less](../../standard-library/less-struct.md)值进行比较。  
  
 [!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]  
  
 此示例演示如何提供自定义比较函数。 它使用[std::complex::real](../../standard-library/complex-class.md#real)方法进行排序[std:: complex\<double >](../../standard-library/complex-double.md)升序排序的值。  
  
 [!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]  
  
 此示例演示如何为 `parallel_radixsort` 算法提供哈希函数。 此示例对三维点排序。 根据这些点与参考点的距离对它们进行排序。  
  
 [!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]  
  
 为了便于演示，本示例使用相对较小的数据集。 您可以增大向量的初始范围，体验较大数据集中性能的提升。  
  
 此示例使用 lambda 表达式作为哈希函数。 你还可以使用的一个内置实现的 std::[哈希类](../../standard-library/hash-class.md)或定义自己的专用化。 如本示例所示，您还可以使用自定义哈希函数对象：  
  
 [!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]  
  
 [!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]  
  
 哈希函数必须返回整型 ([std::is_integral::value](../../standard-library/is-integral-class.md)必须`true`)。 此整型必须可转换为类型 `size_t`。  
  
###  <a name="choose_sort"></a>选择排序算法  
 在许多情况下，`parallel_sort` 会提供速度和内存性能的最佳平衡。 但是，当您增加数据集的大小、可用处理器的数量或比较函数的复杂性时，`parallel_buffered_sort` 或 `parallel_radixsort` 性能更佳。 确定在任何给定方案中使用哪种排序算法的最佳方式是：体验并度量在有代表性计算机配置下对典型数据排序需要多长时间。 在选择排序策略时请遵循以下准则。  
  
-   数据集的大小。 在此文档中，*小*数据集包含的元素少于 1000，*中等*数据集包含 10,000 和 100,000 个之间元素之间和*大型*数据集包含元素多于 100,000 个。  
  
-   您的比较函数或哈希函数所执行的工作量。  
  
-   可用计算资源的量。  
  
-   数据集的特征。 例如，一种算法对已完成近似排序的数据可能执行效果很好，但对完全未排序的数据执行效果就不那么好了。  
  
-   区块的大小。 可选的 `_Chunk_size` 参数将指定算法在将整体排序细分成较小工作单元时何时从并行排序实现切换为串行排序实现。 例如，如果提供的是 512，算法会在工作单元包含 512 个或更少元素时切换到串行实现。 串行实现可以提高整体性能，因为它消除了并行处理数据所需的开销。  
  
 以并行方式对小型数据集排序可能不值得，即使是在您拥有大量的可用计算资源或您的比较函数或哈希函数执行相对大量的工作时。 你可以使用[std:: sort](../../standard-library/algorithm-functions.md#sort)函数对小型数据集进行排序。 (`parallel_sort`和`parallel_buffered_sort`调用`sort`时指定的区块大小大于数据集; 但是，`parallel_buffered_sort`将必须分配 o （n） 空间，这可能需要额外由于锁争用或内存分配的时间。)  
  
 如果您必须节省内存或您的内存分配器容易出现锁争用问题，请使用 `parallel_sort` 对中型数据集排序。 `parallel_sort`不需要额外的空间;其他算法需要 o （n） 空间。  
  
 使用`parallel_buffered_sort`中型数据集和你的应用程序时满足要求的其他 o （n） 空间进行排序。 当您拥有大量的计算资源或高开销的比较函数或哈希函数时，`parallel_buffered_sort` 尤其有用。  
  
 使用`parallel_radixsort`大型数据集和你的应用程序时满足要求的其他 o （n） 空间进行排序。 当等效的比较操作开销较大或两种操作开销都很大时，`parallel_radixsort` 尤其有用。  
  
> [!CAUTION]
>  好的哈希函数的实现要求您知道数据集范围以及数据集中的每个元素如何转换为对应的无符号值。 由于哈希操作会处理无符号值，如果无法生成无符号哈希值，请考虑使用另外的排序策略。  
  
 下面的示例针对相同大小的随机数据集对 `sort`、`parallel_sort`、`parallel_buffered_sort` 和 `parallel_radixsort` 的性能进行比较。  
  
 [!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]  
  
 在此示例中，假定它是可接受排序时分配 o （n） 空间，`parallel_radixsort`在此计算机配置此数据集执行效果最佳。  
  
 [[返回页首](#top)]  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[如何：编写 parallel_for 循环](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|演示如何使用`parallel_for`算法执行矩阵乘法。|  
|[如何：编写 parallel_for_each 循环](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|演示如何使用`parallel_for_each`算法来计算内的质数的计数[std:: array](../../standard-library/array-class-stl.md)并行的对象。|  
|[如何：使用 parallel_invoke 来编写并行排序例程](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|演示如何使用 `parallel_invoke` 算法提高双调排序算法的性能。|  
|[如何：使用 parallel_invoke 来执行并行操作](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|演示如何使用 `parallel_invoke` 算法提高对共享数据源执行多项操作的程序的性能。|  
|[如何：并行执行映射和减少操作](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|演示如何使用 `parallel_transform` 和 `parallel_reduce` 算法执行用于计算文件中单词出现次数的映射和化简操作。|  
|[并行模式库 (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|介绍 PPL，它提供命令式编程模型。|  
|[PPL 中的取消操作](cancellation-in-the-ppl.md)|说明 PPL、 如何取消并行工作以及如何确定取消任务组的时间中的取消操作的角色。|  
|[异常处理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|说明中并发运行时的异常处理的角色。|  
  
## <a name="reference"></a>参考  

 [parallel_for 函数](reference/concurrency-namespace-functions.md#parallel_for)
  
 [parallel_for_each 函数](reference/concurrency-namespace-functions.md#parallel_for_each)  
  
 [parallel_invoke 函数](reference/concurrency-namespace-functions.md#parallel_invoke)  

  
 [affinity_partitioner 类](../../parallel/concrt/reference/affinity-partitioner-class.md)  
  
 [auto_partitioner 类](../../parallel/concrt/reference/auto-partitioner-class.md)  
  
 [simple_partitioner 类](../../parallel/concrt/reference/simple-partitioner-class.md)  
  
 [static_partitioner 类](../../parallel/concrt/reference/static-partitioner-class.md)  
  

 [parallel_sort 函数](reference/concurrency-namespace-functions.md#parallel_sort)  
  
 [parallel_buffered_sort 函数](reference/concurrency-namespace-functions.md#parallel_buffered_sort)  
  
 [parallel_radixsort 函数](reference/concurrency-namespace-functions.md#parallel_radixsort)


