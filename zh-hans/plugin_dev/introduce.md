插件简介
---

为了方便对插件的理解，本小节将会介绍插件的设计与工作原理

### 插件设计理念

「插件」**仅与Shell进行通信、交互**。


### 插件工作原理

为了方便理解，这里直接附上一张AntSword插件工作流程图（以调用 PortScan 插件为例）。

![][img_introduce_1]

详细说明：

1. 从上到下为时间顺序
2. 如果要调用的插件不需与用户交互，则可省去第4､5步，例如`phpinfo`插件
3. 第4步创建插件UI可根据插件作者喜好，随意发挥，推荐使用`dhtmlx`统一风格
4. 第7､8步为一次HTTP请求与结果展示，如果该插件需要多次请求，此处则可循环直到结束
5. 插件与核心框架通信，可以是调用发包模块向WebShell发送模版代码也可以是对Shell进行操作，例如`CopyShell`插件

[img_introduce_1]: http://7xtigg.com1.z0.glb.clouddn.com/doc/plugin_dev/introduce_1.png
