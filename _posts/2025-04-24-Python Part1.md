---
title: Python Part1
date: 2025-04-24
categories: [Python]
tags: [Python]
math: true
---
## 시작하기

컴퓨터 프로그램은 _명령어_ 들로 구성되며, 각 명령어는 컴퓨터에게 어떤 동작을 수행하도록 지시합니다. 컴퓨터는 이 명령어들을 하나씩 실행합니다. 명령어는 계산 수행, 컴퓨터 메모리 내의 내용 비교, 프로그램 작동 방식 변경, 메시지 전달 또는 프로그램 사용자로부터 정보 요청 등 다양한 용도로 사용될 수 있습니다.

텍스트를 _출력(print)_ 하는 `print` 명령어를 익히면서 프로그래밍을 시작해 봅시다. 이 맥락에서 출력한다는 것은 기본적으로 프로그램이 화면에 어떤 텍스트를 보여준다는 의미입니다.

다음 프로그램은 "Hi there!"라는 줄을 출력합니다:

```py
print("Hi there!")
```

프로그램을 실행하면 다음과 같은 결과가 나옵니다:

```
Hi there!
```

코드가 위에 나온 것과 정확히 똑같이 작성되지 않으면 프로그램은 작동하지 않습니다. 예를 들어, 따옴표 없이 print 명령어를 실행하려고 하면, 다음과 같이 됩니다

```py
print(Hi there!)
```

이는 메시지를 출력하지 않고 대신 오류를 발생시킵니다:

```
File "", line 1
  print(Hi there!)
                   ^
SyntaxError: invalid syntax
```

요약하자면, 텍스트를 출력하려면 텍스트 전체를 따옴표로 감싸야 합니다. 그렇지 않으면 파이썬이 이를 올바르게 해석하지 못합니다.

### 여러 명령어로 이루어진 프로그램

연속해서 작성된 여러 명령어는 처음부터 마지막 순서대로 실행됩니다. 예를 들어 이 프로그램은

```py
print("Welcome to Introduction to Programming!")
print("First we will practice using the print command.")
print("This program prints three lines of text on the screen.")
```

화면에 다음 줄들을 출력합니다:

```
Welcome to Introduction to Programming!
First we will practice using the print command.
This program prints three lines of text on the screen.
```

### 산술 연산

`print` 명령어 안에 산술 연산을 넣을 수도 있습니다. 이를 실행하면 연산 결과가 출력됩니다. 예를 들어, 다음 프로그램은

```py
print(2 + 5)
print(3 * 3)
print(2 + 2 * 10)
```

다음과 같은 줄들을 출력합니다:

```
7
9
22
```

위 산술 연산 주위에 따옴표가 없는 것을 주목하세요. 따옴표는 _문자열(string)_ 을 나타내는 데 사용됩니다. 프로그래밍 맥락에서 문자열은 문자들의 연속입니다. 문자열은 글자, 숫자 및 구두점과 같은 다른 모든 종류의 문자로 구성될 수 있습니다. 문자열은 우리가 흔히 이해하는 단어뿐만 아니라, 여러 개의 완전한 문장 길이만큼 길어질 수도 있습니다. 문자열은 보통 작성된 그대로 출력됩니다. 따라서 다음 두 명령어는 상당히 다른 두 가지 결과를 생성합니다:

```py
print(2 + 2 * 10)
print("2 + 2 * 10")
```

이 프로그램은 다음을 출력합니다:

```
22
2 + 2 * 10
```

두 번째 코드 줄에서는 파이썬이 연산 결과를 계산하지 않고, 대신 연산 자체를 문자열로 출력합니다. 즉, 문자열은 내용과 관계없이 작성된 그대로 출력됩니다.

### 주석 달기

파운드 기호 `##`(해시 또는 숫자 기호라고도 함)로 시작하는 모든 줄은 주석입니다. 이는 _##_ 기호 뒤에 오는 해당 줄의 모든 텍스트가 프로그램 기능에 어떤 영향도 미치지 않는다는 것을 의미합니다. 파이썬은 이를 그냥 무시합니다.

주석은 프로그래머 자신과 프로그램 코드를 읽는 다른 사람 모두에게 프로그램이 어떻게 작동하는지 설명하는 데 사용됩니다. 이 프로그램에서는 주석이 코드에서 수행되는 계산을 설명합니다:

```py
print("Hours in a year:")
## 1년은 365일이고, 하루는 24시간입니다
print(365*24)
```

프로그램이 실행될 때 주석은 사용자에게 보이지 않습니다:

