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

## Summary
swift ui is more like a combination of HTML and CSS.
It is declarative and reactive kind of like vue.
It is easy to use and understand.
