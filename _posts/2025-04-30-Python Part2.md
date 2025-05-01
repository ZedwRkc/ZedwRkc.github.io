---
title: Part2
date: 2025-04-30
categories: [Python]
tags: [Python]
math: true
---

## 프로그래밍 용어
 
이 과정의 첫 부분에서는 용어에 크게 신경 쓰지 않았으므로, 프로그래밍의 몇 가지 핵심 개념을 살펴보겠습니다.
 
### 문
_문_ 은 무언가를 실행하는 프로그램의 일부입니다. 항상 그런 것은 아니지만, 종종 단일 명령을 나타냅니다.
 
예를 들어, `print("Hi!")`는 텍스트 한 줄을 출력하는 문입니다. 마찬가지로, `number = 2`는 변수에 값을 할당하는 문입니다.
 
문은 더 복잡할 수도 있습니다. 예를 들어, 다른 문을 포함할 수 있습니다. 다음 문은 세 줄에 걸쳐 있습니다:

```py
if name == "Anna":
    print("Hi!")
    number = 2
```

위의 경우 조건문 안에 두 개의 문장 (출력문과 할당문)이 있습니다.

### 블록
_블록_ 은 프로그램 구조에서 동일한 수준에 있는 연속된 문장들의 그룹입니다. 예를 들어, 조건문의 블록은 조건이 참일 경우에만 실행되는 문장들을 포함합니다.
 
파이썬에서는 블록 내의 모든 코드를 동일한 양의 공백으로 들여쓰기하여 블록을 표현합니다.
 
주의: 파이썬 프로그램의 메인 블록은 항상 들여쓰기 없이 파일의 가장 왼쪽 가장자리에 있어야 합니다:

```py
if age > 17:
    # beginning of the conditional block
    print("You are of age!")
    age = age + 1
    print("You are now one year older...")
    # end of the conditional block

print("This here belongs to another block")
```
파이썬에서는 블록 안의 모든 코드를 동일한 양의 공백으로 들여쓰는 것으로 블록을 표현합니다.
 
주의: 파이썬 프로그램의 메인 블록은 항상 들여쓰기 없이 파일의 가장 왼쪽 가장자리에 있어야 합니다:
```py
# this program will not work because it is not written at the leftmost egde of the file
  print("hello world")
  print("this program is not very good...")
```

### 표현식
_표현식_ 은 결정된 데이터 타입으로 귀결되는 약간의 코드입니다. 프로그램이 실행될 때, 표현식은 평가되어 프로그램에서 그 다음에 사용될 수 있는 값을 갖게 됩니다.
 
다음은 표현식의 몇 가지 예입니다:

|Expression	|Value	|Type	|Python data type
|---|---|---|---|---|
|`2 + 4 + 3	`|`9`	|integer	|`int`
|`"abc" + "de"`	|`"abcde"`	|string	|`str`
|`11 / 2`	|`5.5`	|floating point number	|`float`
|`2 * 5 > 9`	|`True`	|Boolean value	|`bool`

모든 표현식은 타입을 가지기 때문에, 변수에 할당될 수 있습니다:

```py
# the variable x is assigned the value of the expression 1 + 2
x = 1 + 2
```
단순한 표현식은 함께 조합되어 더 복잡한 표현식을 형성할 수 있습니다, 예를 들어 산술 연산으로:

```py
# the variable y is assigned the value of the expression '3 times x plus x squared'
y = 3 * x + x**2
```

### 함수
_함수_는 어떤 기능을 실행합니다. 함수는 또한 하나 이상의 인수를 받을 수 있으며, 이는 함수에 공급되어 처리될 수 있는 데이터입니다. 인수는 때때로 _매개변수_라고도 합니다. 인수와 매개변수 사이에는 기술적인 구분이 있지만, 이 단어들은 종종 혼용되어 사용됩니다. 지금으로서는 두 용어 모두 함수에 전달되는 일부 데이터라는 개념을 가리킨다는 것을 기억하는 것으로 충분합니다.
 
함수는 호출될 때 실행됩니다. 즉, 함수(및 인수가 있는 경우 해당 인수)가 코드에서 언급될 때입니다. 다음 문장은 `"this is an argument"`라는 인수를 사용하여 `print` 함수를 호출합니다:

