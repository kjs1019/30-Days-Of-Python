<div align="center">
  <h1> 30 Days Of Python: Day 6 - Tuples</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Second Edition: July, 2021</small>
</sub>

</div>

[<< Day 5](../05_Day_Lists/05_lists.md) | [Day 7 >>](../07_Day_Sets/07_sets.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [6일차](#6일차)
  - [튜플](#튜플)
    - [튜플 만들기](#튜플-만들기)
    - [튜플 길이](#튜플-길이)
    - [튜플 항목 액세스](#튜플-항목-액세스)
    - [튜플 슬라이싱](#튜플-슬라이싱)
    - [튜플을 목록으로 변경](#튜플을-목록으로-변경)
    - [튜플에서 항목 확인](#튜플에서-항목-확인)
    - [튜플 결합](#튜플-결합)
    - [튜플 삭제](#튜플-삭제)
  - [💻 실습: 6일차](#실습:-6일차)
    - [실습: 레벨 1](#실습-레벨-1)
    - [실습: 레벨 2](#실습-레벨-2)

# 6일차:

## 튜플

튜플은 순서가 정해져 있고 변경할 수 없는 다양한 데이터 유형의 모음입니다. 튜플은 둥근 대괄호()를 사용합니다. 튜플이 생성되면 해당 값을 변경할 수 없습니다. 추가, 삽입, 제거 메서드는 수정할 수 없기 때문에 튜플에서 사용할 수 없습니다. 리스트와 달리 튜플은 메소드가 거의 없습니다. 튜플과 관련된 방법:
- 튜플(): 빈 튜플을 생성하려면
- 카운트(): 튜플에서 지정된 항목의 수를 셉니다.
- 인덱스: 튜플에서 지정된 항목의 인덱스를 찾으려면
- + 연산자: 두 개 이상의 튜플을 결합하고 새 튜플을 만듭니다.
### 튜플-만들기

- 빈 튜플: 빈 튜플 만들기
  
  ```py
  # syntax
  empty_tuple = ()
  # or using the tuple constructor
  empty_tuple = tuple()
  ```

- 튜플 초기화
  
  ```py
  # syntax
  tpl = ('item1', 'item2','item3')
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  ```

### 튜플-길이

튜플의 길이를 얻기 위해  _len()_ 메소드를 사용합니다.

```py
# syntax
tpl = ('item1', 'item2', 'item3')
len(tpl)
```

### 튜플-항목-액세스

- 양의 인덱싱
목록 데이터 유형과 유사하게 우리는 양수 또는 음수 인덱싱을 사용하여 튜플 항목에 액세스합니다.
![튜플 항목 액세스 중](../images/tupples_index.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3')
  first_item = tpl[0]
  second_item = tpl[1]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[0]
  second_fruit = fruits[1]
  last_index =len(fruits) - 1
  last_fruit = fruits[las_index]
  ```

- 음수 인덱싱
음수 인덱싱은 끝에서 시작하는 것을 의미하며, -1은 마지막 항목을, -2는 두 번째 마지막 항목을 의미하며, 음수는 목록/튜플 길이의 첫 번째 항목을 의미합니다.
![Tuple Negative 인덱싱](../images/tuple_negative_indexing.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  first_item = tpl[-4]
  second_item = tpl[-3]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[-4]
  second_fruit = fruits[-3]
  last_fruit = fruits[-1]
  ```

### 튜플-슬라이싱

튜플에서 시작할 인덱스와 종료할 인덱스 범위를 지정하여 하위 튜플을 잘라낼 수 있습니다. 반환 값은 지정된 항목이 있는 새 튜플이 됩니다.
- 양의 인덱스 범위

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[0:4]         # all items
  all_items = tpl[0:]         # all items
  middle_two_items = tpl[1:3]  # does not include item at index 3
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[0:4]    # all items
  all_fruits= fruits[0:]      # all items
  orange_mango = fruits[1:3]  # doesn't include item at index 3
  orange_to_the_rest = fruits[1:]
  ```

- 음의 인덱싱 범위

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[-4:]         # all items
  middle_two_items = tpl[-3:-1]  # does not include item at index 3 (-1)
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[-4:]    # all items
  orange_mango = fruits[-3:-1]  # doesn't include item at index 3
  orange_to_the_rest = fruits[-3:]
  ```

### 튜플을-목록으로-변경

우리는 tuple을 list로, list를 tuple로 바꿀 수 있습니다. 우리가 튜플을 수정하고 싶다면 우리는 그것을 리스트로 바꿔야 합니다.
```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
lst = list(tpl)
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
fruits = list(fruits)
fruits[0] = 'apple'
print(fruits)     # ['apple', 'orange', 'mango', 'lemon']
fruits = tuple(fruits)
print(fruits)     # ('apple', 'orange', 'mango', 'lemon')
```

### 튜플에서-항목-확인
우리는 _in_ 을 사용하여 항목이 튜플에 존재하는지 여부를 확인할 수 있으며, 그것은 부울을 반환합니다.

```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
'item2' in tpl # True
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
print('orange' in fruits) # True
print('apple' in fruits) # False
fruits[0] = 'apple' # TypeError: 'tuple' object does not support item assignment
```

### 튜플-결합

+ 연산자를 사용하여 두 개 이상의 튜플을 결합할 수 있습니다.
```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
tpl2 = ('item4', 'item5','item6')
tpl3 = tpl1 + tpl2
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
vegetables = ('Tomato', 'Potato', 'Cabbage','Onion', 'Carrot')
fruits_and_vegetables = fruits + vegetables
```

### 튜플-삭제

튜플에서 단일 항목을 제거할 수 없지만 _del_ 을 사용하여 튜플 자체를 삭제할 수 있습니다.

```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
del tpl1

```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
del fruits
```

🌕 당신은 정말 용감해요, 여기까지 왔군요. 여러분은 이제 막 6일차의 도전을 마쳤고 위대함을 향한 6단계 앞으로 나아갑니다. 이제 여러분의 뇌와 근육을 위한 운동을 하세요.
## 💻 실습: 6일차

### 실습: 레벨 1

1. 빈 튜플을 만듭니다
2. 언니들과 오빠들의 이름이 들어있는 튜플을 만드세요 (상상속의 형제들도 괜찮다)
3. 형제자매를 튜플에 할당합니다
4. 형제가 몇 명입니까?
5. 형제 튜플을 수정하고 아버지와 어머니의 이름을 추가하여 family_members에게 할당합니다.

### 실습: 레벨 2

1. family_members로부터 형제자매와 부모를 분석합니다
2. 과일, 채소, 동물 제품 튜플을 만듭니다. 세 개의 튜플을 결합하고 food_stuff_tp라는 변수에 할당합니다.
3. about food_stuff_tp tuple을 food_stuff_lt 목록으로 변경합니다.
4. food_stuff_tp tuple 또는 food_stuff_lt 목록에서 중간 항목을 잘라냅니다.
5. food_staff_list에서 처음 3개의 항목과 마지막 3개의 항목을 잘라냅니다.
6. food_staff_tp tuple을 완전히 삭제합니다.
7. 항목이 튜플에 있는지 확인합니다

- '에스토니아'가 북유럽 국가인지 확인하세요.
- '아이슬란드'가 북유럽 국가인지 확인하세요.

  ```py
  nordic_countries = ('Denmark', 'Finland','Iceland', 'Norway', 'Sweden')
  ```


[<< Day 5](../05_Day_Lists/05_lists.md) | [Day 7 >>](../07_Day_Sets/07_sets.md)
