<h1>HW1</h1>
    
```swift

import SwiftUI

struct ContentView: View {
    var body:some View{
        Image("Tony")
            .resizable()
            .aspectRatio(contentMode: .fill)
            .overlay(
                Text("學號：1100964   姓名：陳忠翰")
                    .fontWeight(.heavy)
                    .font(.system(size:40))
            )
            .overlay(
                Image(systemName: "graduationcap.fill")
                    .font(.system(size:30))
                    .foregroundColor(.gray)
                    .opacity(0.6)
                    .frame(width:500,height:200,alignment: .top)
            )
            .overlay(
                Text("一句話：just do it")
                    .fontWeight(.heavy)
                    .lineSpacing(20)
                    .font(.system(size:32.0))
                    .foregroundColor(.white)
                    .frame(width: 400, height:300, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                    .background(Color.blue)
                    .cornerRadius(30.0)
                    .opacity(0.8)
                ,
                alignment: .bottom
            )
    }
}


    
```

<img width="40%"  src="https://raw.githubusercontent.com/wayne1007/yzu-swiftui-1100964/main/hw1-20231002-1.jpg">
