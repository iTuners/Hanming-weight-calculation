# Hanming-weight-calculation
汉明重量求解
这段代码是一个经典的用于计算某个整数范围（从0到2^9 - 1）内每个数字1的二进制表示中连续1的数量（也称为汉明重量）的计数器。for循环结构有两层嵌套。

外层循环通过变量i遍历从0到255（因为 1<<9等于512，但数组下标是从0开始的），对于每个i值，它代表当前二进制表示中的位。

内层循环利用了一个技巧，j = i，然后j -= j & -j实际上是将j更新为其二进制表示中最右边的一个1的位置向左移一位后的差。这个操作会逐次减少j直到变成0，过程中cnt[i]++表示每当找到一个连续的1就增加相应位置的计数。

例如，如果i的二进制表示是 1010_0101（即177），那么j初始为177，执行j -= j & -j后得到99（移除了最右边的1），再继续递减直到0，这时cnt[177]就会加1，因为 1010_0101中有4个连续的1。
