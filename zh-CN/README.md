# spx

`spx`是`goplus`支持的2D下`STEM education`教育的游戏引擎

`spx`通过工程目录下的`index.gmx`作为整个游戏的入口文件，里面有一个run方法，为整个游戏的入口开始。

## 代码结构

代码组织结构一般为：一个`index.gmx`，若干个`spx`文件，以及一个按照规定的`resources`目录

所有的这些内容构成一个`Game`对象，作为游戏的运行时环境

## index.gmx文件

`index.gmx`是整个工程的入口文件，`run`是这个工程的入口函数。

`run`带两个参数，第一个是`resource`的目录名称或者互联网上的资源文件，第二个是配置，支持的配置为：

```go
Title              string
Scale              float64
FullScreen         bool
DontRunOnUnfocused bool
DontParseFlags     bool
```

`run`的示例：

```spx
run "hzip://open.qiniu.us/weather/res.zip", {Title: "Weather (by Go+)"}
```

## resources目录

`resources`目录结构，通常为如下的目录格式:

- sounds
- sprites
- index.json


### index.json的格式说明

`index.json`文件的格式为：

```json
{
  "costumes": [
    {
      "bitmapResolution": 2,
      "name": "backdrop1",
      "path": "38.png",
      "x": 480,
      "y": 360
    }
  ],
  "currentCostumeIndex": 0,
  "zorder": [
    "Backdrop",
    "YouWin",
    "Bomb",
    "TextIntro",
    "GameLogo",
    "GameStart",
    {
      "color": 15629590,
      "isDiscrete": true,
      "label": "bombs",
      "mode": 1,
      "sliderMax": 100,
      "sliderMin": 0,
      "target": "",
      "type": "stageMonitor",
      "val": "getVar:bombs",
      "visible": true,
      "x": 2,
      "y": 337
    },
    {
      "color": 15629590,
      "isDiscrete": true,
      "label": "score",
      "mode": 1,
      "sliderMax": 100,
      "sliderMin": 0,
      "target": "",
      "type": "stageMonitor",
      "val": "getVar:score",
      "visible": true,
      "x": 7,
      "y": 0
    },
    "MyAircraft",
    "MiddleEnemy",
    "HugeEnemy",
    "Bullet",
    "SmallEnemy",
    "GameOver"
  ]
}
```

`costume`（造型）对象:

- name：名称，string
- path：图像路径，string
- bitmapResolution： 图像分辨率，图像会用这个缩放，>1表示缩小, <1表示放大
- x，y：表示图片中心点位置


`currentCostumeIndex`: 多个`costume`时的索引，从0开始计数

`zorder`表示游戏中的对象（称为`Shape`)，`Shape`有两种，一种是`Sprite`（精灵），另一种是`stageMonitor`（通过json对象来定义）

一个精灵（sprite）有多个造型（costume），通过切换造型实习动态效果，比如走路，比如飞机被打爆。


## 支持的类型

主要分下面几种

1. 内置简单类型，如int,float32,int64, bool等等
2. 全局的`Game`类型
3. `Shape`类型，又细分为：
   1. `Sprite`对象
   2. `stageMonitor`对象


### `Game`类型

- `Game`类型构建的对象，是整个运行的环境，提供全局的函数方法，见[全局方法](./global.md)

### `Sprite`类型

- `Sprite`类型的对象，是通过`.spx`的后缀名来定义，详情见[sprite](./sprite.md)

### `stageMonitor`类型

`stageMonitor`对象，定义示例：

```json
{
  "color": 15629590,
  "isDiscrete": true,
  "label": "score",
  "mode": 1,
  "sliderMax": 100,
  "sliderMin": 0,
  "target": "",
  "type": "stageMonitor",
  "val": "getVar:score",
  "visible": true,
  "x": 7,
  "y": 0
}
```

## 内置的对象

- Invalid
  - 无效的对象
- Last
  - 最后一个对象
- All
  - 所有对象
- Random
  - 随机对象
- Mouse
  - 鼠标对象
- Edge
  - 边缘对象



## 几个边缘方向

touchingScreenLeft
touchingScreenTop
touchingScreenRight
touchingScreenBottom
touchingAllEdges

## 游戏窗口

整个游戏的默认窗口大小是 xxxx,