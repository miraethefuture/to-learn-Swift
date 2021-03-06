---
title: "SwiftUI Tutorial: Landmarks"
categories:
  - TIL
tags:
  - learning
  - ๊ณต๋ถ ๊ธฐ๋ก
  - Swift
show_date: true
toc: true
toc_sticky: true
toc_label: "๐"
toc_icon: "๐"
---

<sub>SwiftUI Tutorial์ ๋ฐ๋ผ๊ฐ๋ฉฐ ์๋ Landmark์ฑ์ ๋ง๋ค์ด ๋ณด๊ฒ ์ต๋๋ค. ํํ ๋ฆฌ์ผ์ ์ถ์ฒ๋ [SwiftUI Essentials](https://developer.apple.com/tutorials/swiftui/creating-and-combining-views) ์๋๋ค.</sub>
<br>
<br>
<br>

<center><video src="https://user-images.githubusercontent.com/85061148/159120793-a9d5166b-fad5-41f0-899a-fcfe0bee25da.mov" controls="controls" style="max-width: 300px">
</video></center>  

<br>
<br>

# **โ๏ธ What I Learned From This Tutorial**  

- SwiftUI ํ๋ ์์ํฌ์ ๋ค๋ฅธ ํ๋ ์์ํฌ๋ฅผ ํจ๊ป ์ฌ์ฉํ๋ ๋ฐฉ์
- ์ฌ๋ฌ๊ฐ์ ํ์ผ์ ํ๋์ View๋ก ํฉ์น๊ธฐ
- Stack์ ์ฌ์ฉ๋ฒ
- ์ง๋์ ๊ด๋ จ๋ Structures
- alignment: .leading
- Divider()
- Spacer()
<!-- - Binding ($) -->

<br>
<br>

# SwiftUI Essentials
## Creating and Combining Views
### 1. Stacks์ ์ด์ฉํด ํ์คํธ ๋ฐฐ์นํ๊ธฐ: ContentView.swift

```swift
// ContentView.swift
// Landmarks

import SwiftUI

struct ContentView: View {
  var body: some View {

    VStack(alignment: .leading) {

        Text("๊ฒฝ๋ณต๊ถ")
            .font(.title)
            .foregroundColor(.black)

        HStack {

            Text("Gyeongbokgung Palace")
                .font(.subheadline)
            Text("Korea")
                .font(.subheadline)
        } // HStack ๋
        .font(.subheadline)
        .foregroundColor(.secondary)

        Divider()
        Text("About Gyeongbokgung")
            .font(.title2)
        Text("Gyeongbokgung, also known as Gyeongbokgung Palace or Gyeongbok Palace,
        was the main royal palace of the Joseon dynasty.
        Built in 1395, it is located in northern Seoul, South Korea.")
            .font(.body)

    } // VStack
    .padding()
  }
}

struct ContentView_Previews: PreviewProvider {
  static var previews: some View {
      ContentView()
    }
}
```  

  ์ด ๋ถ๋ถ์์๋ Stack๊ณผ Spacer()๋ฅผ ์ด์ฉํด์ Text view๋ฅผ ๋ฐฐ์นํ๋ ๊ฒ์ ๋ํด ์์๋ณด์์ต๋๋ค. <code>.foregroundColor(.secondary)</code>๋ ์์ ํ์์ ํ๋ฉด์ ๋ณด์ฌ์ค๋๋ค. alignment๊ฐ ๊ธฐ๋ณธ์ ์ผ๋ก๋ ๊ฐ์ด๋ฐ๋ก ์ง์ ๋์ด ์๊ณ  ์ผ์ชฝ ์ ๋ ฌ์ ํ๋ ค๋ฉด <code>(alignment: .leading)</code>์ ์ฌ์ฉํ๋ฉด ๋ฉ๋๋ค.  
  ์๋๋ ์ ์ฝ๋๊ฐ ํ๋ฉด์ ๊ทธ๋ ค์ง ๊ฒฐ๊ณผ์๋๋ค. Divider()๋ฅผ ์ด์ฉํด ์ฝํ์ธ ๋ฅผ ๋๋๋ ์ค์ ๊ทธ๋ฆด ์ ์์ต๋๋ค.


<center><img src="/assets/images/Landmarks1.png" alt="gbg" width= "300">
</center>  


### 2. ์ง๋์ ๊ด๋ จ๋ ๋ฐ์ดํฐ ๋ถ๋ฌ์ค๊ธฐ: MapView.swift  


```swift
// MapView.swift
// Landmarks

import SwiftUI
import MapKit

struct MapView: View {
    @State private var region = MKCoordinateRegion(
        // ๊ฒฝ๋ณต๊ถ์ ์๋์ ๊ฒฝ๋
        center: CLLocationCoordinate2D(latitude: 37.580_535, longitude: 126.977_341),
        span: MKCoordinateSpan(latitudeDelta: 0.05, longitudeDelta: 0.05)
        )

    var body: some View {
        Map(coordinateRegion: $region)
    }
}

struct MapView_Previews: PreviewProvider {
    static var previews: some View {
        MapView()
    }
}
```  




SwiftUI ํ๋ ์์ํฌ๋ฅผ ์ถ๊ฐํ๊ณ  ๊ทธ ์ธ์ ๋ ๋ค๋ฅธ ํ๋ ์ ์ํฌ๋ฅผ ์ถ๊ฐํ๋ฉด,  
(์ฌ๊ธฐ์๋ MapKit๋ผ๋ ํ๋ ์์ํฌ๋ฅผ ์ถ๊ฐํ์ต๋๋ค.)  
์ถ๊ฐ๋ ํ๋ ์์ํฌ์ ๊ด๋ จ๋ SwiftUI์ ํน์  ๊ธฐ๋ฅ์ ์ ๊ทผํ  ์ ์๊ฒ ๋ฉ๋๋ค.


MKCoordinateRegion๋ ์๋, ๊ฒฝ๋๋ก ํ์๋ ํน์  ์ขํ ํ๋ฉด์์ ์ง์ญ์ ์ง์ฌ๊ฐํ์ ํํ๋ก ๊ฐ์ ธ์ค๋ Structure์๋๋ค. ์ ์ฝ๋์์๋ ๊ฐ์ ธ์จ ์ง์ญ ์ ๋ณด๋ฅผ region์ด๋ผ๋ ์ด๋ฆ์ private state variable์ ๋ด์์ต๋๋ค.  

center: ์ span:์ ํ๋ผ๋ฏธํฐ ์๋๋ค.  
center: ๋ ๊ฐ์ด๋ฐ ์ค๊ฒ ๋  ์ง์ญ์ ์๋, ๊ฒฝ๋  
span: ์ ์ง๋๊ฐ ๋ณด์ฌ์ง ํฌ๊ธฐ๋ฅผ ๋ํ๋ด๋ horizontal span๊ณผ vertical span์ด ๋ค์ด์ฌ ๊ฒ์๋๋ค.

CLLocationCoordinate2D์ ๊ตญ์  ์ขํ๊ณ๋ฅผ ๊ธฐ์ค์ผ๋ก ํน์  ์ง์ญ์ ์๋ ๊ฒฝ๋๋ฅผ ์ด์ฉํ์ฌ ์ง์ญ ์ขํ object๋ฅผ ์์ฑํ๋ Structure์๋๋ค. center: ํ๋ผ๋ฏธํฐ๋ฅผ ์ง๋๋ ๊ฐ์ด๋ ์์ฑ๋ ์ขํ object๋ฅผ ์ค์ฌ์ ์ผ๋ก ์ฌ์ฉํ๋ค๋ ๋ป์ด๊ฒ ์ฃ ?

MKCoordinateSpan์ ์ง๋๋ก ํํ๋ ์ง์ญ์ ๊ฐ๋ก์ ์ธ๋ก ํฌ๊ธฐ๋ฅผ ํํํ๋ Structure์๋๋ค. delta values๋ฅผ ์ด์ฉํด์ ์ํ๋ ์ค ๋ ๋ฒจ์ ์ค์ ํ  ์ ์์ต๋๋ค. delta value์ด ์ปค์ง๋ฉด ์ค ๋ ๋ฒจ์ ์์์ง๋๋ค. delta value๊ฐ ์์์ง๋ฉด ์ค ๋ ๋ฒจ์ ์ปค์ง๋ฉด์ ๋ ๊ฐ๊น์ด ์ง๋๋ฅผ ๋ณผ ์ ์์ต๋๋ค.

body property์ Map()์ Generic Structure๋ก, ์ฌ์ฉํ  ์ง๋ ์ธํฐํ์ด์ค๋ฅผ ๋ณด์ฌ์ฃผ๋ ์ญํ ์ ํฉ๋๋ค. ์ ์ฝ๋์๋ ํํ๋์ง ์์์ง๋ง ์ฌ์ฉ์์ ์์น๋ฅผ ๋ณด์ฌ์ฃผ๊ฑฐ๋ ์ด๋๊ฒฝ๋ก๋ฅผ ์ถ์ ํ๋ ๋ฑ์ ๊ธฐ๋ฅ์ ํฉ๋๋ค.  
์๋๋ ์ ์ฝ๋๊ฐ ํ๋ฉด์ ๊ทธ๋ ค์ง ๊ฒฐ๊ณผ์๋๋ค. ๋๋ธ ํด๋ฆญ์ ํ์ฌ ํ๋ฉด์ ํ๋ํ๊ฑฐ๋, ์์ชฝ์ผ๋ก ๋์ด ์์ง์ผ ์ ์์ต๋๋ค.
<br>

<center><video src="https://user-images.githubusercontent.com/85061148/158296265-93e3410e-c9f0-46e2-9e10-b237f9ea7320.mov" controls="controls" style="max-width: 300px">
</video></center>


### 3. ๋๊ทธ๋ผ๋ฏธ ๋ชจ์์ผ๋ก ์ด๋ฏธ์ง ์๋ผ๋ด๊ธฐ: CircleImage.swift

```swift
//  CircleImage.swift
//  Landmarks

import SwiftUI

struct CircleImage: View {
    var body: some View {
        Image("kbpalace")
            .clipShape(Circle())
            .overlay {
                Circle().stroke(.white, lineWidth: 4)
            } //overlay {}
            .shadow(radius: 7)
    }
}

struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }
}
```  
์ด ๋ถ๋ถ์์๋ <code>.clipShape(Circle())</code> ๋ฉ์๋๋ฅผ ์ฌ์ฉํ์ฌ ์ด๋ฏธ์ง๋ฅผ ๋๊ทธ๋๊ฒ ์๋ผ๋๋๋ค. .overlay ๋ถ๋ถ์์๋ ํ๋๋ฆฌ๊ฐ ๋  ๋ถ๋ถ์ ๋ง๋ค์ด ์ค๋๋ค. overlay ๋ฉ์๋๋ ๋ ์ด์ด๋ฅผ ๋ง๋ค์ด ์ค๋๋ค. ์ฐ๋ฆฌ๊ฐ ์์์ ๋ง๋ค์๋ ๋๊ทธ๋ผ๋ฏธ ๋ชจ์์ ์ฌ์ง ์์ ๋ ์ด์ด๊ฐ ํ์ธต ์๊ธฐ๋ ๊ฑฐ์ฃ . Circle().stroke(.white, lineWidth: 4)๋ ๋๊ทธ๋ผ๋ฏธ ๋ชจ์์ ํ๋๋ฆฌ๋ฅผ ๊ทธ๋ ค์ค๋๋ค. .shadow๋ ๊ทธ๋ฆผ์๋ฅผ ๊ทธ๋ ค์ค๋๋ค.

<center><img src="/assets/images/Landmarks2.png" alt="CircleImage" width="300"></center>

### 4. Views๋ฅผ ๊ฒฐํฉํ๊ธฐ  

```swift
//  ContentView.swift
//  Landmarks

import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            MapView()
                .ignoresSafeArea(edges: .top)
                .frame(height: 300)

            CircleImage()
                .offset(y: -130)
                .padding(.bottom, -130)

            VStack(alignment: .leading) {
                Text("๊ฒฝ๋ณต๊ถ")
                    .font(.title)
                .foregroundColor(.black)
                HStack {
                    Text("Gyeongbokgung Palace")
                        .font(.subheadline)
                    Spacer()
                    Text("Korea")
                        .font(.subheadline)
                } // HStack
                .font(.subheadline)
                .foregroundColor(.secondary)

                Divider()
                Spacer()
                Text("About Gyeongbokgung")
                    .font(.title2)
//                Spacer()
                Text("Gyeongbokgung, also known as Gyeongbokgung Palace or Gyeongbok Palace, was the main royal palace of the Joseon dynasty. Built in 1395, it is located in northern Seoul, South Korea.")
                    .font(.body)
                Spacer()


            } // VStack
            .padding()

            Spacer()
        } // ๊ฐ์ฅ ๋ฐ๊นฅ์ชฝ VStack

    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```

์ด์  ์์์ ๋ง๋  ๋ชจ๋  View ๋ค์ ํฉ์ณ์ค๋๋ค. .offset() ๋ฉ์๋์ y ํ๋ผ๋ฏธํฐ์ ๊ฐ์ ์ฃผ์ด ์๋์ dimension์์ ์ฝํ์ธ ๋ฅผ ์กฐ๊ธ ์ฌ๋ ค์ค๋๋ค. .offset() ๋ฉ์๋๊ฐ ์๋ค๋ฉด VStack ์์์ ๊ฒน์น์ง ์๊ณ  ๋์ด๋์ด ์์ ๊ฒ์๋๋ค.

## Handling User Input  
### Section 1: Mark the User's Favorite Landmarks  

  ์๋์ ๊ฐ์ด Boolํ์ ์์ฑ์ landmark ๋ชจ๋ธ์ ์ถ๊ฐํด์ค๋๋ค.  

  ```swift
  struct Landmark: Hashable, Codable, Identifiable {
    var id: Int
    var name: String
    var park: String
    var state: String
    var description: String
    var isFavorite: Bool
    ...
  }
  ```

  ์๋๋ landmarkData.json ํ์ผ์๋๋ค. ์๋์ ๊ฐ์ ๋ฐ์ดํฐ๊ฐ ๊ฐ ๋๋๋งํฌ๋ง๋ค ์๋ ฅ๋์ด ์์ต๋๋ค. ๋ชจ๋ธ์ ์์ฑ๊ณผ ๊ฐ์ ์ด๋ฆ์ ํค๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค. Landmark structure๊ฐ Codableํ๊ธฐ ๋๋ฌธ์ ํค์ ๊ฐ์ ์ด๋ฆ์ ๊ฐ์ง ์์ฑ์ ์์ฑํด์ค์ผ๋ก์จ json ํ์ผ์ ์ฐ๊ฒฐ๋ ๊ฐ์ ์ฝ์ด์ฌ ์ ์์ต๋๋ค.

  ```swift
  [
    {
        "name": "Turtle Rock",
        "category": "Rivers",
        "city": "Twentynine Palms",
        "state": "California",
        "id": 1001,
        "isFeatured": true,
        "isFavorite": true,
        "park": "Joshua Tree National Park",
        "coordinates": {
            "longitude": -116.166868,
            "latitude": 34.011286
        },
        "description": "Suscipit inceptos est felis purus aenean aliquet adipiscing diam venenatis, augue nibh duis neque aliquam tellus condimentum sagittis vivamus, ... Interdum mattis sapien ac orci vestibulum vulputate laoreet proin hac, maecenas mollis ridiculus morbi praesent cubilia vitae ligula vel, sem semper volutpat curae mauris justo nisl luctus, non eros primis ultrices nascetur erat varius integer.",
        "imageName": "turtlerock"
    },
  ... ]
  ```

  ```swift
  import SwiftUI

  struct LandmarkRow: View {
      var landmark: Landmark

      var body: some View {
          HStack {
              landmark.image
                  .resizable()
                  .frame(width: 50, height: 50)
              Text(landmark.name)

              Spacer()

              // SwiftUI blocks์์ ์กฐ๊ฑด์ ์ผ๋ก ๋ทฐ๋ฅผ ํฌํจํ  ๋ if๋ฌธ์ ์ฌ์ฉํฉ๋๋ค.
              // Landmark ๋ชจ๋ธ์ isFavorite ์์ฑ์ด true๋ผ๋ฉด
              if landmark.isFavorite {
                  Image(systemName: "star.fill")
                      .foregroundColor(.yellow)
              }
          }
      }
  }
  ```
  isFavorite ์์ฑ์ด true์ธ ๊ฒฝ์ฐ์๋ ๋ฆฌ์คํธ์ ๋ณ์ด ๋ํ๋๋๋ก if๋ฌธ์ ์์ฑํด์ค๋๋ค.  

  <center><img src="/assets/images/Landmarks3.png" alt="stars" width="400"></center>

### Section 2: Filter the List View  

  ๋ฆฌ์คํธ ๋ทฐ๋ฅผ ์ปค์คํฐ๋ง์ด์งํ์ฌ ๋ชจ๋  ์์ดํ์ด ๋ณด์ด๊ฒ ํ๊ฑฐ๋, Favorite ์์ดํ๋ง ๋ณด์ด๋๋ก ํ  ์ ์์ต๋๋ค. ์ด๊ฒ์ ํ๊ธฐ ์ํด, LandmarkList ํ์์ state๋ฅผ ์ถ๊ฐํด์ผ ํฉ๋๋ค.  

  _State_ ๋ ์๊ฐ์ด ์ง๋จ์ ๋ฐ๋ผ ๋ณํ  ์ ์๋ ๊ฐ ๋๋ ๊ฐ๋ค์ ๋ชจ์์๋๋ค. ๋ทฐ์ behavior๋ ์ปจํ์ธ  ๋๋ ๋ ์ด์์์ ์ํฅ์ ๋ฏธ์นฉ๋๋ค. ํ๋์ ๋ทฐ์ state๋ฅผ ์ถ๊ฐํ๊ธฐ ์ํด @State ์ดํธ๋ฆฌ๋ทฐํธ๋ฅผ ์์ฑ ์์ ์์ฑํด์ค๋๋ค.

#### filter(_:)  

  ```swift
  let cast = ["Vivien", "Marlon", "Kim", "Karl"]
  let shortNames = cast.filter { $0.count < 5 }
  print(shortNames)
  // Prints ["Kim", "Karl"]
  ```  

  cast๋ผ๋ ๋ฐฐ์ด์ด ์์ต๋๋ค. filter ๋ฉ์๋๋ฅผ ์ฌ์ฉํ์ฌ ๊ธฐ์กด ๋ฐฐ์ด์์ ๊ธ์์๊ฐ ๋ค์ฏ์ ์ดํ์ธ ๋จ์ด๋ง์ผ๋ก ์๋ก์ด ๋ฐฐ์ด์ ์์ฑํฉ๋๋ค. ์๋กญ๊ฒ ์์ฑ๋ ๋ฐฐ์ด์ shortNames ์์์ ํ ๋นํด์ค๋๋ค. $0์ด cast์ ์์๋ผ๋ ๊ฒ์ ์ ์ ์์ต๋๋ค.

  ```swift
  var filteredLandmarks: [Landmark] {
  //        landmarks.filter { landmark in
  //            (!showFavoritesOnly || landmark.isFavorite)
  //        }
      landmarks.filter { $0.isFavorite == true }
  }
  ```  

  ์ฃผ์์ฒ๋ฆฌ ํ ๋ถ๋ถ์ด ์๋ ํํ ๋ฆฌ์ผ์ filter ๋ฉ์๋ ์ฝ๋์ด๊ณ , ์ฃผ์์ฒ๋ฆฌ ๋์ง ์์ ์ฝ๋๋ ์์ ์์๋ฅผ ๋ณด๊ณ  ๊ฐ์ ๋ฐฉ์์ผ๋ก ๋ง๋ค์ด ๋ณด์์ต๋๋ค. ๋๊ฐ์ด ์๋ํ๋ ๊ฒ์ ์ ์ ์์์ต๋๋ค. (!showFavoritesOnly ๋ถ๋ถ์ ์์ง ์ฝ๋์ ์ํฅ์ ๋ฏธ์น์ง ์์.)

<!-- ```swift
var body: some View {
  Map(coordinateRegion: $region)
}
``` -->

<!-- $region Binding -->
<!-- Generic Structure -->
