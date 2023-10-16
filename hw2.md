<h1>HW2</h1>
    
```swift

import SwiftUI

struct ContentView: View {
    @State var count:Int = 0
    @State var count2:String = "剪刀"
    var body: some View {
        VStack{
            Text(String(count2))
                .padding(.all,10)
                .frame(width:150, height: 120, alignment:.center )
                .font(.system(size:60))
            
            Text(String(count))
                .padding(.all,10)
                .frame(width:150, height: 120, alignment:.center )
                .font(.system(size:100))
            Button(action: {
                 count = Int.random(in: 0..<3)
                if(count == 0) {count2 = "剪刀"}
                if(count == 1) {count2 = "石頭"}
                if(count == 2) {count2 = "布"}
            },label:{
                Text("Go")
                    .padding(.all,10)
                    .frame(width:300, height: 100,alignment: .center)
                    .font(.system(size:50))
                    .background(Color.purple)
                    .foregroundColor(.white)
                    .border(Color.purple,width:5)
                    .cornerRadius(20)
            })
        }
    }
}

    
```

<img width="40%"  src="https://github.com/wayne1007/yzu-swiftui-1100964/blob/main/hw2-20231009-1.jpg">
