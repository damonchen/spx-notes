# sprite（精灵）

`sprite`对象是整个游戏中的核心，通过事件来串联sprite之间的关系


## sprite支持的事件

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



## sprite支持的方法：

- hide()
  - 表示隐藏该对象
- show()
  - 表示显示该对象
- destroy()
  - 销毁对象
- clone()
  - 复制对象，对象会收到onCloned的事件


- costumeName()
  - 对象名称
- setCostumeName(name)
  - 设置对象的名称
- nextCostume()
  - 下一个costume

- say(msg, sec):
  - 会在屏幕上打印一句话，sec秒后消失
- think(msg, sec):
  - 同say

- setXYpos(x,y)
  - 表示设置对象在屏幕中的x，y坐标
- goto(obj):
  - 将对象和obj对象重叠
- setXpos(x)
  - 表示设置对象的x坐标
- setYpos(y)
  - 表示设置对象的y坐标
- changeXpos(dx)
  - 移动x坐标dx
- changeYpos(dy)
  - 移动y坐标dy
- xpos()
  - 表示读取对象的x坐标
- ypos()
  - 表示读取对象的y坐标
- distanceTo(obj)
  - 和另外一个对象的距离
- step(s)
  - 某个方向走step步
- glide(x, y, sec):
  - 在sec时间内，对象滑到x,y的位置
- size()
  - 表示对象的尺寸
- setSize(size)
  - 表示设置对象的尺寸
- changeSize(delta)
  - 修改对象的尺寸delta


- mouseX()
- mouseY()
  - 鼠标位置
- mousePressed
  - 鼠标按下
- keyPressed(key)
  - 按键按下

- turnTo(obj)
  - 转向某个对象
- turn(delta)
  - 偏转
- heading()
  - 头部的方向
- setRotationStyle(style)
  - 设置偏转的style，style值可以为：
    - 0：none
    - 1：normal
    - 2：left-right


- gotoFront
  - 向前一层
- goBackLayers
  - 向后一层

- penDown
- penUp
- setPenColor(color)
  - 设置pen颜色
- changePenColor(color)
  - 修改pen颜色
- setPenShade(shade)
- changePenShade(shade)
- setPenHue(hue)
- changePenHue(hue)
- setPenSize(size)
  - 设置pen的尺寸
- changePenSize(delta)
  - 修改pen的尺寸


- touching
  - 触发一个触摸动作，支持在sprite上触发以及mouse和edge上触发
- bounceOffEdge
  - 弹开边缘
- stamp

