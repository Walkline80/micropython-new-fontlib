<h1 align="center">MicroPython New FontLib</h1>

<p align="center"><img src="https://img.shields.io/badge/Licence-MIT-green.svg?style=for-the-badge" /></p>

### 项目介绍

使用`MicroPython 开发板`读取自定义字库并显示

### 获取完整项目

因为项目中使用了子模块 [FontMaker Client](https://gitee.com/walkline/fontmaker-client.git) 的`binary`分支 和 [OLED Research](https://gitee.com/walkline/oled-research.git)，所以要获取完整项目代码需要如下操作

#### 克隆方式

```bash
$ git clone --recursive https://gitee.com/walkline/micropython-new-fontlib.git
```

#### 下载压缩文件方式

或者克隆时未使用`--recursive`参数的，使用如下代码更新子模块

```bash
$ cd micropython-new-fontlib
$ git submodule update --init --recursive
```

### 如何使用和测试

#### 生成字库文件

直接运行

```bash
$ client/youyuan_16.cmd
```

会生成一个`combined.bin`文件，字库文件信息如下

| 参数 | 数值 | 说明 |
| :-: | :-: | :-: |
| 字体 | 幼圆 |  |
| 字号 | 16 | 像素 |
| 字重 | 普通 | 不加粗、不斜体、无下划线 |
| 字符宽度 | 固定 |  |
| 宽度 | 16 | 像素 |
| 高度 | 16 | 像素 |
| 水平偏移 | 0 | 像素 |
| 垂直偏移 | 0 | 像素 |
| 扫描方式 | 垂直扫描 | |
| 字节顺序 | 低位在前 |  |

#### 使用电脑测试

直接运行

```bash
$ python fontlib.py
```

会显示相关信息，包括：

* 字库信息
* 获取的字模数据
* 字模打印预览

完整输出内容如下

```docs
HZK Info: .//client/combined.bin
    file size : 303520
  font height : 16
    data size : 32
    scan mode : Horizontal
   byte order : LSB
   characters : 8932

！: b'\x00\x00\x00\x00\x00\x00\x08\x00\x0c\x00\x08\x00\x08\x00\x08\x00\x08\x00\x08\x00\x08\x00\x08\x00\x00\x00\x08\x00\x08\x00\x00\x00'

☆: b'\x00\x00\x00\x00\x00\x80\x01\x80\x01\x80\x01@\x02@~? \x04\x10\x08\x0c\x10\x08\x10\x08\x90\x0bH\x148\x18\x08'

⒉: b'\x00\x00\x00\x00\x00\x00\x07\xc0\x08@\x00@\x00@\x00@\x00\x80\x01\x00\x01\x00\x02\x00\x04\x00\x0c\x08\x0f\xcc\x00\x00'

，: b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00p\x000\x00 \x00'

我: b'\x00\x00\x00@\x07PxH\x08D\x08D\x7f\xfe\x08D\x08D\t(\x0e0x0\x080\x08R\t\x8ax\x06'

ㄘ: b'\x00\x00\x00\x00\x00\x00\x01\x00\x01\x80\x00\x80\x01\x00\x03\xf0\x1d\x00\x01\x00\x02\xe0\x03`\x00@\x00\x80\x00\x00\x00\x00'

■: b'\x00\x00\x00\x00\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff\x7f\xff'

Ｂ: b'\x00\x00\x00\x00\x00\x00\x00\x00\x07\xf0\x060\x068\x060\x06p\x07\xf0\x06\x18\x06\x18\x06\x18\x07\xf0\x00\x00\x00\x00'

中: b'\x00\x00\x01\x00\x01\x00\x01\x00?\xfc!\x04!\x04!\x04!\x04!\x04!\x04?\xfc\x01\x00\x01\x00\x01\x00\x01\x00'

爱: b'\x00\x00\x00\x00?\xf8\x11\x10\t\x10?\xfcD\x02B\x02\x1f\xf8\x04\x00\x07\xf8\x0e\x08\x13\x10 \xe0\x01\xe0\x1e\x1e'

β: b'\x00\x00\x00\x00\x00\x00\x01\xe0\x01\x10\x030\x02 \x02\xc0\x02`\x06 \x04 \x04`\x04`\x07\xc0\x0c\x00\x08\x00'

あ: b"\x00\x00\x00\x00\x03\x00\x03\x00\x02\xc0\x1f\x80\x02\x00\x06\x80\x07\xf0\x0c\x98\x15\x0c'\x0c&\x0c/\x088\x10\x01\xe0"

H: b'\x00\x00\x00\x00\x00\x00\xe7\x00B\x00B\x00B\x00B\x00~\x00B\x00B\x00B\x00B\x00\xe7\x00\x00\x00\x00\x00'

华: b'\x00\x00\x00\x00\x08@\x08H\x18p(\xc0+BHB\x08~\x01\x00\x01\x00\x7f\xfe\x01\x00\x01\x00\x01\x00\x01\x00'

ǚ: b"\x00\x00\x00\x00\x00\x00\x00\x00\x14\x00\x08\x004\x00C\x00C\x00C\x00C\x00C\x00C\x00'\x00\x18\x00\x00\x00"

e: b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00<\x00B\x00~\x00@\x00@\x00B\x00<\x00\x00\x00\x00\x00'

l: b'\x00\x00\x00\x00\x00\x00p\x00\x10\x00\x10\x00\x10\x00\x10\x00\x10\x00\x10\x00\x10\x00\x10\x00\x10\x00|\x00\x00\x00\x00\x00'

o: b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00<\x00B\x00B\x00B\x00B\x00B\x00<\x00\x00\x00\x00\x00'

⑴: b'\x00\x00\x00\x00\x08\x00\x10\x08!\x84 \x82@\x82@\x83@\x81@\x81@\x81@\x82 \x82 \x84\x13\xc4\x10\x08'

................ ................ ................ ................ ................ ................
................ ................ ................ ................ .........@...... ................
................ ........@....... ................ ................ .....@@@.@.@.... ................ 
....@........... .......@@....... .....@@@@@...... ................ .@@@@....@..@... .......@........
....@@.......... .......@@....... ....@....@...... ................ ....@....@...@.. .......@@.......
....@........... .......@.@...... .........@...... ................ ....@....@...@.. ........@.......
....@........... ......@..@...... .........@...... ................ .@@@@@@@@@@@@@@. .......@........
....@........... .@@@@@@...@@@@@@ .........@...... ................ ....@....@...@.. ......@@@@@@....
....@........... ..@..........@.. ........@....... ................ ....@....@...@.. ...@@@.@........
....@........... ...@........@... .......@........ ................ ....@..@..@.@... .......@........
....@........... ....@@.....@.... .......@........ ................ ....@@@...@@.... ......@.@@@.....
....@........... ....@......@.... ......@......... ................ .@@@@.....@@.... ......@@.@@.....
................ ....@...@..@.... .....@.......... ................ ....@.....@@.... .........@......
....@........... ....@.@@.@..@... ....@@......@... .@@@............ ....@....@.@..@. ........@.......
....@........... ...@.@....@@@... ....@@@@@@..@@.. ..@@............ ....@..@@...@.@. ................
................ ...@@.......@... ................ ..@............. .@@@@........@@. ................

................ ................ ................ ................ ................ ................
................ ................ .......@........ ................ ................ ................
.@@@@@@@@@@@@@@@ ................ .......@........ ..@@@@@@@@@@@... ................ ......@@........
.@@@@@@@@@@@@@@@ ................ .......@........ ...@...@...@.... .......@@@@..... ......@@........
.@@@@@@@@@@@@@@@ .....@@@@@@@.... ..@@@@@@@@@@@@.. ....@..@...@.... .......@...@.... ......@.@@...... 
.@@@@@@@@@@@@@@@ .....@@...@@.... ..@....@.....@.. ..@@@@@@@@@@@@.. ......@@..@@.... ...@@@@@@.......
.@@@@@@@@@@@@@@@ .....@@...@@@... ..@....@.....@.. .@...@........@. ......@...@..... ......@.........
.@@@@@@@@@@@@@@@ .....@@...@@.... ..@....@.....@.. .@....@.......@. ......@.@@...... .....@@.@.......
.@@@@@@@@@@@@@@@ .....@@..@@@.... ..@....@.....@.. ...@@@@@@@@@@... ......@..@@..... .....@@@@@@@....
.@@@@@@@@@@@@@@@ .....@@@@@@@.... ..@....@.....@.. .....@.......... .....@@...@..... ....@@..@..@@...
.@@@@@@@@@@@@@@@ .....@@....@@... ..@....@.....@.. .....@@@@@@@@... .....@....@..... ...@.@.@....@@..
.@@@@@@@@@@@@@@@ .....@@....@@... ..@@@@@@@@@@@@.. ....@@@.....@... .....@...@@..... ..@..@@@....@@..
.@@@@@@@@@@@@@@@ .....@@....@@... .......@........ ...@..@@...@.... .....@...@@..... ..@..@@.....@@..
.@@@@@@@@@@@@@@@ .....@@@@@@@.... .......@........ ..@.....@@@..... .....@@@@@...... ..@.@@@@....@...
.@@@@@@@@@@@@@@@ ................ .......@........ .......@@@@..... ....@@.......... ..@@@......@....
.@@@@@@@@@@@@@@@ ................ .......@........ ...@@@@....@@@@. ....@........... .......@@@@.....

................ ................ ................ ................ ................ ................
................ ................ ................ ................ ................ ................
................ ....@....@...... ................ ................ ................ ................
@@@..@@@........ ....@....@..@... ................ ................ .@@@............ ................
.@....@......... ...@@....@@@.... ...@.@.......... ................ ...@............ ................ 
.@....@......... ..@.@...@@...... ....@........... ................ ...@............ ................
.@....@......... ..@.@.@@.@....@. ..@@.@.......... ................ ...@............ ................
.@....@......... .@..@....@....@. .@....@@........ ..@@@@.......... ...@............ ..@@@@..........
.@@@@@@......... ....@....@@@@@@. .@....@@........ .@....@......... ...@............ .@....@.........
.@....@......... .......@........ .@....@@........ .@@@@@@......... ...@............ .@....@.........
.@....@......... .......@........ .@....@@........ .@.............. ...@............ .@....@.........
.@....@......... .@@@@@@@@@@@@@@. .@....@@........ .@.............. ...@............ .@....@.........
.@....@......... .......@........ .@....@@........ .@....@......... ...@............ .@....@.........
@@@..@@@........ .......@........ ..@..@@@........ ..@@@@.......... .@@@@@.......... ..@@@@..........
................ .......@........ ...@@........... ................ ................ ................
................ .......@........ ................ ................ ................ ................

................
................
....@...........
...@........@...
..@....@@....@..
..@.....@.....@.
.@......@.....@.
.@......@.....@@
.@......@......@
.@......@......@
.@......@......@
.@......@.....@.
..@.....@.....@.
..@.....@....@..
...@..@@@@...@..
...@........@...
```

#### 使用开发板测试 1

推荐使用 [AMPY Batch Tool](https://gitee.com/walkline/a-batch-tool) (`ab`工具) 进行文件上传和调试操作

```bahs
# 上传文件
$ ab

# 进入 repl 模式
$ ab --repl

# 运行开发板上的文件
# 使用快捷键 Ctrl-T
>>>
Run onboard file
    [1] /boot.py
    [2] /drivers/ssd1306.py
    [3] /fontlib.py
Choose a file: 3
>>>

# 在开发板上运行本地文件
# 使用快捷键 Ctrl-R
>>> Run local file
    [1] fontlib.py
    [2] drivers\ssd1306.py
Choose a file: 1
>>>
```

#### 使用开发板测试 2

这是把`fontlib.py`文件中非`MicroPython`代码精简掉，并编译为字节码再运行测试的方法

```bash
# 上传文件
$ ab abconfig-mpy
```

因为上传文件中已经包含了`main.py`，所以直接复位就可以看到效果了

### 关于速度

> 以当前字库文件举例：
> * 文件名：`combined.bin`
> * 文件大小：`303,520`字节
> * `GB2312`索引表大小：`17,672`字节
> * 点阵大小：`16x16`像素
> * 字符数据大小：`32`字节
> * 字符总数：`8932`个（包含`ASCII`和`GB2312`）


* 实例化`FontLib`时打开字库文件，读取文件头信息，大约 12 ms
* 同时读取`?`的字符数据作为占位符，大约 5 ms
* 打印字库信息，大约 39 ms（简直无语，建议实际使用时不要打印）
* 检索字符数据前再次打开字库文件，大约 12 ms
* 检索字符数据，每字符大约 12 ms
* 字符数据使用`Dict`存储，字符`Unicode`值作为关键字，取值耗时可以忽略
* 显示字符耗时未统计

### 合作交流

* 联系邮箱：<walkline@163.com>
* QQ 交流群：
    * 走线物联：163271910
    * 扇贝物联：31324057

<p align="center"><img src="https://gitee.com/walkline/WeatherStation/raw/docs/images/qrcode_walkline.png" width="300px" alt="走线物联"><img src="https://gitee.com/walkline/WeatherStation/raw/docs/images/qrcode_bigiot.png" width="300px" alt="扇贝物联"></p>
