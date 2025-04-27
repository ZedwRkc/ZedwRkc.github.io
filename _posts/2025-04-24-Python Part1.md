---
title: Part1
date: 2025-04-24
categories: [Python]
tags: [Python]
math: true
---
## 1. 시작하기

컴퓨터 프로그램은 _명령어_ 로 구성되며, 각 명령어는 컴퓨터에게 어떤 행동을 취하도록 지시합니다. 컴퓨터는 이 명령어들을 하나씩 실행합니다. 다른 것들 중에서도, 명령어는 계산을 수행하고, 컴퓨터 메모리의 내용을 비교하고, 프로그램 작동 방식에 변화를 일으키고, 메시지를 전달하거나 프로그램 사용자에게 정보를 요청하는 데 사용될 수 있습니다.

텍스트를 _출력_하는 `print` 명령어에 익숙해지는 것으로 프로그래밍을 시작해 봅시다. 이러한 맥락에서, 출력한다는 것은 기본적으로 프로그램이 화면에 어떤 텍스트를 보여줄 것이라는 것을 의미합니다.

다음 프로그램은 "Hi there!" 줄을 출력합니다:

```py 
print("Hi there!")
```
프로그램이 실행되면 다음과 같이 생성됩니다:
 
```
Hi there!
```

코드가 위에 있는 그대로 정확하게 작성되지 않으면 프로그램은 작동하지 않습니다. 예를 들어, 다음과 같이 따옴표 없이 print 명령을 실행하려고 하면

```py 
print(Hi there!)
```
메시지를 출력하지 않고 대신 오류가 발생합니다:
 
```
File "", line 1
print(Hi there!)
^
SyntaxError: invalid syntax
```
요약하면, 텍스트를 인쇄하려면 텍스트 전체를 따옴표로 묶어야 합니다. 그렇지 않으면 파이썬이 올바르게 해석하지 못합니다.

### 여러 명령어의 프로그램
 
연속으로 작성된 여러 명령어는 처음부터 마지막 순서대로 실행됩니다. 예를 들어 이 프로그램은

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
 
`print` 명령어 안에 산술 연산을 넣을 수도 있습니다. 실행하면 연산 결과가 출력됩니다. 예를 들어, 다음 프로그램은

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

위의 산술 연산 주위에 따옴표가 없는 것을 주목하십시오.
따옴표는 _문자열_ 을 나타내는 데 사용됩니다.
프로그래밍 맥락에서 문자열은 문자의 시퀀스입니다.
문자열은 글자, 숫자 및 구두점과 같은 다른 모든 유형의 문자로 구성될 수 있습니다.
문자열은 우리가 일반적으로 이해하는 단어일 뿐만 아니라, 대신 단일 문자열은 여러 개의 완전한 문장만큼 길 수 있습니다.
문자열은 일반적으로 작성된 그대로 출력됩니다.
따라서 다음 두 명령어는 상당히 다른 두 가지 결과를 생성합니다:

```py
print(2 + 2 * 10)
print("2 + 2 * 10")
```
이 프로그램은 출력합니다:

``` 
22
2 + 2 * 10
```

두 번째 코드 줄에서는, 파이썬은 연산의 결과를 계산하지 않고, 대신에 연산 자체를 문자열로서 출력합니다. 그래서, 문자열은 그 내용에 대한 어떠한 참조 없이, 쓰여진 그대로 출력됩니다.

### 주석 달기
파운드 기호 `#` (해시 또는 숫자 기호라고도 함)로 시작하는 모든 줄은 주석입니다. 이는 `#` 기호 뒤에 오는 해당 줄의 모든 텍스트가 프로그램 작동 방식에 어떤 식으로든 영향을 미치지 않음을 의미합니다. 파이썬은 이를 단순히 무시할 것입니다.
 
주석은 프로그래머 자신과 프로그램 코드를 읽는 다른 사람 모두에게 프로그램 작동 방식을 설명하는 데 사용됩니다. 이 프로그램에서는 주석이 코드에서 수행된 계산을 설명합니다:

```py
print("Hours in a year:")
# there are 365 days in a year and 24 hours in each day
print(365*24)
```

프로그램이 실행될 때, 주석은 사용자에게 보이지 않을 것입니다:

```py
Hours in a year:
8760
```

짧은 주석들은 또한 한 줄의 끝에 추가될 수 있습니다:
```py
print("Hours in a year:")
print(365*24) # 365 days, 24 hours in each day
```