```
Hours in a year:
8760
```

짧은 주석은 줄 끝에 추가할 수도 있습니다:

```py
print("Hours in a year:")
print(365*24) ## 365일, 하루에 24시간
```

## 사용자 입력

_입력_ 은 사용자가 프로그램에 제공하는 모든 정보를 의미합니다. 특히, 파이썬 명령어 `input`은 사용자가 입력한 한 줄의 입력을 읽어들입니다. 또한 사용자에게 메시지를 표시하여 특정 입력을 요청하는 데에도 사용될 수 있습니다.

다음 프로그램은 `input` 명령을 사용하여 사용자의 이름을 읽어들입니다. 그런 다음 `print` 명령을 사용하여 이를 출력합니다:

```python
name = input("What is your name? ")
print("Hi there, " + name)
```

이 프로그램의 실행 결과는 다음과 같을 수 있습니다 (사용자 입력은 빨간색으로 표시):

```
What is your name? Paul Python↵
Hi there, Paul Python
```

이 프로그램이 출력하는 내용은 부분적으로 사용자 입력에 따라 달라집니다. 즉, 프로그램 실행 결과는 다음과 같을 수도 있습니다:

```
What is your name? Paula Programmer↵
Hi there, Paula Programmer
```

이 프로그램에서 `name`이라는 단어는 _변수_입니다. 프로그래밍에서 변수는 문자열이나 숫자와 같은 특정 _값_을 저장하는 위치입니다. 이 값은 나중에 사용될 수 있으며, 변경될 수도 있습니다.

> **변수 이름 짓기**<br>
원칙적으로 변수는 파이썬 언어에 지정된 특정 제한 내에서 비교적 자유롭게 이름을 지을 수 있습니다.<br>
<br>
변수 이름을 영어로 짓는 것이 일반적인 국제 프로그래밍 관행이지만, 프로그래머의 모국어와 같은 다른 언어로 변수 이름을 짓는 코드를 접할 수도 있습니다. 변수 이름은 내용에 직접적인 영향을 미치지 않으므로, 그런 의미에서 이름은 중요하지 않습니다. 그러나 변수가 논리적으로 영어로 명명되면 코드가 어떻게 작동하는지 이해하는 데 종종 도움이 될 수 있습니다.

### 변수 참조

단일 변수는 프로그램에서 여러 번 참조될 수 있습니다:

```python
name = input("What is your name? ")
print("Hi, " + name + "!")
print(name + " is quite a nice name.")
```

사용자가 `Paul Python`이라는 이름을 입력하면 이 프로그램은 다음을 출력합니다:

```
What is your name? Paul Python↵
Hi, Paul Python!
Paul Python is quite a nice name.
```

위에서 `print` 명령이 사용된 방식을 자세히 살펴보겠습니다. 명령의 괄호 안에는 따옴표로 묶인 텍스트와 사용자 입력 값을 참조하는 변수 이름이 모두 있습니다. 이들은 `+` 연산자로 결합되었는데, 이 연산자는 두 개의 문자열을 연결하여 하나의 문자열로 만듭니다.

문자열과 변수는 비교적 자유롭게 결합될 수 있습니다:

```python
name = input("What is your name? ")

print("Hi " + name + "! Let me make sure: your name is " + name + "?")
```

사용자가 `Ellen Example`이라는 이름을 입력하면 다음이 출력됩니다.

```
What is your name? Ellen Example↵
Hi Ellen Example! Let me make sure: your name is Ellen Example?
```

### 둘 이상의 입력

프로그램은 둘 이상의 입력을 요청할 수 있습니다. 아래에서 각 `input` 명령은 받은 값을 서로 다른 변수에 저장하는 방식을 확인하십시오.

```python
name = input("What is your name? ")
email = input("What is your email address? ")
nickname = input("What is your nickname? ")

print("Let's make sure we got this right")
print("Your name: " + name)
print("Your email address: " + email)
print("Your nickname: " + nickname)
```

예를 들어, 프로그램은 다음과 같이 출력할 수 있습니다:

```
What is your name? Frances Fictitious↵
What is your email address? frances99@example.com↵
What is your nickname? Fran↵
Let's make sure we got this right↵
Your name: Frances Fictitious↵
Your email address: frances99@example.com↵
Your nickname: Fran↵
```

동일한 변수가 둘 이상의 입력을 저장하는 데 사용되면 각 새 값은 이전 값을 덮어씁니다. 예를 들어:

