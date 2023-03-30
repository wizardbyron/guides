# Swift

## 技巧

### 系统不进入休眠模式

在 `View` 的`.onAppear` 方法中添加 `UIApplication.shared.isIdleTimerDisabled = true` 例如:

```swift
@main
struct ScreenClockApp: App {
    @StateObject var audioPlayer = AudioPlayer()

    var body: some Scene {
        WindowGroup {
            ContentView()
                .onAppear {
                  // 禁用设备的自动锁屏功能
                  UIApplication.shared.isIdleTimerDisabled = true
            }
        }
    }
}

```

运行该应用程序，该应用程序将永远不会进入睡眠模式。
