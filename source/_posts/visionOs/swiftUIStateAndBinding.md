---
title: swift ui state and binding
categories:
  - vision pro
tags:
  - vision pro
---

# SwiftUI State and Binding
the state and binding is just like the state and props in react.
and the swift ui is like a combination of the view and state.

- using `State` variables to indicate data dependencies
- sharing data with other views using the `Binding` property wrapper

the small demo show that the seperation of views and state in swift
make developement easier.

<img src="/images/visionOs/swiftUIStateAndBinding.png" width="800" height="400" alt="Text">

```swift
struct StateAndBinding: View {
    
    @StateObject private var recipeBox = RecipeBox(recipes: load("recipeData.json"))
    @State private var selectedSidebarItem: SidebarItem? = SidebarItem.all
    @State private var selectedRecipeId: Recipe.ID?

    var body: some View {
        VStack {
            NavigationSplitView {
                SidebarView(selection: $selectedSidebarItem, recipeBox: recipeBox)
            } content: {
                ContentListView(selection: $selectedRecipeId, selectedSidebarItem: selectedSidebarItem ?? SidebarItem.all)
            } detail: {
                DetailView(recipeId: $selectedRecipeId)
            }
            .environmentObject(recipeBox)
        }
    }
}
```
- StateObject: A property wrapper type that instantiates an observable object.
- State: A property wrapper type that can read and write a value managed by SwiftUI.

There are other `keyword` which will be learned in the following posts.

# Summary
This is just like `vue3` with `ref` and `reactive`.