```python
address = input("What is your address? ")
print("So you live at address " + address)

address = input("Please type in a new address: ")
print("Your address is now " + address)
```

프로그램:

```
What is your address? Python Path 101, Flat 3D↵
So you live at address Python Path 101, Flat 3D
Please type in a new address: New Road 999↵
Your address is now New Road 999
```

이는 동일한 변수가 연속적으로 두 입력을 저장하는 데 사용되면 두 번째 값으로 대체된 후에는 첫 번째 입력 값에 액세스할 수 없음을 의미합니다:

```python
address = input("What is your address? ")
address = input("Please type in a new address: ")

print("Your address is now " + address)
```

프로그램 출력 예시:

```
What is your address? Python Path 10↵
Please type in a new address: Programmer's Walk 23↵
Your address is now Programmer's Walk 23
```

## 변수에 대한 상세 정보

프로그래밍에서는 다양한 목적으로 변수가 필요합니다. 변수를 사용하면 프로그램 실행 중 나중에 필요한 정보를 저장할 수 있습니다.

파이썬 프로그래밍에서는 변수를 다음과 같이 만듭니다:


`variable_name = ...`


여기서 `...`는 변수에 저장되는 값을 의미합니다.

예를 들어, `input` 함수를 사용하여 사용자로부터 문자열을 읽어올 때, 그 문자열을 변수에 저장한 다음 프로그램의 뒷부분에서 해당 변수를 사용했습니다:

```python
name = input("이름이 무엇인가요? ")
print("안녕하세요, " + name + "님")
```

```
이름이 무엇인가요? Ghosty↵
안녕하세요, Ghosty님
```

변수에 저장되는 값은 다른 변수를 사용하여 정의할 수도 있습니다:

```python
given_name = "Paul"
family_name = "Python"

name = given_name + " " + family_name

print(name)
```

```
Paul Python
```

여기서 세 변수에 저장된 값은 사용자 입력으로 얻은 것이 아닙니다. 이 값들은 프로그램이 실행될 때마다 동일하게 유지됩니다. 이를 프로그램에 데이터를 _하드-코딩_ 한다고 합니다.

### 변수 값 변경하기

_변수(variable)_라는 이름에서 알 수 있듯이, 변수에 저장된 값은 변경될 수 있습니다. 이전 섹션에서 보았듯이, 새로운 값은 기존 값을 대체합니다.

다음 프로그램이 실행되는 동안 `word` 변수는 세 가지 다른 값을 갖게 됩니다:

```python
word = input("Please type in a word: ")
print(word)

word = input("And another word: ")
print(word)

word = "third"
print(word)
```

```
Please type in a word: first↵
first
And another word: second↵
second
third
```

변수에 새로운 값이 할당될 때마다 변수에 저장된 값은 변경됩니다.

변수의 새로운 값은 기존 값으로부터 파생될 수 있습니다. 다음 예제에서는 `word` 변수에 먼저 사용자 입력을 기반으로 한 값이 할당됩니다. 그런 다음, 기존 값 끝에 느낌표 세 개를 추가한 새로운 값이 할당됩니다.

```python
word = input("Please type in a word: ")
print(word)

word = word + "!!!"
print(word)
```

```
Please type in a word: test↵
test
test!!!
```

> **좋은 변수 이름 선택하기**
- 변수의 용도에 따라 이름을 짓는 것이 유용할 때가 많습니다. 예를 들어, 변수에 단어가 포함되어 있다면 `a`와 같은 이름보다는 `word`라는 이름이 더 좋습니다.
- 파이썬에서 변수 이름의 길이에 정해진 제한은 없지만, 몇 가지 다른 제약 사항이 있습니다. 변수 이름은 문자로 시작해야 하며, 문자, 숫자, 밑줄 기호 _만 포함할 수 있습니다.
- 소문자와 대문자는 다른 문자로 취급됩니다. `name`, `Name`, `NAME` 변수는 모두 다른 변수입니다. 이 규칙에는 몇 가지 예외가 있지만, 지금은 무시하겠습니다.
- 파이썬에서는 변수 이름에 소문자만 사용하는 것이 일반적인 프로그래밍 관례입니다. 변수 이름이 여러 단어로 구성된 경우, 단어 사이에 밑줄 기호를 사용합니다. 이 규칙에도 몇 가지 예외가 있지만, 지금은 무시하겠습니다.

### 정수

