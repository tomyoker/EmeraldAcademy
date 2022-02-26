1.Explain why we wouldn't call changeGreeting in a script.
  
   스크립트는 블록체인의 데이터를 수정할수 없기때문
   

2.What does the AuthAccount mean in the prepare phase of the transaction?

  "이 거래를 승인하겠습니다" 라는 버튼을 클릭했다는 의미
  

3.What is the difference between the prepare phase and the execute phase in the transaction?

  prepare 단계는 계정의 정보와 데이터에 엑세스하는 단계이고 
  execute 단계는 함수를 호출하고 블록체인의 데이터를 변경하는 작업을 수행하는 단계
  
 


Add two new things inside your contract:

  -A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
  -A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber
  
  ![deploy](https://user-images.githubusercontent.com/41810744/155829678-94fede15-11d2-45f2-9cd7-7f3807f7b549.png)


Add a script that reads myNumber from the contract

  ![read](https://user-images.githubusercontent.com/41810744/155829691-a4f2f6bb-d430-49c7-aaae-7ae1bcc43c72.png)


Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.

  ![transaction](https://user-images.githubusercontent.com/41810744/155829700-6bd3f03b-9db6-4541-9187-55866bcc26e7.png)
  
  ![result](https://user-images.githubusercontent.com/41810744/155829705-fe015bf9-ba74-4c28-b3dd-f6e7aeb463c9.png)