## 2. 사용자로부터의 정보

_입력_ 은 사용자가 프로그램에 제공하는 모든 정보를 의미합니다. 구체적으로, 파이썬 명령어 `input`은 사용자가 입력한 한 줄의 입력을 읽어들입니다. 또한 사용자에게 메시지를 표시하여 특정 입력을 유도하는 데 사용될 수도 있습니다.
 
다음 프로그램은 `input` 명령어를 사용하여 사용자의 이름을 읽어들입니다. 그런 다음 `print` 명령어로 그것을 출력합니다:
```py
name = input("What is your name? ")
print("Hi there, " + name)
```

이 프로그램의 실행은 다음과 같을 수 있습니다 (사용자로부터의 입력은 빨간색으로 표시):

```
What is your name? Paul Python↵
Hi there, Paul Python
```

이 프로그램이 출력하는 내용은 부분적으로 사용자로부터의 입력에 따라 달라집니다. 이는 즉 프로그램의 실행이 다음과 같을 수도 있다는 것을 의미합니다:

```
What is your name? Paula Programmer↵
Hi there, Paula Programmer
```

이 프로그램에서 단어 `name`은 _변수_ 입니다. 프로그래밍의 맥락에서, _변수_ 는 문자열이나 숫자와 같은 어떤 값을 저장하기 위한 위치입니다. 이 값은 나중에 사용될 수 있으며, 변경될 수도 있습니다.

>**변수 이름 짓기**<br>
원칙적으로, 변수는 파이썬 언어에 명시된 특정 제한 내에서 상당히 자유롭게 이름을 지을 수 있습니다.<br>
<br> 
변수 이름을 영어로 짓는 것이 일반적인 국제 프로그래밍 관행이지만, 프로그래머의 모국어와 같은 다른 언어로 변수 이름이 지어진 코드를 접할 수도 있습니다. 변수의 이름은 그 내용에 직접적인 영향을 미치지 않으므로, 그런 의미에서 이름은 중요하지 않습니다. 하지만, 변수 이름이 논리적으로 그리고 영어로 지어지면 코드가 어떻게 작동하는지 이해하는 데 종종 도움이 될 수 있습니다.

### 변수 참조

단일 변수는 프로그램 내에서 여러 번 참조될 수 있습니다:

```py
name = input("What is your name? ")

print("Hi, " + name + "!")
print(name + " is quite a nice name.")
```
 
사용자가` Paul Python`이라는 이름을 입력하면, 이 프로그램은 다음을 출력합니다:

```
What is your name? Paul Python↵
Hi, Paul Python!
Paul Python is quite a nice name.
```
`print` 명령어 위에서 사용된 방식을 좀 더 자세히 살펴보겠습니다. 명령어의 괄호 안에는 따옴표로 묶인 텍스트와 사용자 입력을 참조하는 변수 이름이 모두 있습니다. 이것들은 `+` 연산자로 결합되었으며, 이는 두 문자열을 단일 문자열로 연결합니다.
 
문자열과 변수는 꽤 자유롭게 결합될 수 있습니다:
```py
name = input("What is your name? ")

print("Hi " + name + "! Let me make sure: your name is " + name + "?")
```

 
사용자가 `Ellen Example`이라는 이름을 입력하면 이것은 다음을 출력합니다
```
What is your name? Ellen Example↵
Hi Ellen Example! Let me make sure: your name is Ellen Example?
```

### 하나 이상의 입력

프로그램은 하나 이상의 입력을 요청할 수 있습니다. 아래에서 각 `input` 명령이 수신된 값을 어떻게 다른 변수에 저장하는지 주목하십시오.
```py
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
Let's make sure we got this right
Your name: Frances Fictitious
Your email address: frances99@example.com
Your nickname: Fran
```
동일한 변수가 둘 이상의 입력을 저장하는 데 사용되면 각 새 값은 이전 값을 대체합니다. 예를 들어:

```py
address = input("What is your address? ")
print("So you live at address " + address)

address = input("Please type in a new address: ")
print("Your address is now " + address)
```

프로그램의 실행 예:

```
What is your address? Python Path 101, Flat 3D↵
So you live at address Python Path 101, Flat 3D
Please type in a new address: New Road 999↵
Your address is now New Road 999
```

