# 图片

如果动画直接从assets中加载且图片在assets的子目录中，就可以在图片上执行动画。只需要在`LottieAnimationView`或`LottieDrawable`上调用`setImageAssetsFolder`并确保bodymovin导出的图片在目录中且没有改名\(由img_开头)。如果直接使用`LottieDrawable`,执行完成后要调用`recycleBitmaps`。

若要使用从网络上下载的自定义位图，可以使用代理实现：
 ```java
animationView.setImageAssetDelegate(new ImageAssetDelegate() {
  @Override public Bitmap fetchBitmap(LottieImageAsset asset) {
    // Your bitmap fetching code
  }
});
```