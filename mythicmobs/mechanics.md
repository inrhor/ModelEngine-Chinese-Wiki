# 技能机制

## 完整技能机制列表

请看：[https://github.com/Ticxo/Model-Engine-Wiki/blob/master/wiki/MythicMobs/MM\_Mechanics.png](https://github.com/Ticxo/Model-Engine-Wiki/blob/master/wiki/MythicMobs/MM_Mechanics.png)

## Model

这个 model 主要应用于MythicMobs生物技能

| 属性 | 别名 | 说明 | 默认 |
| :--- | :--- | :--- | :--- |
| modelid | m, mid, model | 该模型的ID |  |
| hitbox | h | 使用模型打击箱 | true |
| remove | r | If this mechanic removes a model. Provide modelid to specify which model should be removed（翻译能力有限） | false |
| killowner | ko | 删除模型时是否顺便删除使用过该模型的实体 | true |
| invisible | i, invis | If remove is false, this will not the set owner to invisible when applied. If remove is true and this is false, this will remove the invisibility of the owner when removing the model（翻译能力有限） | true |
| damagetint | d, tint | 受伤时是否显示红色 | true |
| nametag | n | 是否显示名称 | true |

例子：生物生成时应用该模型ID的模型，并且不显示名称

```text
- model{mid=kindletronjr;n=false} @self ~onSpawn
```

## State

为模型播放某个状态的动画，也可以删除指定状态

| 属性 | 别名 | 说明 | 默认 |
| :--- | :--- | :--- | :--- |
| modelid | m, mid, model | 该实体的模型ID |  |
| state | s | 状态 |  |
| remove | r | 移除哪一个状态 | false |
| startframe | f, frame | 动画的起始帧，单位为tick | 0 |
| lerpin | li | 过渡到新增状态的时长，单位为tick | 0 |
| lerpout | lo | 结束状态的过渡时长，单位为tick | 0 |
| ignorelerp | i | 当手动移除时，是否忽略淡出效果（lerpout） | false |

例子：将 attack 状态添加到指定模型ID中，并播放动画，and gives it 3 ticks to transition in and out of the animation.

```text
- state{mid=kindletronjr;s=attack;li=3;lo=3} @self ~onAttack
```

## ChangePart

改变模型的部件（请结合 [ModelPart](targeter.md) 目标选择器使用）

## SubMode

将子部件添加到目标子部件列表中，它可以是任何模型的部件

## Petrify

实体死亡，留下模型（可以想象为石化），允许指定其它模型ID

## Tint

设置整个模型或模型的一部分的颜色

## Enchant

附魔整个模型或模型的某一部分

## DefaultState

覆盖当前使用的默认状态



