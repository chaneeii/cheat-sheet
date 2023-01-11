
## Dictionary 정렬하기

```swift
var dic = [5:4, 4:1, 3:2]
// print(dic.sorted()) // => error 
```

### Key로 정렬

```swift
dic.sorted { (first, second) in return first.key > second.key }

dic.sorted{ $0.key < $1.key } // 작은수부터 정렬
dic.sorted { $0.0 > $1.0 } // 큰수대로 정렬
```

### Value로 정렬

```swift
dic.sorted { (first, second) in return first.value > second.value }

dic.sorted{$0.value < $1.value} 
dic.sorted { $0.1 > $1.1 }
```

### Value로 정렬 후 Key만 출력하고자 하는 경우

```swift
dic.sorted{$0.value < $1.value}.map{$0.key} // 만약 value로 정렬후 key만 출력하고 싶으면 이런식으로
```

### Value를 기준으로 정렬하는데 그 값이 같은 경우 Key를 기준으로 정렬 
- if-else 활용하기

```swift
let dict: [Int: Int] = [1: 10, 2: 10, 3: 30, 4: 40]

// 방법1
dict.sorted { (first, second) in
              if first.value == second.value {
                  return first.key > second.key
              }
              return first.value < second.value }

// 방법2
dict.sorted {
              if $0.1 == $1.1 {
                  return $0.0 > $1.0
              }
              return $0.1 < $1.1 }
```



### ref
- [천원의 개발](https://1000one.tistory.com/category/Swift%20%EC%BD%94%EB%94%A9%ED%85%8C%EC%8A%A4%ED%8A%B8%20%EC%A4%80%EB%B9%84?page=1)
- [SeriOSly](https://2unbini.github.io/%F0%9F%93%82%20all/swift/dictionary-sorted/)
