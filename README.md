A widget that displays GIFs in Tkinter.  
一个能在Tkinter中显示GIF动图的控件。

介绍文章：https://www.bilibili.com/read/cv31300353/  
导入方式： from TkGifWidget import *或import TkGifWidget

缺陷： 因为Tk的图像加载方式，极少部分透明度不规则的GIF动图加载速度会极慢。

### 2024/7/14更新：

1. AnimatedGif类新增play_end_func形参，以便在动图播放结束时回调处理。感谢B站@只是一个球_提出的建议
2. 以下改动（未全部列出）使控件可以修改动图，也可以在指定动图前先创建控件：
    * AnimatedGif类file_path, play_mode形参变为默认值形参。
    * 设置动图的部分移至set_gif()方法。
    * bg_img属性只读，且值类型变为Image对象而非PhotoImage。
    * 使用bg_imgtk只读属性获取PhotoImage对象。
    * 新增set_bg_img()方法用于设置当前背景图。（若想指定默认背景图请修改default_bg属性）
    * 处理背景图部分移至apply_bg_func()方法。
    * 新增set_play_mode()方法用于设置播放模式。
    * AnimatedGif类bg_path属性名称修改为default_bg（即使这样不符合向下兼容）。 default_bg用于指定默认的背景图，值可以是路径或Image对象。
3. 修复调用end_play()后，在小于duration时间内再调用start_play()会使播放速度加倍的BUG。
4. 修改内部图像容器的borderwidth为0以确保无边框。
5. AnimatedGif类新增nogif_bg形参，用于指定没有动图时的背景图。

### 2024/7/28更新：

* 修复动图在播放时透明颜色不能正确显示的BUG。感谢B站@只是一个球_
* 添加帧持续时间缺失时的处理。

### 2025/2/21更新：

* Add English translation of the module's documentation string. 为模块中的文档字符串添加英文翻译。
* Adding the module to PyPI and GitHub. 将该模块添加到PyPI和Github上。