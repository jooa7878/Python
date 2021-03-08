# Python

## 문법

#### 리스트
###### 리스트 컴프리헨션
+ 리스트를 초기화하는 방법 중 하나
    
```
   example
   array = [ i for i in range(20) if i % 2 == 1]
```
  
 + 변수를 사용하지 않는 경우 _를 이용하여 무시할 수 있다.


###### 리스트 관련 기타 메서드

```  
    append()
    sort()
    sort(reverse = True)
    reverse()
    insert(idx)
    count(value)
    remove(value)
```

+ remove와 insert는 시간복잡도가 O(N)이라는 점 유의
    + 특정 값 원소 모두 제거하려면 remove_set 사용법을 이용하자.

--------

#### 튜플 자료형
+ 리스트와 비슷하지만 튜플은 한 번 선언된 값을 변경할 수 없고, 소괄호를 이용한다는 차이점이 있다.
    +그래프 알고리즘을 구현할 때 자주 사용
   
--------

#### 사전 자료형
+ Key와 Value 값의 쌍을 데이터로 가지는 자료형, 내부적으로 Hash Table 이용

```
    관련 함수 예제
        data = dict()
        data['사과'] = 'Apple'
        data['바나나'] = 'Banana'
        data['코코넛'] = 'Coconut'
        
        key_list = data.keys() # '사과', '바나나', '코코넛'
        value_list = data.values() # Apple, Banana, Coconut
```

-------

#### 집합 자료형
+ 중복을 허용하지 않으며 순서가 없다. 특정 원소의 존재 유무 검사하는 시간 복잡도 O(1)
+ set() 함수를 이용하거나 {}를 이용하여 초기화가 가능하다.

```
    example
    a = set([1,2,3,4,5])
    b = set([3,4,5,6,7])
    
    print(a|b) # 합집합
    print(a&b) # 교집합
    print(a-b) # 차집합
    
    add(), update(), remove() # add, remove 함수 시간 복잡도 O(1)
    
```

-------

#### 조건문

```
  # exapmple 1
  x = 15
  if x >= 10 :
    print(x)
    
 # example 2
 if 조건문 1 :
    ~~
 elif 조건문 2:
    ~~
 else:
    ~~
    
```

+ 논리 연산자로는 and, or, not이 있다.
+ 기타 연산자로 in 연산자, not in 연산자를 제공
+ 조건부 표현식
    + result = "Success" if score > 80 else "Fail"

------

#### 반복문

###### while

```
  i = 1
  result = 0
  
  while i <= 9:
    result += i
    i+=1
    
  print(result)
```

###### for

```
  for 변수 in 리스트
    실행할 소스코드
    
  result = 0
  
  for i in range(1,10):
      result += i
      
  print(result)
````

-------

#### 함수

``` 
    # 기초
    def add(a,b):
        return a + b
        
    print(add(3,7))
    
    # 람다식 사용
    
    print((lambda a, b : a + b)(3,7))
    
    # 전역변수를 사용하는 경우
    
    a = 0
    
    def func():
        global a
        a += 1
        
    for i in range(10)
        func()
        
    print(a)
```
        
------

#### 입출력

```
    # 입력을 위한 전형적인 소스코드
    n = int(input())
    # 각 데이터를 공백으로 구분하여 입력
    data = list(map(int, input().split()))
    
    data.sort(reverse = True)
    print(data)
    
    # n, m, k를 공백으로 구분하여 입력
    n, m, k = map(int.input().split())
    
    print(n, m, k)
```

+ input() 함수는 동작 속도가 느려서 sys.stdin.readline() 함수를 이용한다.
    + import sys
    + sys.stdin.readline().rstrip()

+ 출력에서 문자열과 정수를 같이 출력하고 싶다면
    + print( "정답은" + str(answer) + "입니다.") # + 대신 , 가능

-------

#### 주요 라이브러리

```

    내장 함수 : print(), input()과 같은 입출력부터 sorted() 까지 필수적인 기능을 포함하고 있는 내장 라이브러리
    itertools : 반복되는 형태의 데이터를 처리하는 기능을 제공, 순열과 조합 라이브러리 제공
    heapq : 힙 기능을 제공하는 라이브러리, 우선순위큐(pq)를 구현하기 위해 사용
    bisect : 이진탐색(Binary Search) 기능을 제공
    collections : 덱(deque), 카운터(Counter) 등의 유용한 자료구조를 포함하고 있는 라이브러리
    
```

###### 내장함수
+ eval() 함수는 수학 수식이 문자열 형식으로 들어오면 해당 수식을 계산한 결과를 반환한다.
    + result = eval("(3+5) * 7")

###### itertools
+ permutations, combinations, product 클래스 유용하게 사용

```
    from itertools import permutations
    from itertools import combinations
    from itertools import product
    from itertools import combinations_with_replacement
    
    data = ['A', 'B', 'C']
    result1 = list(permutations(data,3))
    result2 = list(combinations(data,2))
    result3 = list(product(data, repeat =2))
    result4 = list(combinations_with_replacement(data,2))
    
    print(result1)
    print(result2)
    print(result3)
    print(result4)
    
```

###### heapq
+ PriorityQueue보다 보통 빠르게 동작
+ heappush(), heappop() 이용

```
    import heapq
    
    def heapsort(iterable):
        h = []
        result = []
        # 모든 원소를 차례대로 힙에 삽입
        for value in iterable
            heapq.heappush(h, value)
        for i in range(len(h))
            result.append(heapq.heappop(h))
        return result
        
    result = heapsort([1,3,5,7,9,2,4,6,8,0])
    print(result)
```

###### bisect
+ 정렬된 배열에서 특정한 원소를 찾아야할 때 사용하는 이진 탐색
+ bisect_left(a,x) 와 bisect_right(a,x)가 가장 중요하게 사용

```
    from bisect import bisect_left, bisect_right
    
    a = [1,2,4,4,8]
    x = 4
    
    print(bisect_left(a,x))
    print(bisect_right(a,x))
    
    # count_by_range 함수
    
    def count_by_range(a, left_value, right_value):
        right_index = bisect_right(a, right_value)
        left_index = bisect_left(a, left_value)
        return right_index - left_index
        
    a = [1, 2, 3, 3, 3, 3, 4, 4, 8, 9]
    
    print(count_by_range(a, 4, 4))
    
    print(count_by_range(a, -1, 3))
```

###### collections
+ deque를 많이 사용하는데, popleft()는 첫 원소 제거, pop()은 마지막, appendleft(x)는 첫 원소 삽입, append(x)는 끝 원소 삽입
+ Counter는 등장 횟수를 세는 기능


```
    # Counter 사용 예시
    from collections import Counter
    
    counter = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])
    
    print(counter['blue'])
    print(counter['green'])
    print(dict(counter))
```

###### math

```
    # factorial, sqrt, gcd, pi, e
    import math
    
    print(math.factorial(5))
    print(math.sqrt(7))
    print(math.gcd(14,21))
    print(math.pi)
    print(math.e)
```
    


    

    

