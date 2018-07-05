# Lottie vs Android Vector Drawable (AVD)

有两种方式渲染After Effects动画：

1. 用Bodymovin导出json文件，通过lottie-android执行。
2. 用Bodymovin导出AndroidVectorDrawable xml，通过Android SDK执行。

## Lottie的优势
* 支持一系列After Effects特性。查看完整[功能支持](/after-effects/supported-features.md)列表。
* 支持手动将动画与手势，事件等关联。
* 支持通过网络加载动画。
* 支持控制播放速度。

## AnimatedVectorDrawable的优势
* 由于动画在[渲染线程](https://medium.com/@workingkills/understanding-the-renderthread-4dc17bcaf979)上执行而不是主线程，因此性能更好。