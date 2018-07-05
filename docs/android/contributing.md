# 贡献

非常欢迎贡献代码。仅需发起带有改动描述的PR。Lottie使用[Facebook screenshot tests for Android](https://github.com/facebook/screenshot-tests-for-android)来检查像素级修改/损坏。请在发起PR前执行`./gradlew --daemon recordMode screenshotTests`来确保没有损坏。请使用运行的Lollipop的Nexus 5来测试。修改部分的截图会在git diff中显示。

如果要添加更多JSON文件和截图测试，放手去做，只需把测试添加到`LottieTest`中。