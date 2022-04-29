15.3-6

> 假定你希望兑换外汇，你意识到与其直接兑换，不如进行多种外币的一系列兑换，最后兑换到你想要的那种外币，可能会获得更大收益。假定你可以交易$$n$$种不同的货币，编号为$$1, 2, ..., n$$，兑换从$$1$$号货币开始，最终兑换为$$n$$号货币。对每两种货币$$i$$和$$j$$给定汇率$$r_{ij}$$，意味着你如果有$$d$$个单位的货币$$i$$，可以兑换$$dr_{ij}$$个单位的货币$$j$$。进行一系统的交易需要支付一定的拥金，金额取决于交易的次数。令$$c_k$$表示$$k$$次交易需要支付的佣金。证明：如果对所有$$k=1, 2, ..., n$$，$$c_k= 0$$，那么寻找最优兑换序列的问题具有最优子结构性质。然后请证明：如果佣金$$c_k$$为任意值，那么问题不一定具有最优子结构性质。

这个问题有点类似无权最短或最长路径，因为寻找从$$1$$号货币到$$n$$号货币的兑换序列$$s$$，可以简写成
$$
1 \xrightarrow{s} 6
$$
假如兑换序列中使用到$$x \in [1, 6]$$号货币，那么公式(1)可以写成
$$
1 \xrightarrow{s_1} x \xrightarrow{s_2} 6
$$
因此原问题的解，需要用到两个子问题的解。

1. 无佣金的情况，存在最优子结构的证明，如下

假如$$s$$是最优解的情况下，$$s_1$$不是最优解，那么存在$$s_1^{\text{'}}$$使得$$1 \rightarrow x$$的兑换收益更大，替换$$s_1$$后得到的新解比$$s$$的兑换收益更大，与假设矛盾；同理，也可以应用于$$s_2$$。总之，我们看到该情况下，原问题的最优解是由子问题的最优解构成的，因此具备最优子结构性质。

2. 有佣金的情况，不一定存在最优子结构的证明，如下

为了方便理解，我们需要对题目进行一定的更改。题目说，$$c_k$$为任意值，并且强调不一定具有最优子结构，显得不是很明确。但我们完全可以换种说法，即当兑换的次数大到一定程度后，会产生天价的佣金，使得收益变小甚至出现负收益。然后，我们再换一种说法，即兑换次数存在一个上限$$l$$，超过该上限，则兑换失败。

这样，基于1的证明，我们假设$$s_1$$的兑换序列需要$$m$$次兑换过程，而$$s_2$$的兑换序列需要$$n$$次兑换过程，此时存在以下关系
$$
m &<& l \\
n &<& l \\
m + n &<& 2l
$$
因此，如果想要保证$$m + n < l$$，就必须谨慎调整$$m$$和$$n$$，这样的结果就是，子问题之间是相关的，故而不是最优子结构性质。

- [ ] Finish the English solution

> Imagine that you wish to exchange one currency for another. You realize  that instead of directly exchanging one currency for another, you might be better off making a series of trades through other currencies, winding up with the currency you want. Suppose that you can trade $$n$$ different currencies, numbered $$1,2,…,n$$, where you start with currency $$1$$ and wish to wind up with currency $$n$$. You are given, for each pair of currencies $$i$$ and $$j$$ , an exchange rate $$r_{ij}$$, meaning that if you start with $$d$$ units of currency $$i$$ , you can trade for $$dr_{ij}$$ units of currency $$j$$. A sequence of trades may entail a commission, which depends on the number of trades you make. Let $$c_k$$ be the commission that you are charged when you make $$k$$ trades. Show that, if $$c_k = 0$$ for all $$k=1,2,…,n$$, then the problem of finding the best sequence of exchanges from currency $$1$$ to currency $$n$$ exhibits optimal substructure. Then show that if commissions $$c_k$$ are arbitrary values, then the problem of finding the best sequence of exchanges from currency $$1$$ to currency $$n$$ does not necessarily exhibit optimal substructure.