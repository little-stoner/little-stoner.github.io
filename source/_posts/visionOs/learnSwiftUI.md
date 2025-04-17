---
title: learn swift ui
categories:
  - vision pro
tags:
  - vision pro
---

# Learn SwiftUI

## Text
`Text` is like text tag in HTML.
It is used to display text on the screen.
It can be used to display text in different styles, such as bold, italic, and underline.
```swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text("Hello, world!")
                .font(.largeTitle)
            Text("Text")
                .font(.caption)
                .italic()
        }
        .padding()
    }
}
```
<img src="/images/visionOs/swiftUIText.png" width="800" height="400" alt="Text">

## Symbols
Symbols are like icons in HTML.
```swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text("Hello, world!")
                .font(.largeTitle)
            Text("Text")
                .font(.caption)
                .italic()
        }
        .padding()
        
        HStack {
            Image(systemName: "folder.badge.plus")
            Image(systemName: "heart.circle.fill")
            Image(systemName: "alarm")
        }
        .symbolRenderingMode(.multicolor)
        .font(.largeTitle)
    }
}
```
<img src="/images/visionOs/swiftUISymbol.png" width="800" height="400" alt="Text">

## Label
To use both text and symbol to represent a single element.
```swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text("Hello, world!")
                .font(.largeTitle)
            Text("Text")
                .font(.caption)
                .italic()
        }
        .padding()
        
        HStack {
            Image(systemName: "folder.badge.plus")
            Image(systemName: "heart.circle.fill")
            Image(systemName: "alarm")
        }
        .symbolRenderingMode(.multicolor)
        .font(.largeTitle)
        
        HStack {
            Label("Favorite Books", systemImage: "books.vertical")
                .labelStyle(.titleAndIcon)
                .font(.largeTitle)
        }
        .padding()
        
    }
}
```
<img src="/images/visionOs/swiftUILabel.png" width="800" height="400" alt="swiftUILabel">

## Control
Control is interactive elements that allow users to interact with the app.
```swift
VStack {
    HStack {
        Picker("Choice", selection: $choice) {
            Text("Option 1").tag(0)
            Text("Option 2").tag(1)
            Text("Option 3").tag(2)
        }
        Button("OK") {
            applyChanges()
        }
    }
    .controlSize(.mini)
    HStack {
        Picker("Choice", selection: $choice) {
            Text("Option 1").tag(0)
            Text("Option 2").tag(1)
            Text("Option 3").tag(2)
        }
        Button("OK") {
            applyChanges()
        }
    }
    .controlSize(.large)
}
```
<img src="/images/visionOs/swiftUIControl.png" width="800" height="400" alt="swiftUIControl">

## Image
Image is just like image tag in HTML.
```swift
HStack {
    Image("TUTU")
        .resizable()
        .scaledToFit()
}
```
<img src="/images/visionOs/swiftUITUTU.png" width="800" height="400" alt="swiftUITUTU">

## Shape
Shape provides several common shapes.
```swift
HStack {
    Rectangle()
        .foregroundColor(.blue)
    Circle()
        .foregroundColor(.orange)
    RoundedRectangle(cornerRadius: 15, style: .continuous)
        .foregroundColor(.green)
}
.aspectRatio(3.0, contentMode: .fit)
```
<img src="/images/visionOs/swiftUIShape.png" width="800" height="400" alt="swiftUIShape">


## Scale views 
View layout that adapts to the font styles, Dynamic Type, and varying string lengths.
```swift
import SwiftUI
import RealityKit
import RealityKitContent

struct KeywordBubbleDefaultPadding: View {
    let keyword: String
    let symbol: String
    var body: some View {
        Label(keyword, systemImage: symbol)
            .font(.title)
            .foregroundColor(.white)
            .padding()
            .background(.purple.opacity(0.75), in: Capsule())
    }
}

struct KeywordBubbleDefaultPadding_Previews: View {
    let keywords = ["chives", "fern-leaf lavender"]
    var body: some View {
        VStack {
            ForEach(keywords, id: \.self) { word in
                KeywordBubbleDefaultPadding(keyword: word, symbol: "leaf")
            }
        }
    }
}

struct ScalingView: View {

    var body: some View {
        VStack {
            KeywordBubbleDefaultPadding_Previews()
        }
    }
}
```
<img src="/images/visionOs/swiftUIScaleView.png" width="800" height="400" alt="swiftUIScaleView">

