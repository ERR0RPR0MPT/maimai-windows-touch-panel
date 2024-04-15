# maimai-windows-touch-panel

记录 Windows 设备的触屏事件并模拟 maimai 分区触摸屏幕的脚本.

软件模拟分区触摸, 可用于 maimai 自制手台上.

## 使用方法

1. Windows 设置 - 蓝牙和其他设备 - 触控 - 三指和四指的触摸手势 - 关闭
2. 辅助功能 - 鼠标指针与触控 - 触控指示器 - 关闭
3. 控制面板 - 硬件和声音 - 笔和触控 - 关闭"触摸回应"中的"触摸屏幕时显示直观回应"
4. 打开任意P图工具, 准备一个和显示屏幕大小相同的一张图片(例如:2160x3840), 将 `./image/color_exp_panel.png`
   放置到该图片圆形触摸区域的位置, 编辑好的图片放到脚本 `image` 目录下取名 `image_monitor.png`.
5. 编辑 `config.yaml` 配置文件, 修改 `exp_image_dict` 配置, 将各区块对应的 RGB 通道颜色值改为刚P的图的对应区块颜色值(
   一般不用改默认就行)
6. 执行 `pip install -r ./requirements.txt` 安装依赖
7. 编辑 `config.yaml` 配置文件
8. 下载一个 `VSPD` 虚拟串口工具, 将 `COM3` 和 `COM33` 建立转发
9. 触摸屏连接到电脑, 先双击运行 `start.bat`, 再运行游戏, 脚本控制台输出 `已连接到游戏` 即可
10. 进游戏调整判定A/B的延迟直到可用
11. 打一把看看蹭不蹭星星/触控是否灵敏, 根据体验修改 `AREA_SCOPE` 变量
12. 如果单点延迟低但滑动时延迟变高, 请将脚本中 `TOUCH_THREAD_SLEEP_MODE` 修改为 false,
    或者可以调小 `TOUCH_THREAD_SLEEP_DELAY` 的值(如果还是卡请提 issue 反馈)

## 命令列表

游戏时如果不小心断开连接, 请在控制台输入 `start` 并回车来重新连接游戏

输入 `reverse` 可调整触控设备屏幕方向

输入 `restart` 可重新读取配置文件/重启脚本

## 注意

想要加 2P 的重新复制一下脚本并添加串口 COM4 到 COM44 的转发就好

该脚本仅用于测试.

## 类似项目

[maimai-android-touch-panel](https://github.com/ERR0RPR0MPT/maimai-android-touch-panel)

## 许可证

[MIT License](https://github.com/ERR0RPR0MPT/maimai-windows-touch-panel?tab=MIT-1-ov-file)

## 其他

编辑好的区块成品图类似这样:

![](https://raw.githubusercontent.com/ERR0RPR0MPT/maimai-android-touch-panel/main/image/image_monitor.png)