이는 동일한 변수가 연속으로 두 입력을 저장하는 데 사용되면 두 번째 값으로 대체된 후 첫 번째 입력 값에 접근할 방법이 없다는 것을 의미합니다:

```py
address = input("What is your address? ")
address = input("Please type in a new address: ")

print("Your address is now " + address)
```
프로그램의 출력이 어떻게 보일 수 있는지에 대한 예:

```
What is your address? Python Path 10↵
Please type in a new address: Programmer's Walk 23↵
Your address is now Programmer's Walk 23
```

## 3. 변수에 대해 더 알아보기

프로그래밍에서 변수는 다양한 목적으로 필요합니다. 프로그램 실행 중 나중에 필요할 모든 정보를 저장하기 위해 변수를 사용할 수 있습니다.
 
파이썬 프로그래밍에서 변수는 다음과 같이 생성됩니다:
 
`variable_name = ...`
 
여기서 `...`는 변수에 저장된 값을 의미합니다.
 
예를 들어, 사용자로부터 문자열을 읽기 위해 `input` 명령어를 사용했을 때, 당신은 문자열을 변수에 저장했고 그리고 나중에 프로그램에서 그 변수를 사용했습니다:

```py
name = input("What is your name? ")
print("Hi, " + name)
```

```
What is your name? Ghosty↵
Hi, Ghosty
```

변수에 저장된 값은 다른 변수를 사용하여 또한 정의될 수 있습니다:

```py
given_name = "Paul"
family_name = "Python"

name = given_name + " " + family_name

print(name)
```

```
Paul Python
```
여기서 세 변수에 저장된 값들은 사용자 입력으로부터 얻어지는 것이 아닙니다.
그것들은 프로그램이 실행될 때마다 그대로 유지됩니다.
이것을 프로그램에 데이터를 _하드-코딩_ 한다고 합니다.

### 변수 값 변경하기
 
_변수_ 라는 이름에서 알 수 있듯이, 변수에 저장된 값은 변경될 수 있습니다. 이전 섹션에서 우리는 새로운 값이 이전 값을 대체한다는 것을 확인했습니다.
 
다음 프로그램의 실행 동안, `word` 변수는 세 가지 다른 값을 갖게 됩니다:

```py
word = input("Please type in a word: ")
print(word)

word = input("And another word: ")
print(word)

word = "third"
print(word)
```

```
Please type in a word: first
first
And another word: second
second
third
```

변수에 저장된 값은 변수에 새로운 값이 할당될 때마다 변경됩니다.
 
변수의 새로운 값은 그것의 이전 값으로부터 파생될 수 있습니다. 다음 예시에서 변수 `word`는 먼저 사용자 입력을 기반으로 한 값이 할당됩니다. 그런 다음 그것에는 새로운 값이 할당되는데, 이는 이전 값의 끝에 느낌표 세 개가 추가된 값입니다.

```py
word = input("Please type in a word: ")
print(word)

word = word + "!!!"
print(word)
```

```
Please type in a word: test
test
test!!!
```

>**변수에 좋은 이름 선택하기** <br>
- 변수의 이름은 그것이 무엇에 사용되는지에 따라 짓는 것이 종종 유용합니다. 예를 들어, 변수가 단어를 포함한다면, 이름 `word`가 가령 `a`보다 더 나은 선택입니다.<br>
<br>
- 파이썬에서 변수 이름의 길이에 정해진 제한은 없지만, 몇 가지 다른 제한 사항이 있습니다. 변수 이름은 문자로 시작해야 하며, 문자, 숫자, 그리고 밑줄 _ 만 포함할 수 있습니다.<br> 
<br>
- 소문자와 대문자는 다른 문자입니다. 변수 `name`, `Name`, `NAME`은 모두 다른 변수입니다. 이 규칙에는 몇 가지 예외가 있지만, 지금은 그것들을 무시하겠습니다.<br>
<br>
- 파이썬에서는 변수 이름에 소문자만 사용하는 것이 일반적인 프로그래밍 관행입니다. 변수 이름이 여러 단어로 구성된 경우, 단어 사이에 밑줄을 사용합니다. 이 규칙에도 몇 가지 예외가 있지만, 지금은 그것들을 무시하겠습니다.


### 정수
지금까지, 우리는 변수에 문자열만 저장했지만, 나중에 저장하고 접근하고 싶을 다른 많은 종류의 정보도 있습니다. 먼저 정수를 살펴봅시다. 정수는 `-15`, `0`, `1`과 같이 소수점이나 분수 부분이 없는 숫자입니다.
 