```py
print("this is an argument")
```

당신이 이미 자주 사용한 또 다른 함수는 사용자에게 입력을 요청하는 `input` 함수입니다. 이 함수의 인수는 사용자에게 표시되는 메시지입니다:

```py
name = input("Please type in your name: ")
```

이 경우 함수는 또한 값을 _반환_ 합니다. 함수가 실행된 후, 그것이 호출된 코드 섹션은 그것이 반환하는 값으로 대체됩니다; 그것은 이제 평가된 또 다른 표현식입니다. 함수 `input`은 사용자가 프롬프트에 입력한 무엇이든 포함하는 문자열 값을 반환합니다. 함수가 반환하는 값은 나중에 프로그램에서 사용될 수 있도록 종종 변수에 저장됩니다.

### 데이터 타입
_데이터 타입_ 은 프로그램에 존재하는 값의 특징을 가리킵니다. 다음 코드 조각에서 변수 name의 데이터 타입은 문자열 또는 `str`이며, 변수 `result`의 데이터 타입은 정수 또는 `int`입니다:

```py
name = "Anna"
result = 100
```

`type` 함수를 사용하여 모든 표현식의 데이터 타입을 알아낼 수 있습니다. 사용 예시:

```py
print(type("Anna"))
print(type(100))
```

```
<class 'str'>
<class 'int'>
```

### 구문
자연어와 유사하게, 프로그래밍 언어의 _구문_ 은 프로그램의 코드를 어떻게 작성해야 하는지를 결정합니다. 각 프로그래밍 언어는 고유한 특정 구문을 가지고 있습니다.
 
파이썬의 구문은, 다른 것들 중에서도, `if` 문의 첫 줄은 콜론 문자로 끝나야 하고, 문의 블록은 들여쓰기되어야 한다고 명시합니다:
 

```py
if name == "Anna":
    print("Hi!")
```
프로그래밍 언어의 구문 규칙을 따르지 않으면 오류가 발생합니다:
```py
if name == "Anna"
    print("Hi!")
```

```
  File "test.py", line 1
    if name == "Anna"
                    ^
SyntaxError: invalid syntax
```

### 디버깅
프로그램의 구문은 올바르지만 프로그램이 여전히 의도한 대로 작동하지 않으면 프로그램에 _버그_ 가 있는 것입니다.
 
버그는 다양한 방식으로 나타납니다. 일부 버그는 실행 중에 오류를 일으킵니다. 예를 들어, 다음 프로그램은

```py
x = 10
y = 0
result = x / y

print(f"{x} divided by {y} is {result}")
```
이러한 오류를 일으킵니다:

```
ZeroDivisionError: integer division or modulo by zero on line 3
```

여기서 문제는 수학적인 성격입니다: 0으로 나누는 것은 허용되지 않으며, 이것이 프로그램 실행을 중단시킵니다.
 
실행 중 오류는 일반적으로 수정하기가 다소 쉽습니다. 왜냐하면 오류 메시지가 오류를 일으키는 코드 줄을 명시하기 때문입니다. 물론 버그의 실제 원인은 오류를 일으키는 코드 줄과는 상당히 다른 곳에 있을 수 있습니다.
 
때때로 프로그램의 버그는 코드가 생성하는 결과가 잘못되었기 때문에 드러납니다. 이러한 유형의 버그를 발견하고 찾는 것은 어려울 수 있습니다. 이 과정의 프로그래밍 연습 문제에서 테스트는 일반적으로 이러한 유형의 버그를 드러내기 위한 것입니다. 버그를 수정하기 전에 먼저 그 원인을 찾아야 합니다.
 
프로그래밍 전문 용어에서는 버그의 원인을 찾는 것을 _디버깅_ 이라고 합니다. 이는 모든 프로그래머의 도구 상자에서 매우 중요한 기술입니다. 전문 프로그래머는 종종 새로운 코드를 작성하는 것보다 디버깅에 더 많은 시간을 보냅니다.
 
프로그램을 디버깅하는 간단하면서도 효과적인 방법은 코드에 디버깅 출력문을 추가하는 것입니다. `print` 명령으로 코드 결과를 확인하면 코드가 원하는 대로 작동하는지 빠르게 확인할 수 있습니다.
 
