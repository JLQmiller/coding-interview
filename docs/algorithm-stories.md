# 《枕边算法书》

> 这里仅挑一些有意思的故事或知识点做个记录。

- [“红色眼睛与褐色眼睛”谜题](#红色眼睛与褐色眼睛谜题)

## “红色眼睛与褐色眼睛”谜题
从前，有个小岛上只住着和尚。有些和尚的眼睛是红色的，而另一些则是褐色的。红色眼睛的和尚受到诅咒，如果得知自己的眼睛是红色的，那么当晚 12 点必须自行了断，无一例外。

和尚间有一条不成文的规定，就是彼此不能提起对方眼睛的颜色。小岛上没有一面镜子，也没有可以反射自己容貌的物体。因此，没有任何人能够得知自己眼睛的颜色。出于这些原因，每个和尚都过着幸福的日子。

有一天，岛上突然来了一位游客，她完全处于状况外。于是，她对和尚们说：“你们当中至少有一位的眼睛是红色的”。

这名无心的游客当天就离开了小岛，而和尚们却因第一次听到有关眼睛颜色的话题而惴惴不安。当晚，小岛上开始出现了可怕的事情......

究竟是什么事呢？

这道题不简单却非常有意思，而一旦知道答案，又会觉得并不太难。这并非是那种荒谬的问题，要想解开需要一些逻辑推理，所以不要试图一下子解开。先花 2 分钟时间独立思考一下吧。

下面开始查看正确答案。

游客说，“至少有一个人”的眼睛是红色的。假如这岛上**没有任何一个和尚的眼睛是红色的**，那么这会导致最糟糕的结果。你想一想，对于和尚们来说，除了自己以外，看到的其它和尚的眼睛都是褐色的。因此，每个和尚都会认为自己的眼睛是红色的，可想而知，所有和尚当晚都会自杀。

如果**只有一名和尚的眼睛是红色的**，会出现什么结果呢？很简单，这名和尚知道其它和尚眼睛都是褐色的，那么就会判断出自己眼睛的颜色，进而选择自杀。游客的无心之言就这样夺走了一条生命。

考虑稍微复杂点的情况。假如**有两个红眼和尚**，那么他们各自都知道有一个红眼和尚，都以为说的是对方。这两个和尚心想：“那个红眼的家伙今晚就要自杀喽。”当晚，各自都安心入睡了。第二天，这两个和尚相互碰面，并看到对方没有自杀时，心理备受打击。他们都会意识到，红眼和尚有两个而非一个，而另一个正是自己。除此之外的任何情况都不可能让对方在第一个晚上不自杀而安然入睡。因此，受到极大打击的这两个红眼和尚在第二天晚上**都会悲惨死去**。

再考虑更复杂的情况。如果有 3 个红眼和尚，又会是怎样呢？平时，这 3 位会看到两个红眼和尚，所以听到游客的话后，都不会选择自杀。第一晚过后，他们又会想，另外两个和尚在第二天晚上都会自杀（就是前面探讨的“有两个红眼和尚”的情形）。到了第三天早上，看到本以为会自杀的另两个和尚并没有自杀时，根本没想到自己也是红眼和尚的这 3 人会同时受到极大的打击。因为，两个红眼和尚第二天晚上也没有自杀，这表明还有一个红眼和尚，而这第三个红眼和尚正是自己。

这种逻辑会反复循环。因此，该题的答案是“若小岛上共有 n 个红眼和尚，那么第 n 个晚上这些和尚会同时自杀”。离入，小当时共有 5 个红眼和尚，那么第 5 个晚上，这 5 个红眼和尚会同时自杀。

这道题其实可以利用递归的方法。假设红眼和尚人数 N 为 10，那么我们可以适用 N 为 9 的逻辑。同理，N 为 8 或 7 时，都适用 `N-1` 时的逻辑。将 `N=1`，即“只有一个红眼和尚”视为终止条件，即可得出最终结果。这种过程与计算机算法中函数的递归调用过程完全相同或给。