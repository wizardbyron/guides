# Swift

## 技巧

### 系统不进入休眠模式

将以下代码行复制到ViewController.Swift的viewDidLoad方法中

```swift
override func viewDidLoad() {
   super.viewDidLoad()
   // Do any additional setup after loading the view, typically from a nib.
   UIApplication.shared.isIdleTimerDisabled = true
}
```

运行该应用程序，该应用程序将永远不会进入睡眠模式。
