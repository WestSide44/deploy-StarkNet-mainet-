## deploy смарт контракта StarkNet (mainnet) 


Ubuntu 22.04


Активированный кошелек (с наличием транзакций в мейннете) + ~0.0005 на газ


  
  ```
  curl -L https://raw.githubusercontent.com/software-mansion/protostar/master/install.sh | bash  
  ```

  
  ```
  source /root/.bashrc
  ```
  
  
  ```
  apt update 
  ```
  
  
  ```
  protostar init  
  ```
  
  
  В появившейся строке вводим любое название проекта
  
  
  
  ```
  cd <название вашего проекта>
  ```
   
  
  ```
  protostar build
  ```
  
  
  ```
  echo "<здесь вставляем private key от кошелька, не путать с recovery phrase>" > .env
  ```
  
  
  ```
  protostar declare ./build/main.json --account-address <адрес кошелька>  --max-fee auto --private-key-path ./.env --network mainnet
  ```
  
 
 Появляется результат в виде хэшей, они нам пригодятся.
Открываем транзу по transaction hash на [starkscan](https://starkscan.co/) и ждём когда статус перейдет в Accepted on L2, после этого деплоим:

  
  ```
  protostar deploy <здесь вставляем class hash> --account-address <адрес кошелька>  --max-fee auto --private-key-path ./.env --network mainnet
  ```


Снова появляются хэши.
Отслеживаем транзу на [starkscan](https://starkscan.co/) , проверяем contract address


The End

