# 动态颜色

支持对整个动画、特定层或层内特定内容添加色彩滤镜：

```java
// Any class that conforms to the ColorFilter interface
PorterDuffColorFilter colorFilter = new PorterDuffColorFilter(Color.RED, PorterDuff.Mode.LIGHTEN);

// Color filter helper supplied by Lottie
colorFilter = new SimpleColorFilter(Color.RED);

// Adding a color filter to the whole view
animationView.addColorFilter(colorFilter);

// Adding a color filter to a specific layer
animationView.addColorFilterToLayer("hello_layer", colorFilter);

// Adding a color filter to specfic content on the "hello_layer"
animationView.addColorFilterToContent("hello_layer", "hello", colorFilter);

// Clear all color filters
animationView.clearColorFilters();
```

支持在布局XML文件中对整个动画添加色彩滤镜，通过`PorterDuff.Mode.SRC_ATOP`来应用：

```xml
<com.airbnb.lottie.LottieAnimationView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:lottie_fileName="hello-world.json"
        app:lottie_colorFilter="@color/blue" />
```

注意：色彩滤镜只能用在图片层和包含填充，线条或组内容的填充层上。

你可以在[这里](https://developer.android.com/reference/android/graphics/PorterDuff.Mode.html)了解更多不同的色彩滤镜。