다음은 이전 섹션의 연습 문제 중 하나를 해결하려는 시도입니다:

```py
hourly_wage = float(input("Hourly wage: "))
hours = int(input("Hours worked: "))
day = input("Day of the week: ")

daily_wages = hourly_wage * hours
if day == "sunday":
    daily_wages * 2

print(f"Daily wages: {daily_wages} euros")
```

프로그램이 제대로 작동하지 않습니다. 테스트를 실행하면 다음이 출력됩니다:

```
FAIL: PythonEditorTest: test_sunday_1

With input 20.0,6,Sunday correct wage 240.0 is not found in output Daily wages: 120.0 euros
```
이 과정의 연습 문제를 디버깅할 때, 첫 번째 단계는 종종 실패한 테스트에 명시된 입력으로 프로그램이 어떻게 동작하는지 확인하는 것입니다. 실제로 결과는 예상했던 것과 다릅니다:
```
Daily wages: 120.0 euros
```
디버깅은 보통 프로그램을 여러 번 실행하는 것을 의미합니다. 매번 사용자에게 입력을 요청하는 대신에, 문제가 되는 입력을 임시로 "하드 코딩"하는 것이 유용할 수 있습니다. 이 경우 하드 코딩은 다음과 같을 수 있습니다:

```py
# hourly_wage = float(input("Hourly wage: "))
# hours = int(input("Hours worked: "))
# day = input("Day of the week: ")
hourly_wage = 20.0
hours = 6
day = "Sunday"

daily_wages = hourly_wage * hours
if day == "sunday":
    daily_wages * 2

print(f"Daily wages: {daily_wages} euros")
```

다음 단계는 _디버깅 출력문을 추가하는 것_ 일 수 있습니다. 코드의 문제가 되는 부분은 일요일을 처리하는 섹션에 있으므로, 일요일에 일당을 두 배로 만들어야 하는 줄의 앞과 뒤에 `print` 명령을 추가합시다:

```py
# ...

daily_wages = hourly_wage * hours
if day == "sunday":
    print("wages before:", daily_wages)
    daily_wages * 2
    print("wages after doubling:", daily_wages)

print(f"Daily wages: {daily_wages} euros")
```

지금 코드를 실행하면 아무것도 나타나지 않습니다 - 디버깅 출력문이 전혀 출력되지 않습니다. `if` 블록의 내용이 전혀 실행되지 않는 것 같으므로, 조건문에 문제가 있는 것이 틀림없습니다. 불리언 표현식의 값을 출력해 봅시다:

```py
# ...

daily_wages = hourly_wage * hours
print("condition:", day == "sunday")
if day == "sunday":
    print("wages before:", daily_wages)
    daily_wages * 2
    print("wages after doubling:", daily_wages)

print(f"Daily wages: {daily_wages} euros")
```

실제로, 값은 `False`이므로, if 블록의 내용은 절대 실행되지 않습니다:

```
condition:  False
Daily wages: 120.0 euros
```

문제는 그러면 `if` 문의 조건 안에 있는 것이 틀림없습니다. 프로그래밍의 많은 상황에서처럼, 비교에서도 문자의 대소문자가 중요합니다. 불리언 표현식의 "sunday"는 대문자로 표기되지 않았지만, 입력에서는 대문자였음을 주목하십시오. 이것을 수정합시다 (`print` 명령어와 `if` 문 모두에서):

```py
# ...

daily_wages = hourly_wage * hours
print("condition:", day == "Sunday")
if day == "Sunday":
    print("wages before:", daily_wages)
    daily_wages * 2
    print("wages after doubling:", daily_wages)

print(f"Daily wages: {daily_wages} euros")
```
이것을 실행하면 다음이 출력됩니다:

```
condition: True
wages before: 120
wages after doubling: 120
Daily wages: 120.0 euros
```

처음에는 `daily_wages`에 저장된 값이 올바른 것 같습니다: `hourly_wage = 20.0`이고 `hours = 6`이며, 20.0 * 6 = 120.0입니다. 그러나, 수치를 두 배로 만들기로 되어 있는 명령은 그렇게 하지 않습니다, 따라서 명령에 문제가 있는 것이 틀림없습니다. 그리고 실제로 그 명령은

