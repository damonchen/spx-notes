# 支持的事件

- onStart
  - 开始
- onClick
  - 鼠标点击
- onCloned()
- onCloned(data)
  - 克隆对象后的回调，方便重新初始化对象
- onKey
- onKey(key)
  - 按键
- onMsg
- onMsg(msg, onMsg)
  - 响应消息
- onScene
- onScene(name)
  - 场景消息

## 2021-10增加的事件

- onMoving(func(MovingInfo))
- onMoveing(func())
  - 移动的事件
  - MovingInfo:
    - OldX
    - OldY
    - NewX
    - NewY
    - Obj 为移动的sprite对象