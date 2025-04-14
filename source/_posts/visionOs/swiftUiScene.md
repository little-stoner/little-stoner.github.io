---
title: swift ui scene
categories:
  - vision pro
tags:
  - vision pro
---

# SwiftUI Scene
```swift
import SwiftUI

@main
struct SwiftUiSceneApp: App {
    
    var body: some Scene {
        WindowGroup {
            TabView {
                ContentView()
                    .tabItem {
                        Label("Journal", systemImage: "book")
                    }
                SettingsView()
                    .tabItem {
                        Label("Settings", systemImage: "gear")
                    }
            }
        }
    }
}
```
The App return a `Scene` object.
The `Scene` return the primary scene `WidnowGroup`.
The `WindowGroup` return a `TabView` object.
The `TabView` return two views, `ContentView` and `SettingsView`.
The `TabItem` is used to set the text and icon of the tab.

<img src="/images/visionOs/swiftUiScene.png" width="600" height="400" alt="Swift UI Scene">

## Add Another WindowGroup
```swift
import SwiftUI

@main
struct SwiftUiSceneApp: App {
    
    var body: some Scene {
        WindowGroup {
            TabView {
                ContentView()
                    .tabItem {
                        Label("Journal", systemImage: "book")
                    }
                SettingsView()
                    .tabItem {
                        Label("Settings", systemImage: "gear")
                    }
            }
        }
        WindowGroup {
            AlternativeContentView()
        }
    }
}
```
Seems like the new WindowGroup does not influence the primary windowGroup.