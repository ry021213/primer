# Where is number?
이 프로그램은 python으로 구현한 숫자찾기게임입니다.

## 프로그램 설명
1부터 100까지의 숫자 중 10개의 숫자가 나열되어 있을 때 주어진 숫자가 있을 위치를 추측하여 찾는 게임입니다.


user의 name은 영어로 받아 list에 없다면 list에 추가함과 동시에 dic에 user의 name을 key로 하여 value값에 1000coin을 넣습니다.
user_name이 list에 존재한다면 숫자 위치 비교 함수와 결과함수를 연달아 실행합니다.
user중 한명의 coin이 0이 되어도 프로그램은 종료됩니다.
user name에 q 또는 Q를 입력 시 프로그램은 종료됩니다.
종료 후 재접속 시 모든 데이터는 초기화됩니다.

## 함수(이진탐색, 선택정렬, 숫자위치 비교, 결과)
### 숫자 위치 비교 함수 - result()
1부터 100까지 숫자 중 10개를 중복되지 않게 뽑습니다.
무작위로 나열된 숫자 중 4번째에 위치하는 숫자를 이용자가 찾을 숫자(find_num)로 선정합니다. 
이후 **선택정렬**을 사용하여 무작위로 나열된 숫자들을 오름차순으로 정렬합니다.
정렬된 list에서 **이진탐색**을 사용하여 find_num이 위치한 번호(real_loc)를 찾아줍니다.
이용자가 선택한 위치와 real_loc이 같다면 '일치'를, 같지 않다면 '불일치'와 real_loc을 return해줍니다.

### 결과 함수 - final()
return값이 '일치'라면 user의 money에 100coin을 추가시키고, 결과를 print해줍니다. 만일, 아니라면 100coin을 차감하고, 결과를 print해줍니다. 

## 예외처리
1. find_num이 있을 위치를 입력할 때, 1~10이외의 숫자나 다른 문자를 입력 시, '1부터 10까지의 숫자만 입력하세요.'가 출력된 후, 100coin이 차감되고 게임이 지속됩니다.
   이를 try, except, else 구문을 통해 구현하였습니다.
2. user name을 입력할 때, 영어가 아닌 문자나 숫자 등을 입력 시 '영어로 입력해주세요.'가 출력된 후, 다시 user name을 입력받습니다.
   이는 if, elif, else를 사용하여 구현해보았습니다. 다만, isalpha와 upper(),lower()를 사용했는데 한글과 영어가 섞이는 경우는 제외하지 못한 것이 아쉽습니다.

## 느낀점
포인트를 차감하는 방식도 좋지만, 베팅의 방식을 이용해도 좋을 것 같습니다. 여러 이용자에게서 금액을 받아 맞추는 이용자들에게만 그 돈을 나누어 주는 방법입니다.
추가적으로 상,중,하의 단계를 만들어, 상으로 갈수록 선택할 위치가 늘어나는 것도 재미있을 것 같다고 생각했습니다.
아쉬운 점은 coin이 0이 되면 프로그램을 아예 종료하도록 만든 것 입니다. dic에서 user를 삭제 후, user에게 게임이 종료되었다고 안내 후 게임을 계속 진행하는 것이 조금 더 좋지 않을까라는 생각이 듭니다.

프로그램을 만들며 예외구문을 써보고 싶어서 조금 공부 후 코드를 짜봤는데 결과는 원하는대로 나왔지만 제대로 잘 사용한건지 모르겠습니다...
예외구문에 대한 공부는 좀 더 해야할 것 같습니다 :)

## 실행영상

https://user-images.githubusercontent.com/121685926/210158337-b0b34d3b-d10f-48cd-8560-178dd7383d8d.mp4

