# RefreshableList

A refreshable List. Perfroming an action when scrolling to the last row.

## Installation

## Usage
Supports two main functions
onRefreshPerform: perfom an action 

```swift
struct ContentView: View {
    @State var showRefresh: Bool = false
    var body: some View {
        RefreshableList(showRefreshView: $showRefresh){
            ForEach(0..<20, id: \.self) { index in
                VStack(alignment: .leading){
                    Text("Item \(index)")
                    Divider()
                }
            }
        }
        .onRefreshPerform {
            print("add your action here")
            self.showRefresh = false
        }
        .onLastPerform {
            // add your code here
            print("on last row")
        }
    }
}
```
