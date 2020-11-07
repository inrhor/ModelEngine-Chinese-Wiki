# 配置

```text
# 关于游戏中的数据
Model-Engine:
  # 翻译能力有限
  # 但如果发现模型永远变黑或后台有相关报错，则设置为 -1 禁用此值
  Marker-Tick: 3
  # 设置为正值启用此值，每tick发送一个更新数据包
  # 值越低，发送更新数据包越多，虽然会导致模型不稳定，但能减轻任何旋转的错误
  # 注意，此选项不会修复客户端异步问题，但会减轻异步问题
  Force-Update-Tick: 5
  # 关于动画，对应导出的动画模型的状态的动画ID(这在制作模型动画过程中会了解到的)
  Animation:
    Idle: idle
    Walk: walk
    Fall: fall
    Land: land
    Death: death
  # 动画模式，翻译能力有限
  Animation-Mode: smooth

# 关于模型生成器
Model-Generator:
  # 是否在启动服务器时加载模型配置
  # 如果禁用，则请用 /me reload models 重载模型配置
  Generate-On-Start: true
  # 是否输出有关模型配置的加载错误信息
  Enable-Error: true
  # 是否允许加载模型时覆盖原来的模型配置
  # 如果禁用，则在删除模型配置才能生成新的模型配置
  Overwrite: true
  # 材质资源包中的模型空间文件夹名称
  Namespace: modelengine

# 实验阶段，启用的话请注意风险
Experimental-Options:
  # 是否使用ProtocolLib数据包处理模型
  Use-ProtocolLib: false
  # 超精确模型，翻译能力有限
  Hyper-Accurate-Model: false
```

