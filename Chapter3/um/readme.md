

```swift

pub contract Test {

    pub var dictionaryOfGreetings: @{String: Greeting}

    pub resource Greeting {
        pub let message: String
        init() {
            self.message = "Hello, Mars!"
        }
    }

    pub fun addGreeting(greeting: @Greeting) { // greeting 매개변수를 Greeting 리소스 타입으로 정의 했으므로
        let key = greeting.message  //  greeting 은 Greeting 리소스의 멤버를 갖게됨 구조체도 마찬가지임 
        self.dictionaryOfGreetings[key] <-! greeting // greeting 매개변수를 구조체 '이름' 타입으로 정의했으면 그 구조체에 있는 멤버를 가지게됨 
    }                                                // 이전과제에서 했던 Wallet 구조체를 예를 들면 greeting : Wallet 시 
                                                     // greeting 은 btc, eth, flow, account 멤버를 갖게됨 따라서 greeting.btc 같은 표현이 

    init() {
        self.dictionaryOfGreetings <- {}
    }

}

```
