# gacha-expectation<br>

本程序旨在为抽卡玩家对抽卡预期和预计资源提供信息<br>

version1.1
---
Update: 更改了程序结构，在原有内容的基础上增加了对界限触发可变概率保底和固定概率有保底的抽卡模型的支持<br>
现在在主体程序结束运行后（即是否继续后选择n后）可以在IDE内输入
```
step(p,p_up,thres,most,mg).smlt(n,e,times)
```
>p为最高稀有度角色出率<br>
>p_up为up角色占最高稀有度角色出率的比例<br>
>thres为触发保底机制的抽数下限<br>
>most为必出抽数<br>
>>也可输入触发保底机制后每次递增的概率<br>
>
>mg为是否有大保底（原神限定池机制）
>n为总抽数<br>
>e为目标up数<br>
>times为模拟次数<br>

以及
```
bound(p,p_up,most).prob(n)
```
>p为最高稀有度角色出率<br>
>p_up为up角色出率<br>
>most为硬保底抽数<br>
>n为总抽数<br>

结果返回达到目标up数的频率（保留四位小数）<br>


version1.0
---
`gacha.py`程序主体运行为原神抽卡计算器，通过大样本频率趋近于概率的方式进行相应概率计算<br>

源码内还包括明日方舟单up和双up计算器，可在主体程序结束运行后在IDE命令行内输入
```
lottery_mrfz(n,up,times=100000)
```
>n为预计抽数<br>
>up为单池内up数量（1或2）<br>
>times为模拟次数（可不输入，取Default=100000）<br>

未来更新预计为更多抽卡概率模型（可变概率，固定概率有保底/无保底，收藏品兑换……）提供支持，并提供自定义抽卡概率模型结果测算