지금까지는 변수에 문자열만 저장했지만, 나중에 저장하고 접근하고 싶은 다른 유형의 정보도 많이 있습니다. 먼저 정수를 살펴보겠습니다. 정수는 `-15`, `0`, `1`과 같이 소수점이나 분수 부분이 없는 숫자입니다.

다음 프로그램은 정수 값을 포함하는 `age` 변수를 만듭니다.

```python
age = 24
print(age)
```

프로그램은 다음과 같이 출력합니다:

```
24
```

여기서 따옴표가 없다는 점에 주목하세요. 사실, 숫자 주위에 따옴표를 추가하면 변수는 더 이상 정수가 아니라 문자열이 됩니다. 문자열은 숫자를 포함할 수 있지만, 다르게 처리됩니다.

그렇다면, 다음 프로그램이 여전히 같은 것을 두 번 출력하는데 왜 변수에 타입(자료형)이 있다는 것이 중요할까요?

```python
number1 = 100
number2 = "100"

print(number1)
print(number2)
```

```
100
100
```

변수 타입이 중요한 이유는 다른 연산이 다른 타입의 변수에 다른 방식으로 영향을 미치기 때문입니다. 예제를 살펴보겠습니다:

```python
number1 = 100
number2 = "100"

print(number1 + number1)
print(number2 + number2)
```

이 코드는 다음을 출력합니다:

```
200
100100
```

정수 값의 경우 `+` 연산자는 덧셈을 의미하지만, 문자열 값의 경우에는 연결, 즉 "문자열 이어붙이기"를 의미합니다.

모든 연산자가 모든 타입의 변수에 사용 가능한 것은 아닙니다. 숫자는 나눗셈 연산자 `/`를 사용하여 나눌 수 있지만, 문자열을 숫자로 나누려고 하면 에러가 발생합니다:

```python
number = "100"
print(number / 2)
```

```
TypeError: unsupported operand type(s) for /: 'str' and 'int'
```

### 출력 시 값 결합하기

마찬가지로, `"The result is "`와 `result`가 서로 다른 두 타입이기 때문에 다음 프로그램은 작동하지 않습니다:

```python
result = 10 * 25
# 다음 줄은 에러를 발생시킵니다
print("The result is " + result)
```

프로그램은 아무것도 출력하지 않고 대신 에러를 발생시킵니다:

```
TypeError: unsupported operand type(s) for +: 'str' and 'int'
```

여기서 파이썬은 서로 다른 타입의 값을 그냥 결합할 수는 없다고 알려줍니다. 이 경우, `"The result is "`는 문자열 타입이고, `result`에 저장된 값은 정수 타입입니다.

만약 하나의 명령어로 문자열과 정수를 함께 출력하고 싶다면, `str` 함수를 사용하여 정수를 문자열로 형 변환한 다음 두 문자열을 정상적으로 결합할 수 있습니다. 예를 들어, 이렇게 하면 작동합니다:

```python
result = 10 * 25
print("The result is " + str(result))
```

```
The result is 250
```

`print` 함수에는 다른 타입의 값 결합을 지원하는 내장 기능도 있습니다. 가장 간단한 방법은 값 사이에 쉼표를 추가하는 것입니다. 모든 값은 타입에 관계없이 출력됩니다:

```python
result = 10 * 25
print("The result is", result)
```

```
The result is 250
```

여기서는 쉼표로 구분된 값 사이에 공백 문자가 자동으로 추가된 것을 확인하세요.

### f-string로 출력하기

출력하는 내용에 대해 더 많은 유연성과 제어권을 원한다면 어떻게 해야 할까요? 소위 _f-strings_ 은 파이썬에서 출력 서식을 지정하는 또 다른 방법입니다. 문법이 처음에는 약간 혼란스러워 보일 수 있지만, 결국 f-string은 텍스트 서식을 지정하는 가장 간단한 방법인 경우가 많습니다.

f-string을 사용하면 이전 예제는 다음과 같이 보입니다:

```python
result = 10 * 25
print(f"The result is {result}")
```

이것을 분해해 봅시다. 출력하려는 문자열의 맨 처음에 _f_ 문자가 있습니다. 이것은 다음에 오는 것이 f-string임을 파이썬에게 알려줍니다. 문자열 내에서 중괄호로 묶인 곳에 변수 이름 `result`가 있습니다. 이 변수가 포함하는 값이 출력된 문자열의 일부가 됩니다. 출력 결과는 이전 예제들과 정확히 동일합니다:

```
The result is 250
```

단일 f-string은 여러 변수를 포함할 수 있습니다. 예를 들어, 이 코드는

