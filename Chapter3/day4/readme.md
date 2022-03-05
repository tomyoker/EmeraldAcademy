1. Explain, in your own words, the 2 things resource interfaces can be used for (we went over both in today's content)

    구현해야할 요구사항을 지정할수있음 / 특정한 사람에게 특정한 내용만 노출시킬수 있게 지정할수 있음 
    



2. Define your own contract. Make your own resource interface and a resource that implements the interface. Create 2 functions. In the 1st function, show an example of not restricting the type of the resource and accessing its content. In the 2nd function, show an example of restricting the type of the resource and NOT being able to access its content.

    ![1](https://user-images.githubusercontent.com/41810744/156872557-d0fe261f-17d2-488d-8e89-cadd97a3f84f.png)

    https://play.onflow.org/dd20ca4c-b5fb-43bd-801e-93c95d32a6ea?type=account&id=66e6633c-0a39-4193-852e-94bae1a01e3e&storage=none




3. How would we fix this code?

```swift
pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
    }

    // ERROR:
    // `structure Stuff.Test does not conform 
    // to structure interface Stuff.ITest`
    pub struct Test: ITest {
      pub var greeting: String

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting // returns the new greeting
      }

      init() {
        self.greeting = "Hello!"
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") // ERROR HERE: `member of restricted type is not accessible: changeGreeting`
      log(newGreeting)
    }
}

```




```swift
pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
      pub fun changeGreeting(newGreeting: String): String // put the function definition
    }

   
    pub struct Test: ITest {
      pub var greeting: String
      pub var favouriteFruit: String // define the things in the interface

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting 
      }

      init() {
        self.greeting = "Hello!"
        self.favouriteFruit = "Apple" // Add
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") 
      log(newGreeting)
    }
}

```
