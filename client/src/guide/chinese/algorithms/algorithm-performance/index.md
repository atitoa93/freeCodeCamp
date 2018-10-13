---
title: Algorithm Performance
localeTitle: 算法性能
---
在数学中，big-O表示法是用于描述和比较函数的_限制行为_的象征。  
函数的限制行为是函数的行为方式，因为它趋向于特定的值，而在大O符号中，它通常是趋向于无穷大。  
简而言之，big-O表示法用于描述函数的增长或下降，通常与另一个函数有关。

在算法设计中，我们通常使用big-O表示法，因为我们可以看到算法在最差模式下有多么糟糕或不好。但请记住，情况并非总是如此，因为最坏的情况可能是超级罕见的，在这种情况下我们计算平均情况。现在，以免欺骗大O符号。

在数学中，big-O表示法是用于描述和比较函数的_限制行为_的象征。

函数的限制行为是函数在趋向特定值时的行为方式，而在大O符号中，它通常随着趋势向无穷大趋势而变化。

简而言之，big-O表示法用于描述函数的增长或下降，通常与另一个函数有关。

注意：x ^ 2相当于x \* x或'x-squared'\]

例如，对于所有x> 1，我们说x = O（x ^ 2），换句话说，x ^ 2是x的上限，因此它增长得更快。  
对于所有x> _n，_ x = 0（x ^ 2）的权利要求的符号可以用x <= x ^ 2代替所有x> _n_ ，其中_n_是满足权利要求的最小数，在这种情况下为1。

实际上，我们说函数f（x）是O（g（x））比g（x）慢得多。

相比之下，在计算机科学和软件开发中，我们可以使用big-O表示法来描述算法通过其时间和空间复杂性的效率。

**空间**算法的**复杂性**是指其相对于输入大小的内存占用。

特别是当使用big-O表示法时，我们描述了算法相对于输入的效率： _n_ ，通常当_n_接近无穷大时。  
在检查算法时，我们通常希望降低时间和空间复杂度。 o（1）的时间复杂度表示恒定时间。

通过算法的比较和分析，我们能够创建更高效​​的应用程序。

对于算法性能，我们有两个主要因素：

*   **时间** ：我们需要知道为我们的数据运行算法需要多长时间以及它将如何根据数据大小（或在某些情况下其他因素，如数字位数等）增长。
    
*   **空间** ：我们的记忆是最终的，所以我们必须知道这个算法需要多少可用空间，以及我们需要能够跟踪其增长的时间。
    

以下3种符号主要用于表示算法的时间复杂度：

1.  **Θ表示法** ：theta表示法从上方和下方界定函数，因此它定义了确切的行为。我们可以说，当最坏情况和最佳情况相同时，我们有theta符号。
    
    > Θ（g（n））= {f（n）：存在正常数c1，c2和n0，使得0 <= c1 _g（n）<= f（n）<= c2_ g（n）对于所有n> = n0}
    
2.  **Big O表示法** ：Big O表示法定义算法的上限。例如，插入排序在最佳情况下采用线性时间，在最坏情况下采用二次时间。我们可以有把握地说插入排序的时间复杂度是_O_ （ _n ^ 2_ ）。
    
    > O（g（n））= {f（n）：存在正常数c和n0，使得对于所有n> = n0，0 <= f（n）<= cg（n）
    
3.  **Ω表示法** ：Ω表示法提供算法的下限。它显示了该算法最快的答案。 >Ω（g（n））= {f（n）：存在正常数c和n0，使得对于所有n> = n0}，0 <= cg（n）<= f（n）。
    

## 例子

例如，我们可以检查[\[冒泡排序\]](https://github.com/FreeCodeCamp/wiki/blob/master/Algorithms-Bubble-Sort.md#algorithm-bubble-sort)算法的时间复杂度，并使用big-O表示法表达它。

#### 冒泡排序：

```javascript
    // Function to implement bubble sort 
    void bubble_sort(int array<a href='http://bigocheatsheet.com/' target='_blank' rel='nofollow'>], int n) 
    { 
        // Here n is the number of elements in array 
        int temp; 
        for(int i = 0; i < n-1; i++) 
        { 
            // Last i elements are already in place 
            for(int j = 0; j < ni-1; j++) 
            { 
                if (array[j] > array[j+1]) 
                { 
                    // swap elements at index j and j+1 
                    temp = array[j]; 
                    array[j] = array[j+1]; 
                    array[j+1] = temp; 
                } 
            } 
        } 
    } 
```

看一下这段代码，我们可以看到，在数组已经排序的最佳情况下，程序只进行_n次_比较，因为不会发生交换。  
因此我们可以说冒泡排序的最佳案例时间复杂度是O（ _n_ ）。

检查阵列顺序相反的最坏情况，第一次迭代将进行_n次_比较，而下一次迭代必须进行_n_ - 1次比较，依此类推，直到只进行1次比较。  
因此，对于这种情况的大O符号是_n_ \* \[（ _n_ -1）/ 2\]，其中= 0.5 _n_ ^ 2 - 0.5 _n_ = O（ _n_ ^ 2），因为_n_ ^ 2项主导了函数，这使我们能够忽略函数中的其他术语。

我们可以使用\[这个方便的大O作弊表来确认这个分析，它具有许多常用数据结构和算法的大O时间复杂性

很明显，虽然对于小用例，这个时间复杂性可能没有问题，但是大规模的冒泡排序根本不是排序的好方法。  
这是big-O表示法的强大功能：它允许开发人员轻松查看其应用程序的潜在瓶颈，并采取措施使这些更具可伸缩性。

有关为什么big-O表示法和算法分析很重要的更多信息，请访问此[视频挑战](https://www.freecodecamp.com/videos/big-o-notation-what-it-is-and-why-you-should-care) ！