다음 프로그램은 정수 값을 포함하는 `age` 변수를 생성합니다.

```py
age = 24
print(age)
```

프로그램은 딱 이것만 출력합니다:
```
24
```

여기에 따옴표가 없는 것을 주목하세요. 사실, 숫자를 따옴표로 묶으면 변수는 더 이상 정수가 아니라 문자열이 됩니다. 문자열은 숫자를 포함할 수 있지만 다르게 처리됩니다.
 
그렇다면, 다음 프로그램이 여전히 같은 것을 두 번 출력하는데 변수에 유형이 있다는 것이 왜 중요할까요?

```py
number1 = 100
number2 = "100"

print(number1)
print(number2)
```

```
100
100
```

변수 유형은 중요합니다, 왜냐하면 다른 연산들은 다른 유형의 변수들에 다른 방식으로 영향을 미치기 때문입니다. 예시를 살펴봅시다:

```py
number1 = 100
number2 = "100"

print(number1 + number1)
print(number2 + number2)
```

이것은 다음을 출력합니다:

```
200
100100
```

정수 값의 경우 `+` 연산자는 덧셈을 의미하지만, 문자열 값의 경우에는 연결, 즉 "함께 묶기"를 의미합니다.
 
모든 연산자가 모든 유형의 변수에 사용 가능한 것은 아닙니다. 숫자는 나눗셈 연산자 `/`를 사용하여 나눌 수 있지만, 문자열을 숫자로 나누려고 하면 오류가 발생합니다:

```py
number = "100"
print(number / 2)
```

```
TypeError: unsupported operand type(s) for /: 'str' and 'int'
```

### 출력할 때 값 결합하기
 
마찬가지로, 다음 프로그램은 작동하지 않을 것입니다, 왜냐하면 `"The result is "`와 `result`는 두 개의 다른 유형이기 때문입니다:

```py
result = 10 * 25
# the following line produces an error
print("The result is " + result)
```
프로그램은 아무것도 출력하지 않고, 대신 오류를 발생시킵니다:
```
TypeError: unsupported operand type(s) for +: 'str' and 'int'
```

여기서 파이썬은 서로 다른 두 가지 유형의 값을 그대로 결합하는 것은 작동하지 않는다고 알려줍니다. 이 경우, `"The result is "`는 문자열 유형이고, 반면 `result`에 저장된 값은 정수 유형입니다.
 
만약 우리가 단일 명령으로 문자열과 정수를 출력하고 싶다면, 정수를 `str` 함수로 문자열로 형 변환한 다음, 두 문자열을 정상적으로 결합할 수 있습니다. 예를 들어, 이것은 작동할 것입니다:

```py
result = 10 * 25
print("The result is " + str(result))
```

`print` 명령어에는 다른 타입의 값들을 결합하는 것을 지원하는 내장 기능 또한 있습니다. 가장 간단한 방법은 값들 사이에 쉼표를 추가하는 것입니다. 모든 값들은 그들의 타입에 관계없이 출력될 것입니다:

```
The result is 250
```

여기에 쉼표로 구분된 값들 사이에는 자동으로 공백 문자가 추가된다는 점을 주목하세요.

### f-문자열을 이용한 출력
 
우리가 출력하는 것에 대해 더 많은 유연성과 제어를 원한다면 어떻게 할까요? 소위 f-문자열은 파이썬에서 출력 형식을 지정하는 또 다른 방법입니다. 구문은 처음에는 약간 혼란스러워 보일 수 있지만, 결국 f-문자열은 종종 텍스트 서식을 지정하는 가장 간단한 방법입니다.
 
f-문자열을 사용하면 이전 예제는 다음과 같이 보일 것입니다:

```py
result = 10 * 25
print(f"The result is {result}")
```

이것을 분해해 봅시다. 우리가 출력하는 문자열의 맨 처음에 문자 $f$가 있습니다. 이것은 파이썬에게 다음에 오는 것이 f-문자열임을 알려줍니다. 문자열 내부에, 중괄호로 둘러싸인 곳에, 변수 이름 `result`가 있습니다. 그것이 포함하는 값은 출력된 문자열의 일부가 됩니다. 출력 결과는 이전 예제들과 정확히 동일합니다:

```
The result is 250
```

