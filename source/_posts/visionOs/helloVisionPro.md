---
title: hello vision pro
categories:
  - vision pro
tags:
  - vision pro
---

# Vision Os Development
Start with the [official document  vision os path](https://developer.apple.com/visionos/pathway/) and start the journey of vision os development.

## Requirements
As the official notes that the development needs `frameworks like SwiftUI, UIKit, RealityKit, and ARKit`

## Cretate a new project
### Open Xcode and create a new project, select the `visionOS` template, and select `App` as the template.
<!-- ![](/images/visionOs/helloVisionPro.png) -->
<img src="/images/visionOs/helloVisionPro.png" width="600" height="400" alt="Create Vision OS Project">


### Then start the project, and select the `visionOS` simulator as the target device.
<!-- ![](/images/visionOs/helloVisionProStart.png) -->
<img src="/images/visionOs/helloVisionProStart.png" width="600" height="400" alt="Create Vision OS Project">

## The project structure
The <font color=Red>HelloVisionOsApp</font> is the main entry point of the app
```swift
import SwiftUI
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```
The Hierarchy of the app is like this:
```swift
MyApp
├── WindowGroup
│   └── ContentView
│       ├── Text
│       └── Button
│           └── Text
```
The ContentView is the main view
```swift
import SwiftUI
import RealityKit

struct ContentView: View {

    var body: some View {
        VStack {
            Text("Hello World")
        }
    }
}
```
So the app is finished, and you can run it on the simulator.

### Summary
The vision os development is based on the SwiftUI, so you need to learn the SwiftUI first, and then you can start the vision os development.
- [SwiftUI](https://developer.apple.com/documentation/swiftui/)
- [VisionOS](https://developer.apple.com/documentation/visionos/creating-your-first-visionos-app)

The Demo is simple and I remove the immersive part which will be the next post.

#### The Demo
[The Demo](https://github.com/little-stoner/VisionOs) project