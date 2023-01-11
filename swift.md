## 고차함수 (map, filter, reduce)

- `map` : for문이랑 비슷하지만 훨씬 간결하게 사용이 가능하다

```swift
let numArray = [1,2,3,4,5]
var multiArray = [Int]()
for num in numArray {
    multiArray.append(num * 2)
}
print(multiArray)  // [2,4,6,8,10]
```
을 아래와 같이 간단하게 바꿀 수 있다.

```swift
let numArray = [1,3,5,7,9]
var multiArray = numArray.Map{$0 * 2} // [2,4,6,8,10]
```

<br/>

- `filter` : for 문에 if절이 있을때 간결하게 사용하기 위해서 사용 조건식이 true인 요소들로만 구성된다.

```swift
let stringArray = ["가수", "대통령", "개발자", "선생님", "의사", "검사", "건물주"]
var threeCountArray = [String]()
for st in stringArray {
    if st.count == 3 {
        threeCountArray.append(st)
    }
}
print(threeCountArray) // ["대통령", "개발자", "선생님", "건물주"]
```

을 filter로

```swift
let stringArray = ["가수", "대통령", "개발자", "선생님", "의사", "검사", "건물주"]
var threeCountArray = stringArray.filter{$0.count = 3} // ["대통령", "개발자", "선생님", "건물주"]
```

<br/>

- `reduce`: 데이터를 합쳐주기 위해서 사용

```swift
/for in
let numberArray = [1,2,3,4,5,6,7,8,9,10]
var sum = 0
for number in numberArray {
    sum += number
}
print(sum) // 55
```
를 아래와 같이 축약!
```swift
//reduce
let numberArray = [1,2,3,4,5,6,7,8,9,10]
var sum = numberArray.reduce(0){$0 + $1} // 55
```

## Dictionary 정렬하기

```swift
var dic = [5:4, 4:1, 3:2]
// print(dic.sorted()) // => error 
```

- Key로 정렬

```swift
dic.sorted { (first, second) in return first.key > second.key }

dic.sorted{ $0.key < $1.key } // 작은수부터 정렬
dic.sorted { $0.0 > $1.0 } // 큰수대로 정렬
```

- Value로 정렬

```swift
dic.sorted { (first, second) in return first.value > second.value }

dic.sorted{$0.value < $1.value} 
dic.sorted { $0.1 > $1.1 }
```

- Value로 정렬 후 Key만 출력하고자 하는 경우

```swift
dic.sorted{$0.value < $1.value}.map{$0.key} // 만약 value로 정렬후 key만 출력하고 싶으면 이런식으로
```

- Value를 기준으로 정렬하는데 그 값이 같은 경우 Key를 기준으로 정렬 
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