```py
daily_wages * 2
```
값을 두 배로 만듭니다, 하지만 새 값을 어디에도 저장하지 않습니다. 새 값도 저장하도록 변경해 봅시다:
```py
daily_wages *= 2
```
프로그램을 다시 실행하면 마지막의 출력도 이제 올바르다는 것을 보여줍니다:

```
condition: True
wages before: 120
wages after doubling: 240
Daily wages: 240.0 euros
```

프로그램이 수정되면, 모든 디버깅 출력문과 디버깅 목적으로 추가된 다른 코드를 제거하는 것을 기억하십시오.
 
이 예제는 꽤 간단했고, 이렇게 짧은 프로그램에서는 아마도 코드를 주의 깊게 읽는 것만으로 버그를 알아낼 수 있었을 것입니다. 하지만, 디버깅 출력문을 사용하는 것은 종종 문제가 어디에 있을지에 대한 감을 잡는 빠른 방법입니다. 출력문은 프로그램의 어느 부분이 올바르게 작동하는 것처럼 보이는지 알아내는 데 사용될 수 있으므로, 버그 추적 노력은 가장 유력한 범인인 코드 섹션에 집중될 수 있습니다.
 
디버깅 출력문은 프로그램을 디버깅하기 위한 하나의 도구일 뿐입니다. 우리는 이 과정 후반에 이 주제로 다시 돌아올 것입니다. 이제 코드에서 실수를 찾기 위해 디버깅 출력문을 사용하는 습관을 들여야 합니다. 프로그래밍 전문가들은 그것들을 사용하지 않고는 지낼 수 없으므로, 초보자에게도 매우 유용한 도구입니다.

## 더 많은 조건문
 
사용자에게 숫자를 입력하도록 요청하고, 그런 다음 숫자가 음수인지, 양수인지, 또는 0과 같은지에 따라 다른 메시지를 출력하는 프로그램을 살펴봅시다:

```py
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")

if number >= 0:
    print("The number is positive or zero")

```
이것은 좀 어색하고 반복적으로 보입니다. 우리는 `if` 블록 중 하나만 실행하기를 원합니다. 왜냐하면 입력은 항상 0보다 작거나, 0이거나, 또는 0보다 클 것이기 때문입니다. 즉,`number < 0` 또는 `number >= 0` 중 하나는 참이지만, 결코 둘 다 동시에 참일 수는 없습니다. 따라서, 첫 번째 조건문이 사실상 여기에 필요한 모든 것을 포함합니다. 그것이 참이면, 숫자는 음수입니다. 그것이 거짓이면, 숫자는 0이거나 양수입니다.
 
위 예시처럼 완전히 다른 조건문을 만드는 대신, _조건이 거짓인_ 모든 경우를 처리하기 위해 동일한 조건문의 다른 분기를 만드는 것이 가능합니다. 이것을 `else` 문이라고 합니다.
 
이전 예제를 다시 작성하면 다음과 같습니다:

```py
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")
else:
    print("The number is positive or zero")
```

if-else 구조를 사용할 때, 분기 중 하나 그리고 정확히 하나만 항상 실행됩니다.
다음 그림은 그 구조를 보여줍니다:

