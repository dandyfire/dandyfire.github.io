# 初始化
Gradle是唯一支持配置文件，因此只需要在`build.gradle`中添加依赖：

<pre><code class="lang-groovy">dependencies {
    ...
    compile 'com.airbnb.android:lottie:{{ book.androidVersion }}'
    ...
}
</code></pre>

Lottie支持安卓4.0(API 14)及以上。LottieAnimationView是最简单的使用方式：

```xml
<com.airbnb.lottie.LottieAnimationView
        android:id="@+id/animation_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:lottie_fileName="hello-world.json"
        app:lottie_loop="true"
        app:lottie_autoPlay="true" />
```

也可以通过多种方式程序化加载。

例如从app/src/main/assets里的json文件加载：

```java
LottieAnimationView animationView = (LottieAnimationView) findViewById(R.id.animation_view);
animationView.setAnimation("hello-world.json");
animationView.loop(true);
animationView.playAnimation();
```

这种方法加载完动画文件后会在后台解析，一旦解析完成就异步执行渲染。

如果想对列表中的每一项复用相同动画或者想从网络请求的JSONObject中加载动画，可以参考以下做法：

```java
 LottieAnimationView animationView = (LottieAnimationView) findViewById(R.id.animation_view);
 ...
 Cancellable compositionCancellable = LottieComposition.Factory.fromJson(getResources(), jsonObject, (composition) -> {
     animationView.setComposition(composition);
     animationView.playAnimation();
 });

 // Cancel to stop asynchronous loading of composition
 // compositionCancellable.cancel();
```

控制动画或添加监听：

```java
animationView.addAnimatorUpdateListener((animation) -> {
    // Do something.
});
animationView.playAnimation();
...
if (animationView.isAnimating()) {
    // Do something.
}
...
animationView.setProgress(0.5f);
...
// Custom animation speed or duration.
ValueAnimator animator = ValueAnimator.ofFloat(0f, 1f)
    .setDuration(500);
animator.addUpdateListener(animation -> {
    animationView.setProgress(animation.getAnimatedValue());
});
animator.start();
...
animationView.cancelAnimation();
```

更深入来说，`LottieAnimationView`使用`LottieDrawable`渲染动画。若有需要，可以直接使用drawable：

```java
LottieDrawable drawable = new LottieDrawable();
LottieComposition.Factory.fromAssetFileName(getContext(), "hello-world.json", (composition) -> {
    drawable.setComposition(composition);
});
```

# 示例App

自行编译示例app或从[Play Store](https://play.google.com/store/apps/details?id=com.airbnb.lottie)下载。示例app包含内置动画，支持从内部存储或url加载自定义动画。
<br/>
<a href='https://play.google.com/store/apps/details?id=com.airbnb.lottie'><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/images/generic/en_badge_web_generic.png' height="80px"/></a>