```python
name = "Mark"
age = 37
city = "Palo Alto"
print(f"안녕하세요 {name}님, 당신은 {age}살입니다. 당신은 {city}에 삽니다.")
```

다음과 같이 출력합니다:

```
Hi Mark, you are 37 years old. You live in Palo Alto.
```

`print` 함수의 쉼표 표기법을 사용하여 이와 똑같은 출력물을 만들기는 어렵습니다. 예를 들어, 이 프로그램은

```python
name = "Mark"
age = 37
city = "Palo Alto"
print("Hi", name, ", you are", age, "years old. You live in", city, ".")
```

다음과 같이 출력합니다:

```
Hi Mark , you are 37 years old. You live in Palo Alto .
```

출력물의 쉼표로 구분된 각 부분 사이에 자동으로 삽입된 공백에 주목하세요. `print`가 추가 공백을 넣지 못하게 하는 것은 기술적으로 가능하지만, 대신 f-string을 사용할 수 있다는 점을 고려하면 그럴 가치가 없습니다.

`print` 함수의 쉼표 표기법은 단순함 덕분에 유용할 때가 많지만, 때로는 그 가치보다 더 많은 문제를 일으키기도 합니다. f-string은 일반적으로 더 신뢰할 수 있는 옵션입니다. 파트 4에서는 출력 서식 지정과 관련하여 f-string의 편리한 기능에 대해 더 자세히 배울 것입니다.

### f-string과 파이썬 버전

이전 버전의 파이썬을 사용하고 있다면 f-string이 작동하지 않을 수 있습니다. f-string은 파이썬 버전 3.6에서 도입되었습니다. 과정 후반부에 자신의 컴퓨터에 파이썬을 설치하게 될 것입니다. 안타깝게도 최신 버전의 파이썬이 구형 운영 체제에서는 항상 사용 가능한 것은 아닙니다. 만약 자신의 컴퓨터가 그런 경우라면, f-string 사용이 필요한 연습 문제가 있을 때 이 과정의 초기 파트에 있는 브라우저 내 연습 문제 템플릿에서 언제든지 시도해 볼 수 있습니다.

### 부동 소수점
 
`부동 소수점 숫자` 또는 _float_ 는 프로그래밍에서 자주 접하게 될 용어입니다. 소수점이 있는 숫자를 가리킵니다. 정수 값과 거의 같은 방식으로 사용할 수 있습니다.
 
이 프로그램은 세 개의 부동 소수점 숫자의 평균을 계산합니다:
 
```py
number1 = 2.5
number2 = -1.25
number3 = 3.62

mean = (number1 + number2 + number3) / 3
print(f"Mean: {mean}")
```

 
```
Mean: 1.6233333333333333
```

## 산술 연산

이전 섹션에서 기본적인 산술 연산 예제를 보았습니다. 다음 표는 파이썬에서 가장 흔히 사용되는 산술 연산자와 그 예시입니다:

| 연산자 | 목적 | 예시 | 결과 |
| --- | --- | --- | --- |
| `+`   | 덧셈 | `2 + 4` | `6`   |
| `\-`  | 뺄셈 | `10 - 2.5` | `7.5` |
| `\*`  | 곱셈 | `\-2 \* 123` | `\-246` |
| `/`   | 나눗셈 (부동소수점 결과) | `9 / 2` | `4.5` |
| `//`  | 나눗셈 (정수 결과) | `9 // 2` | `4`   |
| `%`   | 나머지 | `9 % 2` | `1`   |
| `\*\*` | 거듭제곱 | `2 \*\* 3` | `8`   |

연산 순서는 수학에서 익숙한 방식과 같습니다: 먼저 거듭제곱을 계산하고, 그 다음 곱셈과 나눗셈, 마지막으로 덧셈과 뺄셈을 계산합니다. 괄호를 사용하여 순서를 변경할 수 있습니다.

예를 들어, 다음 코드는

```python
print(2 + 3 * 3)
print((2 + 3) * 3)
```

다음과 같이 출력합니다.

```
11
15
```

### 피연산자, 연산자 및 데이터 타입

