
### 프로그래머스 [LV.0] 배열 만들기 2

> 정수 l과 r이 주어졌을 때, l 이상 r이하의 정수 중에서 숫자 "0"과 "5"로만 이루어진 모든 정수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.
만약 그러한 정수가 없다면, -1이 담긴 배열을 return 합니다.

sol) 정수를 문자열로 변환해서 5,0을 포함하는지 확인

```python
num = 50
number = list(map(int, str(num)))
print(number)

for i in range(len(number)):
  if number[i] == 5:
    if number[i+1] == 0:
      print(number)
    elif number[i+1] == 5:
      print(number)
```

출력 결과
```python
[5,0]
[5,0]
```
