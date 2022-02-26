

1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

  ![1](https://user-images.githubusercontent.com/41810744/155834107-92984d7a-712f-4b0c-9814-afa0cfc27494.png)
  
2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

  ![2](https://user-images.githubusercontent.com/41810744/155834127-3d3ad1c1-e6eb-4a68-9764-8ac47762464e.png) 

3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).


  <img width="841" alt="img" src="https://user-images.githubusercontent.com/41810744/155834818-dc300ed8-09f2-495e-89a4-ddd691509597.png">


  Optional Unwrapping 의 여러가지 방법중 한가지
  
  값이 nil이든 아니든 강제로 Optional Type 을 제거하는 연산자임 
  
  그러나 nil 일경우 에러가 뜨거나 프로그램이 중단됨 
  
  
  ![3](https://user-images.githubusercontent.com/41810744/155835380-1771be10-7004-42f5-9fda-f15c57542acd.png)


  nil 이 지정된 변수를 Unwrapping 하면 안된다.
  
  



4. Using this picture below, explain...

![image](https://user-images.githubusercontent.com/41810744/155834282-12516b69-981f-47b3-a01c-effca0ff6f3e.png)


 - What the error message means
    
    String Type 이 아닌 Optional String Type 이 반환되었다는 뜻
  
 
 - Why we're getting this error

    우리가 dictionary 에 접근하면 값이 Optional Type 으로 반환되기 때문임
    Optional Type의 자료형을 사용하기 위해선 Optional 이란 포장지를 Unwrapping 해줘야함 
    
    
 - How to fix it

    0x03 은 nil 이 아니기 때문에 Force-Unwrap Operator 를 사용하여 Optional Type을 제거하면됨 

    ![4](https://user-images.githubusercontent.com/41810744/155834609-15df3cb4-98aa-475f-920d-909cbfd89825.png)