하나의 f-문자열은 여러 변수를 포함할 수 있습니다. 예를 들어 이 코드는
```py
name = "Mark"
age = 37
city = "Palo Alto"
print(f"Hi {name}, you are {age} years old. You live in {city}.")
```
이것을 출력합니다:

```py
Hi Mark, you are 37 years old. You live in Palo Alto.
```

`print` 명령어에서 쉼표 표기법을 사용하여 이것과 똑같은 출력물을 만드는 것은 어렵습니다. 예를 들어, 이 프로그램은

```py
name = "Mark"
age = 37
city = "Palo Alto"
print("Hi", name, ", you are", age, "years old. You live in", city, ".")
```
다음을 출력합니다:

```
Hi Mark , you are 37 years old. You live in Palo Alto .
```

출력물의 각 쉼표로 구분된 부분 사이에 자동으로 삽입된 공백을 주목하십시오. `print`가 추가 공백을 더하는 것을 막는 것은 기술적으로 가능하지만, 대신 f-string을 사용할 수 있다는 점을 고려하면 그럴 만한 가치가 없습니다.

`print` 명령어의 쉼표 표기법은 단순함 때문에 종종 유용할 수 있지만, 때로는 그만한 가치보다 더 많은 문제를 일으키기도 합니다. F-string은 일반적으로 더 신뢰할 수 있는 옵션입니다. 파트 4에서는 출력물 서식 지정과 관련하여 f-string의 편리한 기능에 대해 더 자세히 배울 것입니다.

> **f-문자열과 파이썬 버전**<br>
만약 당신이 파이썬의 오래된 버전을 사용하고 있다면, f-문자열은 작동하지 않을 수 있습니다.
그것들은 파이썬 버전 3.6에서 도입되었습니다.
나중에 과정 중에 당신은 당신 자신의 컴퓨터에 파이썬을 설치할 것입니다.
불행하게도, 파이썬의 더 현대적인 버전들은 오래된 운영 체제에서 항상 사용 가능하지는 않습니다.
만약 그것이 당신의 컴퓨터의 경우라면, f-문자열의 사용을 요구하는 연습 문제들이 있을 때, 당신은 언제나 이 과정의 이 초기 부분들에 있는 브라우저 내 연습 템플릿에서 그것들을 시도해 볼 수 있습니다.

### 부동 소수점 숫자
 
`부동 소수점 숫자` 또는 _float_ 는 프로그래밍에서 자주 접하게 될 용어입니다. 소수점이 있는 숫자를 가리킵니다. 정수 값과 거의 동일한 방식으로 사용될 수 있습니다.

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

## 4. 산술 연산
 
이전 섹션들에서는 기본적인 산술 예시들을 보았습니다. 다음 표에서는 파이썬의 가장 흔한 산술 연산자들을 예시와 함께 볼 수 있습니다:

|Operator	|Purpose	|Example	|Result
|----|----|----|----|----|
|`+`	|Addition	|`2 + 4`	|`6`
|`-`	|Subtraction	|`10 - 2.5`	|`7.5`
|`*`	|Multiplication	|`-2 * 123`	|`-246`
|`/`	|Division (floating point result)	|`9 / 2`	|`4.5`
|`//`	|Division (integer result)	|`9 // 2`	|`4`
|`%`	|Modulo	|`9 % 2`	|`1`
|`**`	|Exponentiation	|`2 ** 3`	|`8`

연산 순서는 수학에서 익숙합니다: 먼저 지수를 계산하고, 그 다음 곱셈과 나눗셈을, 그리고 마지막으로 덧셈과 뺄셈을 합니다. 순서는 괄호로 바꿀 수 있습니다.
 
예를 들어 이 코드는
```py
print(2 + 3 * 3)
print((2 + 3) * 3)
```

다음과 같이 출력합니다
```
11
15
```

### 피연산자, 연산자 및 데이터 유형
계산은 보통 피연산자와 연산자로 구성됩니다:

