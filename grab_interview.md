## Round 1 - Algorithm    
`using online pair programming tool`: [https://codeinterview.io/RRZAEHAMGE](https://codeinterview.io/RRZAEHAMGE)
### Task 1   

- Given an array of strings, return the array without duplicates  
  `Input: [“abc”, “bcd”, “abc”, “def”, “bcd”]`    
  `Output: [“abc”, “bcd”, “def”] // relative order of elements should be maintained`    

```
func unify(array: [String]) -> [String] {
  var resultArray = []
  array.forEach { string in
    if !resultArray.contains(string) {
      resultArray.append(string)
    }
  }

  return resultArray
}
```

### TASK 2   

- Merge 2 sorted arrays and return a single sorted array (ascending order)    

`for example`
`Input: [1,5,7,20] and [2,4,10]`    
`Output: [1,2,4,5,7,10,20]`    

```
func merge(firstSorted: [Int], secondSorted: [Int]) -> [Int] {
  guard !firstSorted.isEmpty else {return secondSorted}

  guard !secondSorted.isEmpty else {return firstSorted}

  var resultSorted = []

  var itemInFirstArray: Int = 0
  var firstIndex = 0
  var itemInSecondArray Int = 0
  var secondIndex = 0

  while firstIndex < firstSorted.count && secondIndex < secondSorted.count {
    itemInFirstArray = firstSorted[firstIndex]
    itemInSecondArray = secondSorted[secondIndex]

if itemInFirstArray < itemInSecondArray {
  resultArray.append(itemInFirstArray)
  firstIndex += 1
   
} else if itemInFirstArray > itemInSecondArray {
  resultArray.append(itemInSecondArray)
  secondIndex += 1
} else {
  resultArray.append(itemInFirstArray)
  resultArray.append(itemInSecondArray)
  firstIndex += 1
  secondIndex += 1
}

  }

  if firstIndex < firstSorted.count {
      resultArray.append(contentsOf: firstSorted[firstIndex...])
  }

  if secondIndex < secondSorted.count {
    resultArray.append(contentsOf: secondSorted[secondIndex...])
  }

  return resultArray
}

```

### TASK 3

- Return all permutations of an array of integers    
  `Input: [1, 2, 3]`    
  `Output: [[Int]]`    

## Round 2
`using google doc share`

* Implement block based NotificationCenter, it should work just like NSNotificationCenter    
`Interfaces:`    
```
typealias Observer = (_ name: String, _ data: Any) -> Void
func addObserver(forName name: String, usingBlock block: Observer)
func removeObserver(forName name: String)
```
* if a button on a view controller, how can you notify view controller, you have tapped the button? what design patterns you will use?    

* what is the difference between `objective-c` and `swift`?   
1. objective-c is more dynamic, has many runtime features, swift is less dynamic   
2. objective-c is no so strict about type, swift is strict   
3. swift has optional, objective-c does not   

* what is the difference between `class` and `struct`?
1.`class` is reference type, `struct` is value type
2.`class` can mutate member, `struct` need add `mutating`
3.`class` can be derived, `struct` can not, `struct` can only be extend using `extension`
* is function value type or reference type? `reference type`
* is closure value type or reference type? `reference type`
* is enum value type or reference type? `value type`
* is collection classes value type or reference type? `reference type`

* have you been using RxSwift?   
* why RXSwift is good for MVVM?     
* what is lazy collection?

## R3    

// Design interfaces for a cache system. The cache system should have different level of cache: memory cache, disk cache.    
```
protocol CacheMananger {
    init(_ config: CacheConfig)
    func cache<T>(object: T, forKey: String, cachPolicy: CachePolicy) where T : Decodable, T : Encodable
    func load<T>(type: T.Type, forKey: String) -> T? where T : Decodable, T : Encodable
}

protocol CacheConfig {
    var memroySize: Int {get}
    var diskSize: Int {get}
}

enum CachePolicy {
    case memory
    case disk
}

class MyCacheManager: CacheMananger {
    required init(_ config: CacheConfig) {
    }
    
    func cache<T>(object: T, forKey: String, cachPolicy: CachePolicy) where T : Decodable, T : Encodable {
        if cachPolicy == .disk {
            if let data = try? JSONEncoder().encode(object) {
                UserDefaults.standard.set(data, forKey: forKey)
            }
        } else {
            // cache in memory
        }
    }
    
    func load<T>(type: T.Type, forKey: String) -> T? where T : Decodable, T : Encodable {
        // get data from memory, if not exsists, get from disk
        if let data = UserDefaults.standard.data(forKey: forKey) {
            return try? JSONDecoder().decode(type, from: data)
        }
        
        return nil
    }
    
}
```
