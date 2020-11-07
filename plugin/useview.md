# 示范配置

**BlockBench模型**：[https://pan.baidu.com/s/1oZhhQ9am2Pxc\_Vx6QhHlCA](https://pan.baidu.com/s/1oZhhQ9am2Pxc_Vx6QhHlCA) 提取码：ipq1

**Mob.yml**

```text
KindletronJR:
  Type: SILVERFISH
  Health: 20
  Damage: 0
  Skills:
  - model{mid=kindletronjr} @self ~onSpawn
  - skill{s=KindletronJRInit;sync=true} @self ~onAttack
  Options:
    Silent: true
    MovementSpeed: 0.1
    MaxCombatDistance: 25
    PreventOtherDrops: true
    PreventBlockInfection: true
```

Skill.yml

```text
KindletronJRInit:
  Skills:
  - CancelEvent
  - skill{s=KindletronJRPunch} @self

KindletronJRPunch:
  Cooldown: 1.05
  Skills:
  - state{s=attack;li=3;lo=2} @self
  - stun{d=25} @self
  - delay 25
  - totem{ch=1;onStart=KindletronJRPunchDamage;int=1;hR=3;md=1} @Forward{f=0.5}

KindletronJRPunchDamage:
  Skills:
  - damage{amount=3} @EntitiesNearOrigin{r=2}
```

