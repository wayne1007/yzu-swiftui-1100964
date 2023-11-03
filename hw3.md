<h1>HW3</h1>
    
```swift

import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            TitleView()
            sneakerView(imageName: "Dunk")
            sneakerView(imageName: "Airmax")
            sneakerView(imageName: "Slide")
            
        }
    }
}
struct TitleView: View{
    var body: some View{
        VStack(alignment:.center,spacing:2){
            Text("1100964的")
                .font(.system(size:30))
            Text("收藏櫃")
                .font(.title)
                .foregroundColor(Color(red:29/255,green:192/255,blue:40/255))
        }
    }
}

struct sneakerView: View{
    var imageName:String
    var body:some View{
        VStack{
            Image(imageName)
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20,alignment: .center)
            Text(imageName.capitalized)
                .fontWeight(.bold)
                .font(.system(size: 25))
        }
        .padding(.all ,2 )
    }
}


extension UIScreen{
    static let screenWidth = UIScreen.main.bounds.size.width
    static let screenHeight = UIScreen.main.bounds.size.height
    static let screenSize = UIScreen.main.bounds.size
}
    
```

<img width="40%"  src="https://github.com/wayne1007/yzu-swiftui-1100964/blob/main/hw3-20231103-3.jpg">
