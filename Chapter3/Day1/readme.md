

1. In words, list 3 reasons why structs are different from resources.

    복사되지 않음,
    덮어쓰기가 되지 않음,
    구조체를 다루는것보다 훨씬 어려움


2. Describe a situation where a resource might be better to use than a struct.

      삭제되면 안되는 소중한 자료일경우 구조체를 사용하는것 보다 리소스를 사용하는 것이 더 나음, 
      왜냐하면 리소스는 명시적으로 `destroy` 키워드를 쓰지 않는 이상 삭제되거나 실수로 덮어씌워 지지 않기 때문임


3. What is the keyword to make a new resource?

      `create`
  

4. Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?

      create 키워드는 contract 내에서만 사용할수 있다, 따라서 리소스는 스크립트나 트랜잭션에서 만들어질수 없다.


5. What is the type of the resource below?
 
      `Jacob`
 
```swift
pub resource Jacob {

}
```



 

6. Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.
pub contract Test {


```swift
pub contract Test {

    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): Jacob { // there is 1 here
        let myJacob = Jacob() // there are 2 here
        return myJacob // there is 1 here
    }
}
```





```swift
pub contract Test {

   
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): @Jacob { // 리소스 유형 앞에 @기호를 사용해야함
        let myJacob <- create Jacob() // create 키워드로만 새 리소스를 만들수 있고 리소스는 <- 기호를 사용하여 이동시켜야함
        return <- myJacob // 리소스는 <- 기호를 사용하여 이동시켜야함
    }
}
```
