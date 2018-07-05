# 缓存和预加载 

如果动画执行频繁，`LottieAnimationView`内置了可选的缓存策略。将`LottieAnimationView#setAnimation(String, CacheStrategy)` . `CacheStrategy`的值设为`Strong` , `Weak` , 或`None`来指定`LottieAnimationView`对动画加载和编译的缓存强弱。

可以手动加载LottieComposition，取得引用并调用`LottieAnimationView#setAnimation(LottieComposition)`来跳过序列化从而立即加载动画。
