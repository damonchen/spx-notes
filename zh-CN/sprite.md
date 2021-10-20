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
  - 转向某个对象, obj可以为方向，int，float64或者sprite
- turn(val) （2021-10修改）
  - 偏转, val可以为方向，或者int以及float64
  - val的方向
    - Left
    - Right
    - Up
    - Down
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


- touching(sprite, [animation])
- touching(sprite)
- touching(edge)
  - 触发一个触摸动作，支持在sprite上触发以及mouse和edge上触发
  - 增加了animation（为字符串数组），即`setAnimation`中指定的animation（2021-10）
- bounceOffEdge
  - 弹开边缘
- stamp


## 2021-10新增的接口

- setAnimation(name, ani)
  - 用来设置动画，用name来索引，ani是动画方法
  - ani原型为：func(*Sprite)，即接受一个sprite对象参数
- animate(name)
  - 调用setAnimation设置的动画
- animate(sec, costume, n)
- animate(sec, costume, n, step)
- animate(sec, costume, n, step, move)
  - 动画方法，sec为动画帧之间的间隔时间，n表示总共有几帧，step为帧的跳跃间隔，move为移动步伐，和方向相关
- cloned()
  - 判定sprite是否为cloned
- visible()
  - 判定sprite是否可视
- hideVar(name)
  - 隐藏name对应的sprite
- showVar(name)
  - 显示name对应的sprite

### 其他

- 在`sprite`的`index.json`的`costumeSet`增加了`nx`的参数，用来指示图片中`sprite`的间隔。

-  在`sprite`的`index.json`中增加了`costumeMPSet`对象，用来指示复杂图像下的sprite的图片获取方式

其中一个示例如下：

```
 "costumeMPSet": {
    "bitmapResolution": 1,
    "path": "../common.png",
    "parts": [
      {
        "rect": {
          "x": 895,
          "y": 2,
          "w": 215,
          "h": 46
        },
        "nx": 5
      },
      {
        "rect": {
          "x": 1110,
          "y": 2,
          "w": 120,
          "h": 46
        },
        "nx": 2
      },
      {
        "rect": {
          "x": 1070,
          "y": 2,
          "w": 42,
          "h": 46
        },
        "nx": 1
      }
    ]
  },
```

图片为：

![common](assets/common.png)

