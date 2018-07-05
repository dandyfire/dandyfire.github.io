# 性能

## Sizing (px -> dp)
## 尺寸 (px -> dp)
After Effects中任何像素值会被转换成与分辨率无关的像素（iOS中为points，安卓为dp）。例如，动画尺寸为24dp x 24dp，After Effects 中的布局为24px x 24px。 [这里](https://material.io/devices/)有常见的单位为dp的屏幕尺寸。

## 蒙板和遮罩

安卓上的蒙板和遮罩有很大的性能问题。性能问题跟蒙板/遮罩层与蒙板/遮罩的交叉区域有关，因此蒙板/遮罩越小，性能问题越少。如果在安卓上使用蒙板或遮罩，开启硬件加速后性能会有所提升。

## 硬件加速
在安卓上可以对动画开启软硬件加速。硬件加速更快但存在某些限制。
仅部分支持以下特性
* 反锯齿 (API 16+ only)
* 边界裁剪 (API 18+ only)
* 描边端点 (API 19+ only)

获取更多信息，阅读[这里](https://developer.android.com/guide/topics/graphics/hardware-accel.html).

总而言之，如果硬件加速有效，请尝试使用。可以在示例app中尝试开关硬件加速。

## 渲染图 (Android)
Lottie示例app自带实时渲染图，可以在右上方的菜单中开启。![Render Graph](/images/render-graph.png)