![](https://programming-25.mooc.fi/static/c5e369c48eb7d985dab911b91e99c09e/9516f/2_2_1.png)

참고: 이전에 if 분기문 없이 else 분기문이 있을 수는 절대로 없습니다. if-else 구조 전체는 단일 _조건문_ 을 형성합니다.
 
다음 예제는 사용자가 제공한 숫자가 짝수인지 아닌지를 확인합니다. 패리티는 정수 나눗셈 연산의 나머지를 생성하는 모듈로 연산자 `%`로 확인할 수 있습니다. 2로 나누었을 때 나머지가 0이면 숫자는 짝수입니다. 그렇지 않으면 숫자는 홀수입니다.
 
```py
number = int(input("Please type in a number: "))

if number % 2 == 0:
    print("The number is even")
else:
    print("The number is odd")
```

```
Please type in a number: 5
The number is odd
```
문자열 비교에 대한 또 다른 예:

```py
correct = "kittycat"
password = input("Please type in the password: ")

if password == correct:
    print("Welcome")
else:
    print("No admittance")
```
두 개의 다른 입력으로 이것은 출력해야 합니다:
```
Please type in the password: kittycat↵
Welcome
```
```
Please type in the password: monkey↵
No admittance
```

### elif 문을 사용하는 대안 분기
종종 프로그램이 고려해야 할 옵션이 두 개 이상 있습니다. 예를 들어, 축구 경기 결과는 세 가지 방향으로 갈 수 있습니다: 홈 승리, 원정 승리, 또는 무승부입니다.
 
조건문은 `elif` 분기로 추가될 수 있습니다. 이것은 "else if"라는 단어의 줄임말이며, 이는 해당 분기가 원래 조건에 대한 대안을 포함할 것임을 의미합니다. 중요하게도, `elif` 문은 이전 분기 중 어느 것도 실행되지 않은 경우에만 실행됩니다.


![](https://programming-25.mooc.fi/static/62ebffc483e387b1f45eac73a9e0d285/74866/2_2_2.png)

경기의 승자를 결정하는 프로그램을 한번 살펴봅시다:

```py
goals_home = int(input("Home goals scored: "))
goals_away = int(input("Away goals scored: "))

if goals_home > goals_away:
    print("The home team won!")
elif goals_away > goals_home:
    print("The away team won!")
else:
    print("It's a tie!")
```
이 프로그램은 다른 입력들이 주어졌을 때 세 개의 다른 문장들을 출력할 수 있습니다:

```
Home goals scored: 4↵
Away goals scored: 2↵
The home team won!
```
```
Home goals scored: 0↵
Away goals scored: 6↵
The away team won!
```

```
Home goals scored: 3↵
Away goals scored: 3↵
It's a tie!
```
위 예제에는 세 개의 대안 분기가 있으며, 그중 정확히 하나가 항상 실행될 것입니다. 그러나, 조건문이 포함할 수 있는 `elif` 분기의 수에는 제한이 없으며, `else` 분기는 필수가 아닙니다.
 
이것 또한 유효한 조건문입니다:

```py
print("Holiday calendar")
date = input("What is the date today? ")

if date == "Dec 26":
    print("It's Boxing Day")
elif date == "Dec 31":
    print("It's Hogmanay")
elif date == "Jan 1":
    print("It's New Year's Day")

print("Thanks and bye.")
```

```
Holiday calendar
What is the date today? Dec 31↵
It's Hogmanay
Thanks and bye.
```
이전 예제는 `else` 분기를 가지지 않는다는 것을 주목하십시오. 만약 사용자가 `if` 또는 `elif` 분기 중 어느 것에도 언급되지 않은 날짜를 입력하거나, 다른 형식으로 날짜를 입력하면, 조건문의 세 분기 중 어느 것도 실행되지 않습니다.
```
Holiday calendar
What is the date today? Dec 25↵
Thanks and bye.
```

## 조건 결합

### 논리 연산자
논리 연산자 `and`와 `or`를 사용하여 조건을 결합할 수 있습니다. `and` 연산자는 주어진 모든 조건이 동시에 참이어야 함을 지정합니다. `or` 연산자는 주어진 조건 중 적어도 하나가 참이어야 함을 지정합니다.

예를 들어, `number >= 5 and number <= 8` 조건은 `number`가 동시에 최소 5이고 최대 8이어야 함을 결정합니다. 즉, 5와 8 사이여야 합니다.

```py
number = int(input("Please type in a number: "))
if number >= 5 and number <= 8:
    print("The number is between 5 and 8")
```
한편, `number < 5 or number > 8` 조건은 `number`가 5보다 작거나 8보다 커야 함을 결정합니다. 즉, 5에서 8까지의 범위 내에 있어서는 안 됩니다.

```py
number = int(input("Please type in a number: "))
if number < 5 or number > 8:
    print("The number is not within the range of 5 to 8")
```
다음 진리표는 다른 상황들에서의 이 연산자들의 동작을 포함합니다

|a	|b	|a and b	|a or b
|---|---|---|---|---|
|False	|False	|False	|False
|True	|False	|False	|True
|False	|True	|False	|True
|True	|True	|True	|True

때때로 어떤 것이 사실이 _아닌지_ 아는 것이 필요합니다. 연산자 `not`은 조건을 부정합니다:

|a	|not a
|---|---|---|
|True	|False
|False	|True

5에서 8까지의 범위를 _제외한_ 위의 예제는 다음과 같이 프로그래밍될 수도 있습니다:
```py
number = int(input("Please type in a number: "))
if not (number >= 5 and number <= 8):
    print("The number is not within the range of 5 to 8")
```
특히 프로그래밍에서는 논리 연산자를 종종 _Boolean 연산자_ 라고 부릅니다.

> 간소화된 결합 조건
조건 `x >= a and x <= b`는 숫자 `x`가 `a`에서 `b` 사이의 범위에 속하는지 확인하는 매우 일반적인 방법입니다.
이러한 구조를 가진 표현식은 대부분의 프로그래밍 언어에서 동일하게 작동합니다.<br>
파이썬은 또한 조건을 결합하기 위한 간소화된 표기법을 허용합니다: `a <= x <= b`는 `and`를 사용하는 더 긴 버전과 동일한 결과를 얻습니다.
이 더 짧은 표기법은 수학에서는 더 익숙할 수 있지만, 파이썬 프로그래밍에서는 그다지 널리 사용되지 않습니다. 아마도 유사한 축약형을 가진 다른 프로그래밍 언어가 거의 없기 때문일 것입니다.

### 조건 결합 및 연쇄
다음 프로그램은 사용자에게 네 개의 숫자를 입력하도록 요청합니다.
그런 다음 몇 가지 조건의 도움을 받아 네 개 중 어느 것이 가장 큰지 알아냅니다:

```py
n1 = int(input("Number 1: "))
n2 = int(input("Number 2: "))
n3 = int(input("Number 3: "))
n4 = int(input("Number 4: "))

if n1 > n2 and n1 > n3 and n1 > n4:
    greatest = n1
elif n2 > n3 and n2 > n4:
    greatest = n2
elif n3 > n4:
    greatest = n3
else:
    greatest = n4

print(f" {greatest} is the greatest of the numbers.")
```

```
Number 1: 2↵
Number 2: 4↵
Number 3: 1↵
Number 4: 1↵
4 is the greatest of the numbers.
```
위의 예에서 첫 번째 조건 `n1 > n2` 이고 `n1 > n3` 이고 `n1 > n4`는 내부의 세 가지 조건 모두가 참인 경우에만 참입니다.

### 중첩 조건문
조건문은 다른 조건문 안에 중첩될 수도 있습니다. 예를 들어, 다음 프로그램은 숫자가 0보다 큰지 확인한 다음, 홀수인지 짝수인지 확인합니다:
 

```py
number = int(input("Please type in a number: "))

if number > 0:
    if number % 2 == 0:
        print("The number is even")
    else:
        print("The number is odd")
else:
    print("The number is negative or zero")
```
이 프로그램이 어떻게 동작하는지에 대한 몇 가지 예시입니다:

```
Please type in a number: 3↵
The number is odd

Please type in a number: 18↵
The number is even

Please type in a number: -4↵
The number is negative or zero
```
중첩 조건문에서는 들여쓰기를 올바르게 하는 것이 매우 중요합니다. 들여쓰기는 어떤 분기들이 함께 연결되는지를 결정합니다. 예를 들어, 동일한 양의 공백을 가진 `if` 분기와 `else` 분기는 동일한 조건문의 분기로 결정됩니다.
 
동일한 결과는 종종 중첩 조건문이나 논리 연산자와 결합된 조건을 사용하여 달성될 수 있습니다. 아래 예시는 동일한 입력에 대해 정확히 동일한 것을 출력한다는 점에서 위 예시와 기능적으로 다르지 않습니다:


```py
number = int(input("Please type in a number: "))

if number > 0 and number % 2 == 0:
    print("The number is even")
elif number > 0 and number % 2 != 0:
    print("The number is odd")
else:
    print("The number is negative or zero")
```

어느 접근 방식도 본질적으로 다른 방식보다 더 낫지는 않지만, 다른 상황에서는 이쪽 또는 저쪽이 더 논리적으로 보일 수 있습니다. 이 특정 예시에서는 대부분의 사람들은 중첩이 있는 첫 번째 버전을 더 직관적이라고 여기는 경향이 있습니다.

## 단순 반복문
 
 
이제 우리는 조건 구조에 대해 어느 정도 자세히 다루었습니다. 프로그래밍의 또 다른 핵심 기법은 반복 또는 _iteration_ 입니다. 이들은 함께 모든 프로그래머가 숙달해야 하는 기본적인 제어 구조를 형성합니다. 이것들이 제어 구조라고 불리는 이유는 기본적으로 어떤 코드 라인이 언제 실행될지 제어할 수 있게 해주기 때문입니다. 조건 구조는 코드 섹션 _사이에서 선택_ 할 수 있게 해주는 반면, 반복 구조는 코드 섹션을 _반복_ 할 수 있게 해줍니다. 이것들은 프로그램이 이전에 이미 실행된 어떤 라인으로 "되돌아갈" 수 있게 해주기 때문에 종종 _루프_ 라고 불립니다. 루프의 한 반복을 실행하는 과정은 루프의 이터레이션이라고도 합니다.
 
이 섹션에서는 간단한 `while` 루프를 소개합니다. 그 구조는 우리가 이미 다룬 조건문과 유사합니다. 다음 파트에서는 좀 더 복잡한 예제를 살펴볼 것입니다.
 
사용자에게 숫자를 입력하도록 요청한 다음 그 숫자의 제곱을 출력하는 프로그램을 살펴봅시다. 이는 사용자가 -1을 입력할 때까지 계속됩니다.

```py
while True:
    number = int(input("Please type in a number, -1 to quit: "))

    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```
프로그램을 실행하면 다음과 같을 수 있습니다:
```
Please type in a number, -1 to quit: 2↵
4
Please type in a number, -1 to quit: 4↵
16
Please type in a number, -1 to quit: 10↵
100
Please type in a number, -1 to quit: -1↵
Thanks and bye!
```
위에서 볼 수 있듯이, 프로그램은 프로그램 내의 `while` 문 덕분에 여러 숫자를 요청합니다. 사용자가 -1을 입력하면 `break` 명령이 실행되어 루프를 빠져나가고 `while` 블록 다음의 첫 번째 줄부터 실행이 계속됩니다.
 
루프에서는 코드의 어느 시점에서든 항상 루프를 빠져나갈 방법이 있는 것이 중요합니다. 그렇지 않으면 반복이 영원히 계속될 수 있습니다. 이를 설명하기 위해 위의 예제를 약간 변경해 보겠습니다:
 
```py
number = int(input("Please type in a number, -1 to quit: "))
while True:
    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```
이 버전에서는 프로그램이 사용자에게 _루프 밖_ 에서 숫자를 입력하도록 요청합니다. 사용자가 -1 이외의 다른 숫자를 입력하면 루프는 절대 빠져나가지 못합니다. 이는 무한 루프를 형성하며, 이는 루프 내의 코드 블록이 끝없이 반복된다는 것을 의미합니다:

```
Please type in a number, -1 to quit: 2↵
4
4
4
4
4
4
4
4
(continued ad infinitum...)
```
다음 프로그램은 _무한 루프_ 위의 예제와 유사한 구조를 가지고 있지만 사용자 경험은 상당히 다릅니다. 이 프로그램은 사용자가 올바른 PIN _1234_ 를 입력해야만 진행할 수 있도록 허용합니다:
```py
while True:
    code = input("Please type in your PIN: ")
    if code == "1234":
        break
    print("Incorrect...try again")

print("Correct PIN entered!")
```

```
Please type in your PIN: 0000↵
Incorrect...try again
Please type in your PIN: 9999↵
Incorrect...try again
Please type in your PIN: 1234↵
Correct PIN entered!
```

### 루프와 도우미 변수
PIN 확인 예제를 좀 더 현실적으로 만들어 봅시다. 이 버전은 사용자에게 PIN 입력 시도를 세 번만 허용합니다.
 
이 프로그램은 두 개의 도우미 변수를 사용합니다. 변수 `attempts`는 사용자가 PIN을 입력한 횟수를 추적합니다. 변수 `success`는 사용자의 로그인 성공 여부에 따라 `True` 또는 `False`로 설정됩니다.
 

```py
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1

    if code == "1234":
        success = True
        break

    if attempts == 3:
        success = False
        break

    # this is printed if the code was incorrect AND there have been less than three attempts
    print("Incorrect...try again")

if success:
    print("Correct PIN entered!")
else:
    print("Too many attempts...")
```

```
Please type in your PIN: 0000↵
Incorrect...try again
Please type in your PIN: 1234↵
Correct PIN entered!
```

```
Please type in your PIN: 0000↵
Incorrect...try again
Please type in your PIN: 9999↵
Incorrect...try again
Please type in your PIN: 4321↵
Too many attempts...
```

루프는 사용자가 올바른 PIN을 입력하거나 시도 횟수가 너무 많아지면 종료됩니다. 루프 뒤의 `if` 문은 변수 `success`의 값을 확인하고 그에 따라 메시지를 출력합니다.

### 루프 내 디버깅 출력문
프로그램에 루프를 추가하면 잠재적인 버그 원인도 늘어납니다. 이 파트의 첫 번째 섹션에서 소개된 디버깅 출력문의 사용법을 숙달하는 것이 더욱 중요해집니다.
 
이전 예제와 거의 동일하지만 한 가지 결정적인 차이점이 있는 프로그램을 살펴보겠습니다.

```py
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1

    if attempts == 3:
        success = False
        break

    if code == "1234":
        success = True
        break

    print("Incorrect...try again")

if success:
    print("Correct PIN entered!")
else:
    print("Too many attempts...")
```

이 버전은 사용자가 세 번째 시도에서 올바른 코드를 입력했을 때 이상하게 작동합니다.

```
Please type in your PIN: 0000↵
Incorrect...try again
Please type in your PIN: 9999↵
Incorrect...try again
Please type in your PIN: 1234↵
Too many attempts...
```

그러니 루프 내부에 전략적인 디버깅 출력문을 추가하여 원인을 찾아봅시다.

```py
while True:
    print("beginning of the while block:")
    code = input("Please type in your PIN: ")
    attempts += 1

    print("attempts:", attempts)
    print("condition1:", attempts == 3)
    if attempts == 3:
        success = False
        break

    print("code:", code)
    print("condition2:", code == "1234")
    if code == "1234":
        success = True
        break

    print("Incorrect...try again")
```

```
beginning of the while block:
Please type in your PIN: 2233↵
attempts: 1
condition1: False
code: 2233
condition2: False
Incorrect...try again
beginning of the while block:
Please type in your PIN: 4545↵
attempts: 2
condition1: False
code: 4545
condition2: False
Incorrect...try again
beginning of the while block:
Please type in your PIN: 1234↵
attempts: 3
condition1: True
Too many attempts...
```

위의 출력에서 루프의 세 번째 반복 동안 첫 번째 `if` 문의 조건이 `True`가 되어 루프가 종료되는 것을 볼 수 있습니다. 이 반복은 코드가 올바르게 입력되었는지 확인하는 두 번째 `if` 문에 도달하지 못합니다.

```py
while True:
    # ....

    # this block is executed too early
    if attempts == 3:
        success = False
        break

    # the third iteration never gets this far
    if code == "1234":
        success = True
        break
```

조건문의 순서나 조건문 내의 다른 분기 순서는 특히 루프에서 버그의 흔한 원인입니다. 디버깅 출력문은 종종 그 원인을 찾는 가장 간단한 방법입니다.

### + 연산자로 문자열 연결하기
PIN 확인을 사용한 위 예제에서는 사용자가 코드를 입력하려고 시도한 횟수를 추적하기 위해 도우미 변수 `attempts`를 사용했습니다:

```py
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1
    # ...
```
변수는 루프 외부에서 0으로 설정되며, 각 반복마다 그 값이 1씩 증가합니다.
 
증가라는 유사한 아이디어가 문자열 변수에서도 작동합니다. 예를 들어, 프로그램은 사용자가 입력한 모든 PIN 코드를 추적할 수 있습니다:
 

```py
codes = ""
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1
    codes += code + ", "
    # ...
```
도우미 변수는 _빈 문자열_, 즉 문자가 없는 문자열로 초기화됩니다:

```py
codes = ""
```
각 반복마다 사용자가 입력한 코드와 쉼표가 추가되면서 문자열이 길어집니다:

```py
    code = input("Please type in your PIN: ")
    codes += code + ", "
```
사용자가 _1111 2222 1234_ 코드를 입력하면, 프로그램 실행 종료 시 `codes`의 값은 다음과 같을 것입니다
```
1111, 2222, 1234,
```