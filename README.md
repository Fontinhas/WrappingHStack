# WrappingHStack

WrappingHStack is a UI Element that works in a very similar way to HStack, but automatically positioning overflowing elements on next lines.

## Example

![Example](./example.png?raw=true)
```swift
WrappingHStack {
    Text("WrappingHStack")
        .padding()
        .font(.title)
        .border(Color.black)
    
    Text("can handle different element types")
    
    Image(systemName: "scribble")
        .font(.title)
        .frame(width: 200, height: 20)
        .background(Color.purple)
    
    Text("and loop")
        .bold()
    
    WrappingHStack(data: 1...20, id:\.self) {
        Text("Item: \($0)")
            .padding(3)
            .background(Rectangle().stroke())
    }.frame(minWidth: 250)
}
.padding()
.border(Color.black)
```

## Installation
Requirements iOS 13+

### Swift Package Manager 
1. In Xcode, open your project and navigate to File → Swift Packages → Add Package Dependency.
2. Paste the repository URL (https://github.com/dkk/WrappingHStack) and click Next.
3. For Rules, select version.
4. Click Finish.

### Swift Package
```swift
.package(url: "https://github.com/dkk/WrappingHStack", .upToNextMajor(from: "1.1.0"))
```
## Usage

Import the WrappingHStack package to your view:
```swift
import WrappingHStack
```

use it like you would use HStack for single elements:
```swift
WrappingHStack {
    /* some views */
    NewLine() // Optional: Use NewLine to force the next element to be placed in a next line
    /* some more views */
}
```

or like a ForEach to loop over items:
```swift
WrappingHStack(data: 1...30, id:\.self) {
    Text("Item: \($0)")
}
```

## Support
To support this project, you could help solving any [reported issues](https://github.com/dkk/WrappingHStack/issues) or you could [buy me a 🍪 to increase motivation](https://www.buymeacoffee.com/kloeck).

## License
WrappingHStack is released under the [MIT License](LICENSE).