## Layering content
The iphone message overlay effect
```swift
struct Caption: View {
    let text: String
    var body: some View {
        Text(text)
            .padding()
            .background(Color("TextContrast").opacity(0.75),
                        in: RoundedRectangle(cornerRadius: 10.0, style: .continuous))
            .padding()
    }
}

struct CaptionedPhoto: View {
    let assetName: String
    let captionText: String
    var body: some View {
        Image(assetName)
            .resizable()
            .scaledToFit()
            .overlay(alignment: .bottom) {
                Caption(text: captionText)
            }
            .clipShape(RoundedRectangle(cornerRadius: 10.0, style: .continuous))
            .padding()
    }
}


struct LayeringContent : View {
    
    let landscapeName = "mars"
    let landscapeCaption = "This photo is wider than it is tall."
    let portraitName = "mars"
    let portraitCaption = "This photo is taller than it is wide."
    var body: some View {
            CaptionedPhoto(assetName: portraitName,
                           captionText: portraitCaption)
            CaptionedPhoto(assetName: landscapeName,
                           captionText: landscapeCaption)
            .preferredColorScheme(.dark)
            CaptionedPhoto(assetName: landscapeName,
                           captionText: landscapeCaption)
            .preferredColorScheme(.light)
        }
    
}
```

## Hide A View
Hide a view is the way in vue `v-if`
```swift
struct IfElseTrain: View {
    var longerTrain: Bool
    
    var body: some View {
        VStack {
            HStack {
                Image(systemName: "train.side.rear.car")
                if longerTrain {
                    Image(systemName: "train.side.middle.car")
                }
                Image(systemName: "train.side.front.car")
            }
            Divider()
        }
    }
}

struct HideView : View {
    
    var body : some View {
        IfElseTrain(longerTrain: true)
        IfElseTrain(longerTrain: false)
    }
}
```
<img src="/images/visionOs/swiftUIHideView.png" width="800" height="400" alt="swiftUIHideView">

## Stacks
Stacks align the element in its.
`HStack`, `VStack`, `ZStack`
```swift
struct StackView : View {
    
    var body : some View {
        VStack {
            
        }
        HStack {
            
        }
        ZStack {
            
        }
    }
}
```

## AdjustingTheSpace
specify the space and alignment of the element.
```swift
struct AdjustingTheSpace : View {
    var body : some View {
        VStack {
            Text("Default Spacing")
            HStack(spacing: 20) {
                TrainCar(.rear)
                TrainCar(.middle)
                TrainCar(.front)
            }
            TrainTrack()
        }
    }
}
```
```swift
struct AdjustingTheSpace : View {
    var body : some View {
        VStack {
            Text("Default Spacing")
            HStack(spacing: 0) {
                TrainCar(.rear)
                TrainCar(.middle)
                TrainCar(.front)
            }
            TrainTrack()
        }
    }
}
```
<img src="/images/visionOs/swiftUISpacing.png" width="800" height="400" alt="swiftUISpacing">

add padding between elements
```swift
struct AdjustingTheSpace : View {    
    var body : some View {
        VStack {
            Text("Default Spacing")
            HStack(spacing: 20) {
                TrainCar(.rear)
                    .padding([.leading])
                    .background(Color.blue)
                TrainCar(.middle)
                    .padding()
                    .background(Color.blue)
                TrainCar(.front)
            }
            .padding()
            .background(Color.green)
            TrainTrack()
        }
    }
    
}
```
<img src="/images/visionOs/swiftUIPadding.png" width="800" height="400" alt="swiftUIPadding">

## Summary
swift ui is more like a combination of HTML and CSS.
It is declarative and reactive kind of like vue.
It is easy to use and understand.
