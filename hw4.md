<h1>HW4</h1>
    
```swift

import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            Text("Apple store")
                .font(.largeTitle)
                .fontWeight(.heavy)
                .foregroundStyle(.primary)
            TabView{
                Group{
                    WelcomeView()
                        .tabItem { 
                            Image(systemName: "rosette")
                            Text("Welcome")
                        }
                    
                    CourseView()
                        .tabItem { 
                            Image(systemName: "list.dash")
                            Text("Products")
                        }
                    CardView()
                        .tabItem {
                            Image(systemName: "book")
                            Text("LearnMore")
                        }
                }
                .toolbarBackground(Color.black, for: .tabBar)
                .toolbarBackground(.visible, for: .tabBar)
            }
            .tint(.yellow)
        }.padding(.top ,20)
    }
}


struct WelcomeView: View {
    var body: some View {
        VStack {
            Image("Apple")
                .resizable()
                .aspectRatio(contentMode: .fit)
            Text("您好\n歡迎光臨")
                .fontWeight(.heavy).lineSpacing(20)
                .font(.system(size: 32.0))
                .foregroundColor(.white)
                .frame(width: 350, height: 150, alignment: .center)
                .background(Color.gray)
                .cornerRadius(20.0)
                .multilineTextAlignment(.center)
        }.padding(.top ,20)
    }
}
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}

struct TermAndDescription: Identifiable{ 
    var id = UUID()
    var term:String
    var description:String
}

var myDictionary = [
    TermAndDescription(term: "Macbook", description: "computer"),
    TermAndDescription(term: "apple watch", description: "watch"),
    TermAndDescription(term: "airpods", description: "headphone"),
    TermAndDescription(term: "iphone", description: "smart phone"),
    TermAndDescription(term: "ipad", description: "modern note")
]

struct CardView: View{
    @State var currentCard = 0
    var body: some View{
        VStack{
            VStack{
                Text(myDictionary[currentCard].term)
                    .font(.title)
                    .padding(.all,10)
                Text(myDictionary[currentCard].description)
                    .font(.body)
                    .foregroundColor(.white)
                    .padding(.all,10)
            }
            .frame(minWidth: 0,idealWidth: 100,maxWidth: 300,minHeight: 0, idealHeight: 100,maxHeight: 300,alignment: .center)
            .background(Color.gray)
            .onTapGesture{
                if currentCard < myDictionary.count-1{
                    currentCard+=1
                }else{
                    currentCard=0
                }
            }
            Text("click for next pic")
                .padding(.all,10)
        }
    }
}

struct Course:Identifiable{
    var id = UUID()
    var name:String
    var image:String
    var description:String
}
var courses = [
    Course(name: "Intro to Macbook", image: "Macbook", description: "Product Macbook"),
    Course(name: "Intro to iphone", image: "Iphone", description: "Product Iphone"),
    Course(name: "Intro to Apple watch", image: "Apple watch", description: "Product Apple watch"),
    Course(name: "Intro to Ipad", image: "Ipad", description: "Product Ipad"),
    Course(name: "Intro to Airpods", image: "Airpods", description: "Product Airpods")
]

struct CourseView : View{
    @State var showDetailView = false
    @State var selectedCourse:Course?
    var body: some View{
        NavigationView{
            List(courses){ 
                courseItem in
                BasicImageRow(thisCourse: courseItem)
                    .onTapGesture{
                        self.showDetailView = true
                        self.selectedCourse = courseItem
                    }
            }
            .sheet(item: self.$selectedCourse){ thisCourse in 
                CourseDetailView(thisCourse: thisCourse)
            }
            .navigationBarTitle("產品列表")
        }
    }
}

struct BasicImageRow: View{
    var thisCourse:Course 
    var body: some View{
        HStack{
            Image(thisCourse.image)
                .resizable()
                .frame(width: 40, height: 40)
                .cornerRadius(5)
            Text(thisCourse.name)
        }
    }
}


struct CourseDetailView:View{
    @Environment(\.presentationMode) var presentationMode
    var thisCourse:Course
    var body: some View{
        ScrollView{
            VStack{
                Image(thisCourse.image)
                    .resizable()
                    .aspectRatio(contentMode: /*@START_MENU_TOKEN@*/.fill/*@END_MENU_TOKEN@*/)
                    .clipped()
                Text(thisCourse.name)
                    .font(.system(.title,design: .rounded))
                    .fontWeight(.light)
                Spacer()
            }
        }
        .overlay(
            HStack{
                Spacer()
                VStack{
                    Button(action:{
                        self.presentationMode.wrappedValue.dismiss()
                    },label: {
                        Image(systemName: "chevron.down.circle.fill")
                            .font(.largeTitle)
                            .foregroundColor(.white)
                    })
                    .padding(.trailing,20)
                    .padding(.top,40)
                    Spacer()
                }
            })
    }
}


    
```

<img width="40%"  src="https://raw.githubusercontent.com/wayne1007/yzu-swiftui-1100964/main/hw4-20231204-1.jpg">
<img width="40%"  src="https://raw.githubusercontent.com/wayne1007/yzu-swiftui-1100964/main/hw4-20231204-2.jpg">
<img width="40%"  src="https://raw.githubusercontent.com/wayne1007/yzu-swiftui-1100964/main/hw4-20231204-3.jpg">
