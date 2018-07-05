# 故障排除
很多时候Lottie没有正确渲染动画。After effects有许多特性，Lottie无法全部支持。如果动画看起来不对，请在报告issue前尝试以下方法。

## 检查警告
Android版Lottie会自动检测和报告部分错误。虽然无法捕获所有错误但是常见错误都会捕获。可以在自己的项目中调用`getWarnings()`或打开[Lottie 示例 app](https://play.google.com/store/apps/details?id=com.airbnb.lottie)中的动画来查看右上方是否显示警告。如果出现警告，点击警告会展示详细信息。![Warnings](/images/warnings.png)

## 查看功能支持页
查看[功能支持页](/supported-features.md)来确认功能是否支持。

## 调试
尝试独立运行部分动画来检查哪些特性没有正确渲染。尝试将范围缩小到一组特定图形效果的组合或具体的内容而不是仅仅说“它没有正确运行”。如果issue理应但还没有被处理, 可以去lottie的github页面上合适的地方提出issue并附上描述和压缩后的aep文件。

## 路径合并消失
路径合并仅支持KitKat及后续版本，必须通过`enableMergePathsForKitKatAndAbove()`手动启用。

## 动画裁剪
确保使用的Lottie是最新版本。