![](https://programming-25.mooc.fi/static/f717f6a68e7b1bd3b3fb9cbe2898da5b/9cb4e/1_4_1.png)

피연산자의 데이터 유형은 일반적으로 결과의 데이터 유형을 결정합니다: 만약 두 개의 정수가 함께 더해지면, 결과도 정수가 될 것입니다. 만약 부동 소수점 숫자가 다른 부동 소수점 숫자에서 빼지면, 결과는 부동 소수점 숫자입니다. 사실, 표현식 내 피연산자 중 단 하나라도 부동 소수점 숫자이면, 다른 피연산자에 관계없이 결과도 부동 소수점 숫자가 될 것입니다.
 
나눗셈 / 은 이 규칙의 예외입니다. 그 결과는 피연산자가 정수일지라도 부동 소수점 숫자입니다. 예를 들어 1 / 5는 부동 소수점 숫자 0.2가 될 것입니다.
 
예시:

```py
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
파이썬은 또한 정수 나눗셈 연산자 //를 가지고 있다는 것을 참고하세요. 피연산자가 정수이면, 정수를 결과로 낼 것입니다. 결과는 가장 가까운 정수로 내림 처리됩니다. 예를 들어 이 프로그램은

```py
x = 3
y = 2

print(f"/ operator {x/y}")
print(f"// operator {x//y}")
```
 
출력합니다

```
/ operator 1.5
// operator 1
```

### 입력으로서의 숫자들
우리는 이미 사용자로부터 문자열들을 읽어들이기 위해 `input` 명령어를 사용했습니다. 동일한 함수가 숫자들을 읽어들이는 데 사용될 수 있지만, 그 함수에 의해 생성된 문자열은 그 다음 프로그램 코드에서 숫자 데이터 유형으로 변환되어야 합니다. 이전 섹션에서 우리는 str 함수를 사용하여 정수들을 문자열들로 형 변환했습니다. 동일한 기본 원칙이 여기에 적용되지만, 형 변환 함수의 이름은 다를 것입니다.
 
문자열은 int 함수를 사용하여 정수로 변환될 수 있습니다. 다음 프로그램은 사용자에게 그들의 출생 연도를 묻고 그것을 변수 `input_str`에 저장합니다. 그 프로그램은 그 다음 다른 변수 `year`를 생성하는데, 그것은 정수로 변환된 연도를 포함합니다. 이후에 사용자 제공 값을 사용하여 `2021-year` 계산이 가능합니다.

```py
input_str = input("Which year were you born? ")
year = int(input_str)
print(f"Your age at the end of the year 2021: {2021 - year}" )
```

```
Which year were you born? 1995↵
Your age at the end of the year 2021: 26
```

일반적으로 사용자로부터 숫자 값을 읽기 위해 (위의 `input_str` 및 `year`와 같이) 두 개의 별도 변수를 생성할 필요는 없습니다. 대신, `input` 함수로 입력을 읽고 `int` 함수로 변환하는 것은 한 번에 수행될 수 있습니다:

```py
year = int(input("Which year were you born? "))
print(f"Your age at the end of the year 2021: {2021 - year}" )
```
마찬가지로, 문자열은 `float` 함수를 사용하여 부동 소수점 숫자로 변환될 수 있습니다. 이 프로그램은 사용자에게 키와 몸무게를 묻고, 이것들을 사용하여 그들의 BMI를 계산합니다:

```py
height = float(input("What is your height? "))
weight = float(input("What is your weight? "))

height = height / 100
bmi = weight / height ** 2

print(f"The BMI is {bmi}")
```
프로그램의 출력 예시:

```py
What is your height? 163↵
What is your weight? 74.45↵
The BMI is 28.02137829801649
```

### 변수 사용하기
사용자가 입력한 세 숫자의 합을 계산하는 프로그램을 살펴봅시다:

```py
number1 = int(input("First number: "))
number2 = int(input("Second number: "))
number3 = int(input("Third number: "))

sum = number1 + number2 + number3
print(f"The sum of the numbers: {sum}")
```

프로그램의 예시 실행:

```
First number: 5
Second number: 21
Third number: 7
The sum of the numbers: 33
```
프로그램은 네 개의 다른 변수를 사용하지만, 이 경우에는 두 개로도 쉽게 충분할 것입니다:
```py
sum = 0

number = int(input("First number: "))
sum = sum + number

number = int(input("Second number: "))
sum = sum + number

number = int(input("Third number: "))
sum = sum + number

print(f"The sum of the numbers: {sum}")
```
이제 사용자의 모든 입력은 `number`라는 하나의 동일한 변수로 읽어들여집니다. 사용자가 새로운 숫자를 입력할 때마다 변수 `sum`의 값은 변수 `number`의 값만큼 증가됩니다.
 
이 명령을 더 자세히 살펴봅시다:
```py
sum = sum + number
```
여기서는 변수 sum의 값과 변수 number의 값이 함께 더해지고, 그 결과가 변수 sum에 다시 저장됩니다. 예를 들어, 명령 전에 sum의 값이 3이고 number의 값이 2라면, 명령이 실행된 후에는 sum의 값은 5가 됩니다.
 
변수의 값을 증가시키는 것은 매우 흔한 연산입니다. 그렇기 때문에, 위에서 명시적으로 합산하는 것과 동일한 결과를 달성하는 흔히 사용되는 축약 표기법이 있습니다:

```py
sum += number
```

이를 통해 위의 프로그램을 조금 더 간결하게 작성할 수 있습니다:

```py
sum = 0

number = int(input("First number: "))
sum += number

number = int(input("Second number: "))
sum += number

number = int(input("Third number: "))
sum += number

print(f"The sum of the numbers: {sum}")
```

사실,`number` 변수가 반드시 필요한 것은 아닙니다.
사용자 입력은 다음과 같이 처리될 수도 있습니다:

```py
sum = 0

sum += int(input("First number: "))
sum += int(input("Second number: "))
sum += int(input("Third number: "))

print(f"The sum of the numbers: {sum}")
```

물론, 얼마나 많은 변수가 필요한지는 맥락에 따라 달라질 것입니다.
사용자가 입력하는 각 값을 기억해야 한다면, 사용자로부터 다른 값들을 읽기 위해 동일한 변수를 "재사용"하는 것은 불가능할 것입니다.
다음을 고려하십시오

```py
number1 = int(input("First number: "))
number2 = int(input("Second number: "))

print(f"{number1} + {number2} = {number1+number2}")
```

```
First number: 2↵
Second number: 3↵
2 + 3 = 5
```
다른 한편으로는, 위의 프로그램은 두 값의 합을 저장하기 위한 이름이 지정된 변수를 가지고 있지 않습니다.
 
변수를 "재사용"하는 것은 예를 들어 숫자를 합산할 때와 같이 비슷한 유형과 목적의 것들을 임시로 저장할 필요가 있을 때만 의미가 있습니다.
 
다음 예제에서는 변수 `data`가 먼저 사용자의 이름을 저장한 다음, 그들의 나이를 저장하는 데 사용됩니다. 이것은 전혀 합리적이지 않습니다.

```py
data = input("What is your name? ")
print("Hi " + data + "!")

data = int(input("What is your age? "))
# program continues...
```
더 나은 아이디어는 별도의 변수를, _설명적인_ 이름과 함께, 사용하는 것입니다:
```py
name = input("What is your name? ")
print("Hi " + name + "!")

age = int(input("What is your age? "))
# program continues...
```

## 5. 조건문

지금까지 우리가 작성한 모든 프로그램은 순서대로 한 줄씩 실행되었습니다. 프로그램이 실행될 때마다 모든 코드 줄을 실행하는 대신에, 특정 상황에서만 실행되는 프로그램의 섹션을 만드는 것이 종종 유용합니다.
 
예를 들어, 다음 코드는 사용자가 성인인지 확인합니다:
```py
age = int(input("How old are you? "))

if age > 17:
    print("You are of age!")
    print("Here's a copy of GTA6 for you.")

print("Next customer, please!")
```
사용자의 나이가 17세를 초과하는 경우, 프로그램 실행은 다음과 같아야 합니다:
```
How old are you? 18
You are of age!
Here's a copy of GTA6 for you.
Next customer, please!
```

사용자의 나이가 17세 이하인 경우, 이것만 출력됩니다:

```py
How old are you? 16
Next customer, please!
```

이 예제들은 입력으로 주어진 값이 프로그램의 어떤 부분들이 실행되는지에 영향을 미친다는 것을 우리에게 보여줍니다. 그 프로그램은 조건문을 포함하며, 그 안의 코드 블록은 오직 그 문장의 조건이 참일 경우에만 실행됩니다.
![](https://programming-25.mooc.fi/static/416cb381134e2a6b8d72caecc6260d5a/30f41/1_5_1.webp)

조건문에서 키워드 if 다음에는 조건이 옵니다, 예를 들어 두 값의 비교와 같은. 이 헤더 라인 다음에 오는 코드 블록은 조건이 참인 경우에만 실행됩니다.
 
if 헤더 다음에 오는 콜론 문자에 주목하십시오. 다음 코드에서는 콜론이 없습니다:
```py
age = 10

# no colon at the end of the following line
if age > 17
    print("You are of age.")
```
실행 시 이것은 오류를 발생시킵니다:
```
File "program.py", line 3
  if age > 17
            ^
SyntaxError: invalid syntax
```

### 비교 연산자
 
매우 일반적으로 조건들은 두 개의 값을 비교하는 것으로 구성됩니다. 여기에 파이썬에서 사용되는 가장 흔한 비교 연산자들이 있는 표가 있습니다:

|Operator	|Purpose	|Example
|----|----|----|----|
|`==`	|Equal to	 |`a == b`
|`!=`	|Not equal to	|`a != b`
|`>`	|Greater than	|`a > b`
|`>=`	|Greater than or equal to	|`a >= b`
|`<`	|Less than	|`a < b`
|`<=`	|Less than or equal to	|`a <= b`

사용자가 입력하는 숫자가 음수인지, 양수인지, 또는 0과 같은지에 따라 다른 것들을 출력하는 프로그램을 살펴봅시다:
 

```py
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative.")

if number > 0:
    print("The number is positive.")

if number == 0:
    print("The number is zero.")
```

세 가지 다른 입력값으로 프로그램이 어떻게 작동하는지에 대한 예시들:

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
 
파이썬은 블록 내의 각 코드 줄이 동일하게 _들여쓰기_된 경우 코드 블록이 조건문의 일부임을 인식합니다. 즉, 코드 블록 내의 모든 코드 줄 시작 부분에 약간의 공백이 있어야 합니다. 각 줄은 동일한 양의 공백을 가져야 합니다.
 
예를 들어:

```py
password = input("Please type in a password: ")

if password == "kittycat":
    print("You knew the password!")
    print("You must be either the intended user...")
    print("...or quite an accomplished hacker.")

print("The program has finished its execution. Thanks and bye!")
```

당신은 Tab 키, _tabulator_ 키의 줄임말인, 를 사용하여 정해진 양의 공백을 삽입할 수 있습니다.

![](https://programming-25.mooc.fi/static/43a34a2e4b0bc023009954d6f7809f7c/27c24/1_5_keyboard.webp)

많은 텍스트 편집기는 콜론 문자 뒤에 `Enter` 키가 눌렸을 때 다음 줄을 자동으로 들여쓰기할 것입니다. 당신이 들여쓰기된 코드 블록을 끝내고 싶을 때 당신은 줄의 시작으로 돌아가기 위해 `Backspace` 키를 사용할 수 있습니다.
![](https://programming-25.mooc.fi/static/7f8b7a68350e9455732bc0462f21ccff/2b735/1_5_keyboard2.webp)

### Boolean 값과 Boolean 표현식
 
조건문에서 사용되는 모든 조건은 진리 값, 즉 참(True) 또는 거짓(False) 중 하나를 결과로 낳습니다. 예를 들어, 조건 `a < 5`는 `a`가 5보다 작으면 참(True)이고, `a`가 5와 같거나 크면 거짓(False)입니다.
 
이러한 유형의 값은 영국의 수학자 조지 불(George Boole)의 이름을 따서 종종 Boolean 값이라고 불립니다. 파이썬에서는 `bool` 데이터 유형으로 처리됩니다. `bool` 유형의 변수는 오직 두 가지 값, 즉 `True` 또는 `False`만 가질 수 있습니다.
 
Boolean 값을 결과로 내는 모든 코드 조각을 _Boolean 표현식_ 이라고 합니다. 예를 들어, 조건문의 조건은 항상 Boolean 표현식이며, _조건_ 과 _Boolean 표현식_ 이라는 단어는 종종 서로 바꿔 사용할 수 있습니다.
 
Boolean 표현식의 결과는 모든 수치 계산의 결과와 마찬가지로 변수에 저장될 수 있습니다:

```py
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

파이썬 키워드 `True`와 `False`도 직접 사용될 수 있습니다. 다음 예제에서는 조건의 값이 `True`이기 때문에 `print` 명령이 매번 실행됩니다:

```py
condition = True
if condition:
    print("This is printed every time.")
```

```
This is printed every time.
```

이와 같은 프로그램은 매우 유용하지는 않지만, 나중에 과정 동안 당신은 불리언 변수가 매우 유용하게 사용되는 예들을 볼 것입니다.