계산은 보통 **피연산자(operands)**와 **연산자(operators)**로 구성됩니다:
![](https://programming-25.mooc.fi/static/f717f6a68e7b1bd3b3fb9cbe2898da5b/9cb4e/1_4_1.png)


피연산자의 데이터 타입은 일반적으로 결과의 데이터 타입을 결정합니다: 두 정수를 더하면 결과도 정수가 됩니다. 부동소수점 수에서 다른 부동소수점 수를 빼면 결과는 부동소수점 수가 됩니다. 사실, 표현식의 피연산자 중 하나라도 부동소수점 수이면 다른 피연산자와 관계없이 결과는 부동소수점 수가 됩니다.

나눗셈 연산자 `/`는 이 규칙의 예외입니다. 피연산자가 정수이더라도 결과는 부동소수점 수가 됩니다. 예를 들어 `1 / 5`는 부동소수점 수 `0.2`가 됩니다.

예시:

```python
height = 172.5
weight = 68.55

# the Body Mass Index, or BMI, is calculated by dividing body mass with the square of height
# height is converted into metres in the formula
bmi = weight / (height / 100) ** 2

print(f"The BMI is {bmi}")
```

이 프로그램은 다음을 출력합니다:

```
The BMI is 23.037177063642087
```

파이썬에는 정수 나눗셈 연산자 `//`도 있습니다. 피연산자가 정수이면 정수를 생성합니다. 결과는 가장 가까운 정수로 내림됩니다. 예를 들어 다음 프로그램은

```python
x = 3
y = 2
print(f"/ 연산자 {x/y}")
print(f"// 연산자 {x//y}")
```

다음과 같이 출력합니다.

```
/ operator 1.5
// operator 1
```

### 숫자를 입력으로 받기

우리는 이미 `input` 명령어를 사용하여 사용자로부터 문자열을 읽어왔습니다. 동일한 함수를 사용하여 숫자를 읽어올 수도 있지만, 이 함수가 생성하는 문자열은 프로그램 코드 내에서 숫자 데이터 타입으로 변환해야 합니다. 이전 섹션에서는 `str` 함수를 사용하여 정수를 문자열로 형 변환했습니다. 여기서도 동일한 기본 원리가 적용되지만, 형 변환 함수의 이름이 다릅니다.

문자열은 `int` 함수를 사용하여 정수로 변환할 수 있습니다. 다음 프로그램은 사용자에게 출생 연도를 묻고 이를 `input_str` 변수에 저장합니다. 그런 다음 프로그램은 연도를 정수로 변환한 `year`라는 또 다른 변수를 만듭니다. 이후 사용자가 제공한 값을 사용하여 `2021-year` 계산이 가능해집니다.

```python
input_str = input("Which year were you born? ")
year = int(input_str)
print(f"Your age at the end of the year 2021: {2021 - year}" )
```

```
Which year were you born? 1995
Your age at the end of the year 2021: 26
```

일반적으로 사용자로부터 숫자 값을 읽기 위해 두 개의 개별 변수(위의 `input_str` 및 `year`처럼)를 만들 필요는 없습니다. 대신, `input` 함수로 입력을 읽고 `int` 함수로 변환하는 것을 한 번에 수행할 수 있습니다:

```python
year = int(input("Which year were you born? "))
print(f"Your age at the end of the year 2021: {2021 - year}" )
```

마찬가지로, 문자열은 `float` 함수를 사용하여 부동소수점 수로 변환할 수 있습니다. 이 프로그램은 사용자에게 키와 몸무게를 묻고 이를 사용하여 BMI를 계산합니다:

```python
height = float(input("What is your height? "))
weight = float(input("What is your weight? "))

height = height / 100
bmi = weight / height ** 2

print(f"The BMI is {bmi}")
```

프로그램의 예시 출력:

```
What is your height? 163↵
What is your weight? 74.45↵
The BMI is 28.02137829801649
```

### 변수 사용하기

사용자로부터 세 개의 숫자를 입력받아 그 합계를 계산하는 프로그램을 살펴봅시다:

```python
number1 = int(input("First number: "))
number2 = int(input("Second number: "))
number3 = int(input("Third number: "))

sum = number1 + number2 + number3
print(f"The sum of the numbers: {sum}")
```

프로그램 실행 예시:

```
First number: 5↵
Second number: 21↵
Third number: 7↵
The sum of the numbers: 33
```

이 프로그램은 네 개의 다른 변수를 사용하지만, 이 경우에는 두 개만으로도 충분합니다:

```python
sum = 0

number = int(input("First number: "))
sum = sum + number

number = int(input("Second number: "))
sum = sum + number

number = int(input("Third number: "))
sum = sum + number

print(f"The sum of the numbers: {sum}")
```

이제 사용자의 모든 입력은 `number`라는 하나의 동일한 변수로 읽어들입니다. `sum` 변수의 값은 사용자가 새로운 숫자를 입력할 때마다 `number` 변수의 값만큼 _증가_ 합니다.

다음 명령어를 자세히 살펴봅시다:

```python
sum = sum + number
```

여기서는 `sum` 변수의 값과 `number` 변수의 값을 더한 다음, 그 결과를 다시 `sum` 변수에 저장합니다. 예를 들어, 이 명령어를 실행하기 전에 `sum`의 값이 3이고 `number`의 값이 2였다면, 명령어를 실행한 후 `sum`의 값은 5가 됩니다.

변수의 값을 증가시키는 것은 매우 흔한 연산입니다. 따라서 위에서 명시적으로 합계를 구하는 것과 동일한 결과를 얻는 데 흔히 사용되는 축약 표기법이 있습니다:

```python
sum += number
```

이를 사용하면 위의 프로그램을 좀 더 간결하게 작성할 수 있습니다:

```python
sum = 0

number = int(input("First number: "))
sum += number

number = int(input("Second number: "))
sum += number

number = int(input("Third number: "))
sum += number

print(f"The sum of the numbers: {sum}")
```

사실, `number` 변수가 반드시 필요한 것은 아닙니다. 사용자 입력은 다음과 같이 처리할 수도 있습니다:

```python
sum = 0

sum += int(input("First number: "))
sum += int(input("Second number: "))
sum += int(input("Third number: "))

print(f"The sum of the numbers: {sum}")
```

물론, 얼마나 많은 변수가 필요한지는 상황에 따라 다릅니다. 사용자가 입력한 각 값을 기억해야 한다면, 동일한 변수를 "재사용"하여 다른 값을 읽어들일 수는 없습니다. 다음을 고려해 보세요:

```python
number1 = int(input("First number: "))
number2 = int(input("Second number: "))

print(f"{number1} + {number2} = {number1+number2}")
```

```
First number: 2↵
Second number: 3↵
2 + 3 = 5
```

반면에, 위 프로그램은 두 값의 합계를 저장하기 위한 이름 있는 변수가 없습니다.

변수를 "재사용"하는 것은 숫자를 합산하는 경우와 같이 비슷한 유형과 목적의 데이터를 임시로 저장해야 할 때만 의미가 있습니다.

다음 예제에서는 `data` 변수를 사용하여 먼저 사용자의 이름을 저장한 다음, 나이를 저장합니다. 이는 전혀 합리적이지 않습니다.

```python
data = input("What is your name? ")
print("Hi " + data + "!")

data = int(input("What is your age? "))
# 프로그램 계속...
```

더 나은 방법은 **설명적인** 이름을 가진 별도의 변수를 사용하는 것입니다:

```python
name = input("What is your name? ")
print("Hi " + name + "!")

age = int(input("What is your age? "))
# program continues...
```

## 조건문
지금까지 우리가 작성한 모든 프로그램은 순서대로 한 줄씩 실행되었습니다. 프로그램이 실행될 때마다 모든 코드 줄을 실행하는 대신, 특정 상황에서만 실행되는 프로그램 섹션을 만드는 것이 유용할 때가 많습니다.

예를 들어, 다음 코드는 사용자가 성인인지 확인합니다:

```python
age = int(input("How old are you? "))

if age > 17:
    print("You are of age!")
    print("Here's a copy of GTA6 for you.")

print("Next customer, please!")
```

사용자가 17세 초과일 경우, 프로그램 실행은 다음과 같아야 합니다:

```
How old are you? 18↵
You are of age!
Here's a copy of GTA6 for you.
Next customer, please!
```

사용자가 17세 이하일 경우, 다음과 같이 출력됩니다:


```
How old are you? 16↵
Next customer, please!
```

이 예시들은 입력된 값이 프로그램의 어느 부분이 실행될지에 영향을 미친다는 것을 보여줍니다. 이 프로그램에는 _조건문_ 이 포함되어 있으며, 이 문장의 조건이 참(true)일 경우에만 실행되는 코드 블록이 있습니다.

![](https://programming-25.mooc.fi/static/416cb381134e2a6b8d72caecc6260d5a/30f41/1_5_1.webp)

조건문에서는 `if` 키워드 뒤에 두 값의 비교와 같은 _조건_ 이 따릅니다. 이 헤더 라인 다음에 오는 코드 블록은 조건이 참일 경우에만 실행됩니다.

`if` 헤더 뒤에 콜론 문자(`:`)가 오는 것을 주목하세요. 다음 코드에는 콜론이 없습니다:

```python
age = 10

# no colon at the end of the following line
if age > 17
    print("You are of age.")
```

이를 실행하면 오류가 발생합니다:


```
File "program.py", line 3
  if age > 17
            ^
SyntaxError: invalid syntax
```

### 비교 연산자

매우 일반적으로 조건은 두 값을 비교하는 것으로 구성됩니다. 다음은 파이썬에서 사용되는 가장 일반적인 비교 연산자 표입니다:

| 연산자 | 목적 | 예시 |
| --- | --- | --- |
| `\==` | 같음 | `a == b` |
| `!=`  | 같지 않음 | `a != b` |
| `\>`  | 보다 큼 | `a > b` |
| `\>`= | 보다 크거나 같음 | `a >= b` |
| `<`   | 보다 작음 | `a < b` |
| `<=`  | 보다 작거나 같음 | `a <= b` |

사용자가 입력한 숫자가 음수인지, 양수인지, 또는 0인지에 따라 다른 내용을 출력하는 프로그램을 살펴보겠습니다:

```python
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative.")

if number > 0:
    print("The number is positive.")

if number == 0:
    print("The number is zero.")
```

세 가지 다른 입력에 대한 프로그램 작동 예시입니다:


```
Please type in a number: 15↵
The number is positive.
```


```
Please type in a number: -18↵
The number is negative.
```


```
Please type in a number: 0↵
The number is zero.
```

### 들여쓰기

파이썬은 코드 블록의 각 코드 줄이 동일하게 _들여쓰기_ 되어 있으면 해당 블록이 조건문의 일부임을 인식합니다. 즉, 코드 블록 내의 모든 코드 줄 시작 부분에 약간의 공백 문자가 있어야 합니다. 각 줄은 동일한 양의 공백 문자를 가져야 합니다.

예를 들어:

```python
password = input("Please type in a password: ")

if password == "kittycat":
    print("You knew the password!")
    print("You must be either the intended user...")
    print("...or quite an accomplished hacker.")

print("The program has finished its execution. Thanks and bye!")
```

_키_(tabulator key의 약자)를 사용하여 정해진 양의 공백 문자를 삽입할 수 있습니다.

![](https://programming-25.mooc.fi/static/43a34a2e4b0bc023009954d6f7809f7c/27c24/1_5_keyboard.webp)

많은 텍스트 편집기는 콜론 문자 뒤에서 Enter 키를 누르면 다음 줄을 자동으로 들여씁니다. 들여쓴 코드 블록을 끝내고 싶을 때는 _백스페이스_ 키를 사용하여 줄의 시작 부분으로 돌아갈 수 있습니다.

![](https://programming-25.mooc.fi/static/7f8b7a68350e9455732bc0462f21ccff/2b735/1_5_keyboard2.webp)

### Boolean 값과 Boolean 표현식

조건문에서 사용되는 모든 조건은 참 또는 거짓이라는 진리값을 가집니다. 예를 들어, `a < 5`라는 조건은 `a`가 5보다 작으면 참(true)이고, `a`가 5 이상이면 거짓(false)입니다.

이러한 유형의 값은 영국의 수학자 조지 불(George Boole)의 이름을 따서 흔히 _Boolean(Boolean)_ 값이라고 부릅니다. 파이썬에서는 `bool` 데이터 타입으로 처리됩니다. `bool` 타입의 변수는 `True` 또는 `False` 두 가지 값만 가질 수 있습니다.

Boolean 값을 결과로 내는 코드 조각을 _Boolean 표현식(Boolean expression)_ 이라고 합니다. 예를 들어, 조건문의 조건은 항상 Boolean 표현식이며, _조건(condition)_ 과 _Boolean 표현식(Boolean expression)_ 이라는 단어는 종종 같은 의미로 사용될 수 있습니다.

Boolean 표현식의 결과는 수치 계산 결과와 마찬가지로 변수에 저장할 수 있습니다:

```python
a = 3
condition = a < 5
print(condition)
if condition:
    print("a is less than 5")
```


```
True
a is less than 5
```

파이썬 키워드 `True`와 `False`는 직접 사용할 수도 있습니다. 다음 예제에서는 조건의 값이 `True`이기 때문에 `print` 명령이 항상 실행됩니다:

```python
condition = True
if condition:
    print("This is printed every time.")
```


```
This is printed every time.
```

이런 프로그램은 그다지 유용하지 않지만, 과정 후반부에서 Boolean 변수가 매우 유용하게 사용되는 예시를 보게 될 것입니다.