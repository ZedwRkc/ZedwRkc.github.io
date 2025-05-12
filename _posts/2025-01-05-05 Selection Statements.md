---
title: 5장 선택문
date: 2025-01-05
categories: [C]
tags: [C]
math: true
---
C는 많은 연산자를 가지고 있지만, 비교적 적은 수의 **문장(statement)**만을 가지고 있다. 지금까지 우리는 단 두 가지 문장만을 살펴보았다: return 문과 **표현식 문장(expression statement)**이다.
C의 나머지 문장들은 대부분 다음 세 가지 범주 중 하나에 속하며, 각각 문장의 실행 순서에 어떤 방식으로 영향을 주는지에 따라 분류된다:

선택문(Selection statements): if와 switch 문은 여러 실행 경로 중 하나를 선택할 수 있게 해준다.

반복문(Iteration statements): while, do, for 문은 반복(루프)을 지원한다.

점프문(Jump statements): break, continue, goto 문은 프로그램의 다른 위치로 무조건적인 점프를 수행하게 한다. (return 문도 이 범주에 속한다.)

C의 유일한 다른 문장은 다음 두 가지이다:

복합문(compound statement): 여러 문장을 하나의 문장으로 묶는다.

널 문장(null statement): 아무 작업도 수행하지 않는다.

이 장에서는 선택문과 복합문을 다룬다.
(6장은 반복문, 점프문, 그리고 널 문장을 다룬다.)
if 문을 작성하려면 먼저 **논리 표현식(logical expressions)**이 필요하다.
즉, if 문이 판단할 수 있는 **조건(condition)**이 필요하다.

5.1절에서는 <, <=, >, >= 같은 관계 연산자(relational operators), ==, != 같은 동등 연산자(equality operators), 그리고 &&, ||, ! 같은 **논리 연산자(logical operators)**를 사용해 논리 표현식을 어떻게 구성하는지 설명한다.
5.2절에서는 if 문과 복합문을 다루며, 조건을 표현식 내부에서 판단할 수 있게 해주는 **조건 연산자(?:)**도 소개한다.
5.3절에서는 switch 문을 설명한다.

## _**5.1 논리 표현식 (Logical Expressions)**_
C의 여러 문장들—특히 if 문—은 표현식의 값을 평가해서 그 결과가 **"참(true)"**인지 **"거짓(false)"**인지 판단해야 한다.
예를 들어, if 문은 i < j라는 표현식을 평가해야 할 수 있다. 참이면 i가 j보다 작다는 것을 의미한다.

많은 프로그래밍 언어에서는 i < j 같은 표현식이 특수한 "불리언(Boolean)" 또는 "논리(logical)" 타입을 가진다.
이러한 타입은 false와 true라는 두 개의 값만을 가진다.
그러나 C에서는 i < j 같은 비교 연산은 정수값을 생성한다:
0은 거짓(false), 1은 참(true)이다.

이 점을 염두에 두고, 논리 표현식을 구성할 때 사용되는 연산자들을 살펴보자.

관계 연산자 (Relational Operators)
C의 관계 연산자(표 5.1 참조)는 수학에서 사용하는 <, >, ≤, ≥ 연산자에 해당하며,
표현식에서 사용될 때 결과로 0(거짓) 또는 1(참)을 생성한다.
예를 들어:

c
코드 복사
10 < 11   // 값은 1
11 < 10   // 값은 0
표 5.1 — 관계 연산자

기호	의미
<	보다 작다 (less than)
>	보다 크다 (greater than)
<=	작거나 같다
>=	크거나 같다

관계 연산자는 정수와 실수(floating-point)를 비교하는 데 사용할 수 있으며,
혼합 타입(mixed type) 피연산자도 허용된다.
예를 들어:

c
코드 복사
1 < 2.5   // 값은 1  
5.6 < 4   // 값은 0
관계 연산자의 우선순위는 산술 연산자보다 낮다.
예를 들어 i + j < k - 1는 (i + j) < (k - 1)와 동일하다.
관계 연산자는 **왼쪽 결합성(left associative)**을 가진다.

표현식:

c
코드 복사
i < j < k
는 C에서 합법적인 문장이지만, 예상하는 의미와는 다르다.
< 연산자는 왼쪽 결합성을 가지므로 이 표현식은 다음과 같다:

c
코드 복사
(i < j) < k
즉, 먼저 i < j를 평가하여 0 또는 1을 생성하고, 그 값을 다시 k와 비교한다.
이 표현식은 j가 i와 k 사이에 있는지를 테스트하지 않는다.
(이러한 조건은 i < j && j < k로 표현해야 한다.)

동등 연산자 (Equality Operators)
C의 동등 연산자는 다른 많은 언어들과 기호는 유사하지만, 형태는 독특하다 (표 5.2 참조).

같다(equal to) 연산자는 ==이며, =이 아니라 인접한 두 개의 = 문자이다.

같지 않다(not equal to) 연산자는 !=이며, !와 =의 조합이다.

표 5.2 — 동등 연산자

기호	의미
==	같다 (equal to)
!=	다르다 (not equal to)

관계 연산자와 마찬가지로, 동등 연산자는 왼쪽 결합성을 가지며 결과로 0 또는 1을 생성한다.
그러나 동등 연산자의 우선순위는 관계 연산자보다 낮다.

예를 들어:

c
코드 복사
i < j == j < k
이 표현식은 다음과 같이 해석된다:

c
코드 복사
(i < j) == (j < k)
즉, i < j와 j < k가 모두 참이거나 모두 거짓일 경우 전체 표현식은 참이 된다.

능숙한 프로그래머는 관계 및 동등 연산자가 정수값을 반환한다는 점을 이용하기도 한다.
예를 들어:

c
코드 복사
(i >= j) + (i == j)
이 표현식의 값은 i가 j보다 작으면 0, 크면 1, 같으면 2가 된다.
그러나 이런 트릭성 코드는 일반적으로 바람직하지 않다 — 프로그램을 읽기 어렵게 만든다.

논리 연산자 (Logical Operators)
더 복잡한 논리 표현식은 단순한 표현식들을 논리 연산자로 결합해서 만들 수 있다.
논리 연산자는 not, and, or을 의미하며, 기호는 표 5.3과 같다.
!는 단항(unary) 연산자이고, &&, ||는 이항(binary) 연산자이다.

표 5.3 — 논리 연산자

기호	의미
!	논리 부정 (not)
&&	논리 AND (and)
`	

논리 연산자도 0 또는 1을 결과로 생성한다.
피연산자들이 실제로 0 또는 1일 수도 있지만, 꼭 그래야 하는 것은 아니다.
논리 연산자는 **모든 "0이 아닌 값"을 참(true)**으로, **0은 거짓(false)**으로 처리한다.

논리 연산자의 동작 방식은 다음과 같다:

!expr은 expr이 0이면 1, 그렇지 않으면 0

expr1 && expr2는 expr1과 expr2가 모두 0이 아니면 1

expr1 || expr2는 expr1 또는 expr2 둘 중 하나라도 0이 아니면 1

그 외의 경우는 결과가 0이다.

&&와 || 연산자는 **단락 평가(short-circuit evaluation)**를 수행한다.
즉, 이 연산자들은 왼쪽 피연산자부터 평가하며, 그 결과만으로 전체 표현식의 값을 결정할 수 있다면 오른쪽 피연산자는 평가하지 않는다.

예를 들어:

c
코드 복사
(i != 0) && (j / i > 0)
이 표현식을 평가하려면 먼저 (i != 0)을 평가한다.

i가 0이 아니면, (j / i > 0)도 평가해서 전체 결과를 판단한다.

그러나 i가 0이면, 전체 표현식은 무조건 거짓이 되므로 (j / i > 0)을 평가할 필요가 없다.
이것이 단락 평가의 장점이다 — 그렇지 않으면 0으로 나누기 오류가 발생할 수도 있었다.

주의: 논리 표현식에서 **부작용(side effect)**을 조심하라.
단락 평가 때문에, 모든 피연산자가 항상 평가되는 것이 아니다.
예를 들어:

c
코드 복사
i > 0 && ++j > 0
이 표현식에서 j가 증가될 것 같지만, i > 0이 거짓이라면 ++j > 0은 평가되지 않으므로, j는 증가되지 않는다.
이 문제는 조건식을 ++j > 0 && i > 0으로 바꾸거나, 더 나은 방법은 j를 별도로 증가시키는 것이다.

논리 연산자의 우선순위는 다음과 같다:

! 연산자는 단항 +, -와 동일한 우선순위를 가지며

&&, ||는 관계 및 동등 연산자보다 낮은 우선순위를 가진다.

예를 들어:

c
코드 복사
i < j && k == m
은 다음과 같이 해석된다:

c
코드 복사
(i < j) && (k == m)
연산자의 결합성은 다음과 같다:

!는 오른쪽 결합성

&&와 ||는 왼쪽 결합성이다.

## _**5.2 if 문 (The if Statement)**_
if 문은 표현식의 값을 검사하여 두 가지 대안 중 하나를 선택할 수 있도록 해준다.
가장 단순한 형태에서 if 문은 다음과 같은 형식을 갖는다:

c
코드 복사
if ( expression ) statement
괄호로 감싸진 표현식은 반드시 있어야 한다. 이는 if 문 문법의 일부이며, 표현식 자체의 일부가 아니다.
또한, 일부 프로그래밍 언어에서처럼 괄호 뒤에 then이 오지 않는다는 점도 주의해야 한다.

if 문이 실행되면 괄호 안의 표현식이 평가된다.
그 표현식의 값이 0이 아니면—C에서는 이를 **참(true)**으로 해석—괄호 뒤의 문장이 실행된다.
다음은 예제이다:

c
코드 복사
if (line_num == MAX_LINES)
    line_num = 0;
조건 line_num == MAX_LINES가 참이면, 문장 line_num = 0;이 실행된다.

==(같음)과 =(대입)를 혼동하지 말자.
다음 문장은:

c
코드 복사
if (i == 0) …
i가 0과 같은지 테스트한다. 반면:

c
코드 복사
if (i = 0) …
는 i에 0을 대입하고, 그 결과 값이 0인지 검사한다. 이 경우, 테스트는 항상 실패한다.

==과 =를 혼동하는 것은 아마도 C 프로그래밍에서 가장 흔한 오류일 것이다.
이는 수학이나 일부 프로그래밍 언어에서 =가 "같다"는 의미로 쓰이기 때문이다.
일부 컴파일러는 ==이 와야 할 자리에 =이 등장하면 경고를 출력해 준다.

if 문에 들어가는 표현식은 종종 어떤 변수가 일정 범위 내에 있는지 검사하는 데 사용된다.
예를 들어 0 ≤ i < n을 검사하려면 이렇게 쓴다:

c
코드 복사
if (0 <= i && i < n) …
반대로, i가 범위를 벗어났는지 검사하려면:

c
코드 복사
if (i < 0 || i >= n) …
이때 && 대신 ||를 사용한다는 점에 주의하라.

복합문 (Compound Statements)
if 문 기본 형태에서 statement는 단수로 되어 있다:

c
코드 복사
if ( expression ) statement
하지만 if 문으로 두 개 이상의 문장을 제어하고 싶다면 어떻게 해야 할까?
이럴 때 사용하는 것이 **복합문(compound statement)**이다.
복합문은 다음과 같은 형태를 갖는다:

c
코드 복사
{ statements }
여러 개의 문장을 중괄호로 감싸면, 컴파일러는 이를 하나의 단일 문장으로 간주한다.
예를 들어 다음은 복합문이다:

c
코드 복사
{ line_num = 0; page_num++; }
더 명확하게 보이도록, 일반적으로 복합문은 여러 줄에 걸쳐 작성하며, 각 문장은 한 줄씩 쓴다:

c
코드 복사
{
    line_num = 0;
    page_num++;
}
내부의 각 문장은 여전히 세미콜론으로 끝나지만, 복합문 자체는 세미콜론으로 끝나지 않는다.

이제 복합문을 if 문 안에서 사용하는 예제를 보자:

c
코드 복사
if (line_num == MAX_LINES) {
    line_num = 0;
    page_num++;
}
복합문은 반복문 등 하나의 문장만 허용하는 문법 위치에서 여러 문장을 실행하고자 할 때 흔히 사용된다.

else 절 (The else Clause)
if 문은 else 절을 가질 수도 있다:

c
코드 복사
if ( expression ) statement
else statement
괄호 안의 표현식이 **0(거짓)**이면, else 뒤에 오는 문장이 실행된다.

예를 들어:

c
코드 복사
if (i > j)
    max = i;
else
    max = j;
이때 두 내부 문장은 모두 세미콜론으로 끝나야 한다.

else를 어디에 배치할지는 스타일 문제이다.
많은 C 프로그래머는 else를 해당 if와 같은 열에 맞춘다.
또한 내부 문장이 짧으면 같은 줄에 쓰기도 한다:

c
코드 복사
if (i > j) max = i;
else max = j;
if 문 안에는 어떤 종류의 문장도 올 수 있다.
실제로 if 문 안에 또 다른 if 문이 **중첩(nested)**되는 경우도 흔하다.
예를 들어 다음은 i, j, k 중 가장 큰 값을 max에 저장하는 예제이다:

c
코드 복사
if (i > j)
    if (i > k)
        max = i;
    else
        max = k;
else
    if (j > k)
        max = j;
    else
        max = k;
if 문은 얼마든지 깊게 중첩될 수 있다.
각 else를 대응되는 if와 수직 정렬시키면 중첩 구조를 쉽게 파악할 수 있다.
중첩 구조가 여전히 혼란스럽다면 중괄호를 추가하는 것을 주저하지 말자:

c
코드 복사
if (i > j) {
    if (i > k)
        max = i;
    else
        max = k;
} else {
    if (j > k)
        max = j;
    else
        max = k;
}
중괄호를 추가하는 것은 괄호로 수식을 감싸는 것과 비슷하다.
프로그램을 더 읽기 쉽게 만들고, 컴파일러가 의도와 다르게 해석하는 것을 방지해 준다.

일부 프로그래머는 if 문(또는 반복문 등)에서 가능한 모든 위치에 중괄호를 사용하는 스타일을 택한다.
예를 들면:

c
코드 복사
if (i > j) {
    if (i > k) {
        max = i;
    } else {
        max = k;
    }
} else {
    if (j > k) {
        max = j;
    } else {
        max = k;
    }
}
중괄호를 필요하지 않은 경우에도 사용하는 것의 장점은 다음과 같다:

프로그램을 수정하기 쉬워진다. — if나 else 절 안에 문장을 쉽게 추가할 수 있다.

중괄호를 깜빡하고 생기는 오류를 방지할 수 있다.

연쇄 if 문 (Cascaded if Statements)
일련의 조건을 검사하다가 그중 하나라도 참이면 멈추는 코드를 작성해야 하는 경우가 많다.
이럴 땐 **연쇄 if 문(cascaded if statement)**을 사용하는 것이 가장 좋은 방법이다.
예를 들어, n이 0보다 작은지, 0과 같은지, 0보다 큰지를 검사하려면:

c
코드 복사
if (n < 0)
    printf("n is less than 0\n");
else
    if (n == 0)
        printf("n is equal to 0\n");
    else
        printf("n is greater than 0\n");
두 번째 if 문이 첫 번째 else 안에 중첩되어 있지만, 보통 C 프로그래머는 들여쓰기 하지 않고,
각 else를 원래 if와 수평 정렬한다:

c
코드 복사
if (n < 0)
    printf("n is less than 0\n");
else if (n == 0)
    printf("n is equal to 0\n");
else
    printf("n is greater than 0\n");
이런 배치는 연쇄 if 문에 독특한 형태를 부여한다:

c
코드 복사
if ( 표현식 )
    문장
else if ( 표현식 )
    문장
...
else
    문장
맨 마지막 두 줄(else 문장)은 생략될 수도 있다.
이런 방식의 들여쓰기는 조건이 많을 때 지나친 들여쓰기 문제를 피할 수 있고,
독자에게 이것이 단순한 조건 검사 목록임을 명확히 보여준다.

주의할 점은: 연쇄 if 문은 새로운 문장 유형이 아니라,
단순히 else 절 안에 또 다른 if 문이 들어가 있는 것일 뿐이다 (그리고 그 안에도 또 if 문이 들어가는 식이다).

예제 프로그램: 브로커 수수료 계산기

주식이 브로커를 통해 매매될 때, 브로커의 수수료는 거래 금액에 따라 달라지는 **슬라이딩 스케일(sliding scale)**을 사용하여 계산된다.
다음은 브로커가 부과하는 수수료의 예시이다:

거래 금액 구간	수수료 요율
$2,500 미만	$30 + 1.7%
$2,500 – $6,250	$56 + 0.66%
$6,250 – $20,000	$76 + 0.34%
$20,000 – $50,000	$100 + 0.22%
$50,000 – $500,000	$155 + 0.11%
$500,000 초과	$255 + 0.09%

최소 수수료는 $39이다.

다음 프로그램은 사용자에게 거래 금액을 입력받고, 수수료를 출력한다:

yaml
코드 복사
Enter value of trade: 30000  
Commission: $166.00
이 프로그램의 핵심은 거래 금액이 어느 구간에 해당하는지를 판단하는 연쇄 if 문이다:

c
코드 복사
/* broker.c — 브로커 수수료 계산 */
#include <stdio.h>

int main(void)
{
    float commission, value;

    printf("Enter value of trade: ");
    scanf("%f", &value);

    if (value < 2500.00f)
        commission = 30.00f + .017f * value;
    else if (value < 6250.00f)
        commission = 56.00f + .0066f * value;
    else if (value < 20000.00f)
        commission = 76.00f + .0034f * value;
    else if (value < 50000.00f)
        commission = 100.00f + .0022f * value;
    else if (value < 500000.00f)
        commission = 155.00f + .0011f * value;
    else
        commission = 255.00f + .0009f * value;

    if (commission < 39.00f)
        commission = 39.00f;

    printf("Commission: $%.2f\n", commission);

    return 0;
}
위의 연쇄 if 문은 다음과 같이도 쓸 수 있다 (차이점은 굵게 표시):

c
코드 복사
if (value < 2500.00f)
    commission = 30.00f + .017f * value;
**else if (value >= 2500.00f && value < 6250.00f)**
    commission = 56.00f + .0066f * value;
**else if (value >= 6250.00f && value < 20000.00f)**
    commission = 76.00f + .0034f * value;
...
이렇게 해도 프로그램은 여전히 잘 동작하지만, 조건을 더 쓸 필요는 없다.
예를 들어 첫 번째 if는 value < 2500인 경우를 검사하므로, 두 번째 검사 시 value >= 2500은 항상 참이 된다.
그러므로 이를 따로 확인할 필요가 없다.

### **“Dangling else” 문제 (The “Dangling else” Problem)**
if 문이 중첩되면, 우리가 주의해야 할 악명 높은 문제인 “dangling else” 문제가 발생할 수 있다. 다음 예제를 보자:

c
코드 복사
if (y != 0)
    if (x != 0)
        result = x / y;
    else
        printf("Error: y is equal to 0\n");
여기서 else 절은 어느 if 문에 속할까?
들여쓰기로만 보면, else는 바깥쪽 if 문에 속하는 것처럼 보일 수 있다.
하지만 C에서는 다음과 같은 규칙을 따른다:

else 절은 아직 else와 짝지어지지 않은 가장 가까운 if 문에 속한다.

따라서 위 예제에서 else는 실제로 안쪽의 if (x != 0) 문에 속한다.
올바르게 들여쓰기를 하면 다음과 같다:

c
코드 복사
if (y != 0)
    if (x != 0)
        result = x / y;
    else
        printf("Error: y is equal to 0\n");
만약 else 절을 바깥쪽 if (y != 0) 문에 속하게 하고 싶다면, 중괄호를 사용하여 명시적으로 구분해야 한다:

c
코드 복사
if (y != 0) {
    if (x != 0)
        result = x / y;
} else
    printf("Error: y is equal to 0\n");
이 예제는 중괄호의 가치를 잘 보여준다.
처음부터 중괄호를 사용했다면 이런 혼동은 애초에 생기지 않았을 것이다.

조건 표현식 (Conditional Expressions)
C의 if 문은 조건의 값에 따라 두 가지 동작 중 하나를 수행하게 해준다.
C는 또 다른 방법으로, 하나의 표현식이 조건의 값에 따라 두 가지 값 중 하나를 선택하게 해주는 연산자도 제공한다.

이 **조건 연산자(conditional operator)**는 두 기호 ?와 :로 구성되며, 반드시 다음 형태로 사용해야 한다:

c
코드 복사
expr1 ? expr2 : expr3
expr1, expr2, expr3는 어떤 타입의 표현식이든 될 수 있다.
이렇게 구성된 표현식을 **조건 표현식(conditional expression)**이라 부른다.
이 연산자는 C의 연산자 중 유일하게 세 개의 피연산자를 요구하기 때문에, 흔히 **삼항 연산자(ternary operator)**라고도 불린다.

조건 표현식 expr1 ? expr2 : expr3는 다음처럼 읽으면 된다:

“expr1이 참이면 expr2, 아니면 expr3”

평가 순서는 다음과 같다:

먼저 expr1을 평가한다.

그 값이 0이 아니면 expr2를 평가하고, 그 값이 전체 표현식의 값이 된다.

expr1이 0이면, expr3을 평가하여 그것이 표현식의 값이 된다.

다음은 조건 연산자를 사용하는 예제이다:

c
코드 복사
int i, j, k;
i = 1;
j = 2;
k = i > j ? i : j;        // k는 이제 2
k = (i >= 0 ? i : 0) + j; // k는 이제 3
첫 번째 k 대입문에서 i > j ? i : j는 i와 j 중 큰 값을 반환한다.
i가 1, j가 2이므로 조건 i > j는 거짓이고, 따라서 j의 값인 2가 k에 대입된다.

두 번째 문장에서는 i >= 0 ? i : 0 조건이 참이므로, 그 결과는 i의 값인 1이다.
이 값과 j(2)를 더하여 k는 3이 된다.

참고로, 여기서 괄호는 반드시 필요하다.
조건 연산자의 우선순위는 매우 낮기 때문이다 — 지금까지 다룬 연산자들 중에서는 대입 연산자들을 제외하면 가장 낮다.

조건 표현식은 프로그램을 짧게 만들어 주지만, 이해하기 어려워질 수도 있다.
따라서 일반적으로는 사용을 피하는 것이 좋다.
하지만 다음과 같은 경우에는 유용하게 사용할 수 있다.

예를 들어 return 문에서:

c
코드 복사
if (i > j)
    return i;
else
    return j;
를 다음처럼 간단히 표현할 수 있다:

c
코드 복사
return i > j ? i : j;
printf 호출에서도 사용할 수 있다:

c
코드 복사
if (i > j)
    printf("%d\n", i);
else
    printf("%d\n", j);
대신 다음처럼 쓸 수 있다:

c
코드 복사
printf("%d\n", i > j ? i : j);
조건 표현식은 특정 종류의 매크로 정의에서도 자주 사용된다.

### **C89에서의 불리언 값 (Boolean Values in C89)**
오랫동안 C 언어는 정식 Boolean 타입이 없었으며, C89 표준에도 정의되어 있지 않다.
이러한 결핍은 사소하지만 성가신 일이다. 많은 프로그램들이 참 또는 거짓만 저장하는 변수를 필요로 하기 때문이다.

이 한계를 해결하기 위한 방법 중 하나는, int 변수를 선언한 후 0 또는 1을 저장하는 것이다:

c
코드 복사
int flag;
flag = 0;
...
flag = 1;
이 방법은 작동하지만, 가독성에는 도움이 되지 않는다.
flag가 오직 불리언 값을 저장하는 용도로 쓰인다는 점이 명확하지 않기 때문이다.

이를 좀 더 명확히 하기 위해, C89 프로그래머는 다음과 같은 매크로 정의를 자주 사용한다:

c
코드 복사
#define TRUE 1
#define FALSE 0
이제 변수에 값을 대입할 때 좀 더 자연스럽게 보인다:

c
코드 복사
flag = FALSE;
...
flag = TRUE;
flag가 참인지 검사할 때는 이렇게 쓸 수 있다:

c
코드 복사
if (flag == TRUE) ...
또는 더 나은 방법은 다음과 같다:

c
코드 복사
if (flag) ...
이 두 번째 방식이 더 나은 이유는 간결함뿐만 아니라, flag 값이 0 또는 1이 아닌 다른 값이더라도 여전히 올바르게 작동하기 때문이다.

flag가 거짓인지 검사할 때는 다음과 같이 쓸 수 있다:

c
코드 복사
if (flag == FALSE) ...
또는:

c
코드 복사
if (!flag) ...
이 개념을 한 단계 더 발전시키면, int 대신 사용할 수 있는 타입 매크로도 정의할 수 있다:

c
코드 복사
#define BOOL int
이제 BOOL을 사용해서 불리언 변수를 선언하면, 다음과 같이 명확한 의미를 전달할 수 있다:

c
코드 복사
BOOL flag;
이제 flag는 일반적인 정수 변수라기보다는 불리언 조건을 표현하는 변수임이 분명해진다.
(물론 컴파일러 입장에서는 여전히 int 변수로 취급된다.)

앞으로의 장에서는, **타입 정의(type definitions)**와 **열거형(enumeration)**을 사용하여
C89에서 불리언 타입을 만드는 더 나은 방법들을 살펴볼 것이다.

C99에서의 불리언 값 (Boolean Values in C99)
오랫동안 존재했던 불리언 타입의 부재는 C99에서 마침내 해결되었다.
C99는 _Bool 타입을 제공한다.
이제 불리언 변수를 다음과 같이 선언할 수 있다:

c
코드 복사
_Bool flag;
_Bool은 정수 타입(정확히는 부호 없는 정수 타입)이기 때문에, _Bool 변수는 사실상 숫자 변수처럼 동작한다.
하지만 일반적인 정수 변수와 달리, _Bool 변수에는 0 또는 1만 저장될 수 있다.
일반적으로 0이 아닌 값을 _Bool 변수에 저장하려 하면, 그 값은 1로 변환된다:

c
코드 복사
flag = 5; // flag는 1이 된다
비록 권장되지는 않지만, _Bool 변수에 대해 산술 연산을 수행하는 것도 합법적이다.
또한 _Bool 변수를 printf로 출력할 수도 있으며, 출력 결과는 0 또는 1이 된다.
물론 _Bool 변수는 if 문에서도 사용할 수 있다:

c
코드 복사
if (flag) // flag가 1이면 참
    ...
C99는 _Bool 타입 외에도, Boolean 값을 더 편하게 다룰 수 있게 도와주는 새로운 헤더 <stdbool.h>도 제공한다.
이 헤더는 _Bool을 대신하는 **매크로 bool**을 제공한다.

c
코드 복사
#include <stdbool.h>
bool flag; // _Bool flag;와 동일
또한, 이 헤더는 true, false라는 매크로도 제공한다.
각각 1과 0을 의미하므로, 다음과 같은 표현도 가능하다:

c
코드 복사
flag = false;
...
flag = true;
<stdbool.h> 헤더는 매우 유용하므로, 이후의 예제 프로그램들에서는 불리언 변수가 필요한 경우 항상 사용할 것이다.

### _**5.3 switch 문 (The switch Statement)**

일상적인 프로그래밍에서 우리는 어떤 표현식의 값이 여러 값 중 어떤 것과 일치하는지 비교해야 하는 경우가 자주 있다.
5.2절에서 본 것처럼, **연쇄 if 문(cascaded if statement)**을 사용해서 이 작업을 수행할 수 있다.
예를 들어, 다음과 같은 연쇄 if 문은 숫자 성적에 해당하는 영어 단어를 출력한다:
```c
if (grade == 4)
    printf("Excellent");
else if (grade == 3)
    printf("Good");
else if (grade == 2)
    printf("Average");
else if (grade == 1)
    printf("Poor");
else if (grade == 0)
    printf("Failing");
else
    printf("Illegal grade");
```
이러한 연쇄 if 문 대신, C는 switch 문을 제공한다.
다음 switch 문은 위의 연쇄 if 문과 동등하다:

c
코드 복사
switch (grade) {
    case 4: printf("Excellent"); break;
    case 3: printf("Good"); break;
    case 2: printf("Average"); break;
    case 1: printf("Poor"); break;
    case 0: printf("Failing"); break;
    default: printf("Illegal grade"); break;
}
이 문장이 실행되면, 변수 grade의 값이 4, 3, 2, 1, 0 중 하나와 일치하는지 검사한다.
예를 들어 4와 일치하면, "Excellent"가 출력된 후 break 문에 의해 switch 문 다음으로 실행이 이동한다.
grade의 값이 어떤 case에도 해당되지 않으면, default case가 적용되어 "Illegal grade"가 출력된다.

switch 문은 연쇄 if 문보다 읽기 쉬운 경우가 많다.
게다가, case가 많아질수록 성능도 더 나을 수 있다.

switch 문의 기본 구조
switch 문의 일반적인 형태는 다음과 같다:

c
코드 복사
switch ( expression ) {
    case constant-expression : statements
    ...
    case constant-expression : statements
    default : statements
}
switch 문은 비교적 복잡한 문장이므로, 구성 요소를 하나씩 살펴보자:

■ 제어 표현식(Controlling expression)
switch 다음에는 괄호 안에 **정수 표현식(integer expression)**이 와야 한다.
C에서는 **문자(char)**도 정수로 취급되므로 switch 문에서 사용할 수 있다.
하지만 **실수(floating-point)**와 **문자열(string)**은 사용할 수 없다.

■ case 레이블(Case labels)
각 case는 다음과 같은 레이블로 시작한다:

c
코드 복사
case constant-expression:
상수 표현식(constant expression)은 일반 표현식과 비슷하지만, 변수나 함수 호출을 포함할 수 없다.
예를 들어 5, 5 + 10은 상수 표현식이지만, n + 10은 상수 표현식이 아니다 (단, n이 상수를 나타내는 매크로라면 예외).

case 레이블의 상수 표현식은 반드시 정수 값을 가져야 한다 (문자도 허용됨).

■ 문장(Statements)
각 case 레이블 뒤에는 여러 개의 문장이 올 수 있다.
이 문장들 주위에 중괄호는 필요 없다. (C에서 중괄호가 필요 없는 드문 장소 중 하나다.)

각 case 그룹의 마지막에는 보통 break 문이 온다.

중복된 case 레이블은 허용되지 않는다.

case들의 순서는 상관없다. default가 마지막에 올 필요도 없다.

case 뒤에는 한 개의 상수 표현식만 사용할 수 있지만, 여러 case 레이블을 하나의 문장 그룹에 연결할 수 있다:

c
코드 복사
switch (grade) {
    case 4:
    case 3:
    case 2:
    case 1:
        printf("Passing");
        break;
    case 0:
        printf("Failing");
        break;
    default:
        printf("Illegal grade");
        break;
}
혹은 다음처럼 한 줄로 쓰는 경우도 있다:

c
코드 복사
switch (grade) {
    case 4: case 3: case 2: case 1:
        printf("Passing");
        break;
    case 0:
        printf("Failing");
        break;
    default:
        printf("Illegal grade");
        break;
}
아쉽게도, C에서는 일부 언어와 달리 **case 레이블에서 값의 범위(range)**를 지정하는 방법이 없다.

switch 문은 default case를 반드시 포함할 필요는 없다.
만약 default가 없고, 제어 표현식의 값이 어떤 case와도 일치하지 않으면,
제어는 switch 다음 문장으로 넘어간다.

break 문의 역할 (The Role of the break Statement)
이제 종종 혼란을 일으키는 break 문을 더 자세히 살펴보자.
앞서 본 것처럼, break 문이 실행되면 프로그램은 **switch 문에서 “탈출”**하고,
다음 문장으로 제어가 이동한다.

우리가 break를 필요로 하는 이유는, switch 문이 사실상 **“계산된 점프(computed jump)”**의 일종이기 때문이다.
제어 표현식이 평가되면, 일치하는 case 레이블로 제어가 점프된다.
case 레이블은 switch 문 안의 위치를 나타내는 표식일 뿐이다.

일치하는 case의 마지막 문장이 실행된 후, break가 없으면 다음 case로 제어가 넘어가버린다.
즉, 다음 case 레이블은 무시되고, 해당 문장이 바로 실행된다.
예를 들어 다음 switch 문을 보자:

c
코드 복사
switch (grade) {
    case 4: printf("Excellent");
    case 3: printf("Good");
    case 2: printf("Average");
    case 1: printf("Poor");
    case 0: printf("Failing");
    default: printf("Illegal grade");
}
grade의 값이 3이면, 출력되는 메시지는 다음과 같다:

nginx
코드 복사
GoodAveragePoorFailingIllegal grade
break를 빠뜨리는 것은 흔한 실수다.
간혹 일부러 break를 생략하여 여러 case가 공통 코드를 공유하게 하기도 하지만, 대부분의 경우에는 단순한 실수다.

의도적으로 break를 생략하는 경우에는 다음처럼 주석을 남기는 것이 좋다:

c
코드 복사
switch (grade) {
    case 4: case 3: case 2: case 1:
        num_passing++;
        /* FALL THROUGH */
    case 0:
        total_grades++;
        break;
}
이 주석이 없다면, 나중에 이 코드를 본 사람이 이걸 실수로 생각해 break를 추가해버릴 수도 있다.

참고로, switch 문의 마지막 case는 보통 break가 필요 없지만,
나중에 case가 추가될 경우를 대비해 습관적으로 break를 추가하는 경우가 많다.

프로그램 예제: 계약서 형식으로 날짜 출력하기
계약서나 법적 문서에는 날짜가 다음과 같은 형식으로 표시되는 경우가 많다:

markdown
코드 복사
Dated this __________ day of __________ , 20__ .
다음은 사용자로부터 mm/dd/yy 형식의 날짜를 입력받아 “법적(legal)” 형식으로 출력하는 프로그램이다:

입력:

bash
코드 복사
Enter date (mm/dd/yy): 7/19/14
출력:

kotlin
코드 복사
Dated this 19th day of July, 2014.
printf로 대부분의 서식을 처리할 수 있지만, 다음 두 가지 문제는 우리가 해결해야 한다:

날짜 뒤에 "th"(또는 "st", "nd", "rd")를 붙이는 법

월(month)을 숫자가 아닌 단어로 출력하는 법

다행히도, 이 두 작업 모두 switch 문을 이용해 쉽게 처리할 수 있다.

date.c

c
코드 복사
/* Prints a date in legal form */
#include <stdio.h>

int main(void)
{
    int month, day, year;

    printf("Enter date (mm/dd/yy): ");
    scanf("%d /%d /%d", &month, &day, &year);

    printf("Dated this %d", day);

    switch (day) {
        case 1: case 21: case 31:
            printf("st"); break;
        case 2: case 22:
            printf("nd"); break;
        case 3: case 23:
            printf("rd"); break;
        default:
            printf("th"); break;
    }

    printf(" day of ");

    switch (month) {
        case 1:  printf("January");   break;
        case 2:  printf("February");  break;
        case 3:  printf("March");     break;
        case 4:  printf("April");     break;
        case 5:  printf("May");       break;
        case 6:  printf("June");      break;
        case 7:  printf("July");      break;
        case 8:  printf("August");    break;
        case 9:  printf("September"); break;
        case 10: printf("October");   break;
        case 11: printf("November");  break;
        case 12: printf("December");  break;
    }

    printf(", 20%.2d.\n", year);
    return 0;
}
%.2d를 사용하여 년도(year)의 마지막 두 자리를 출력하는 방식에 주목하자.
만약 %d를 사용했다면, 한 자리 숫자의 경우 출력이 잘못될 수 있다 (예: 2005가 205로 출력됨).


## _**Q & A**

Q: == 대신 =을 사용했을 때, 내 컴파일러는 경고를 출력하지 않아요.
컴파일러가 이 문제를 알아차리게 할 수 있는 방법이 있을까요? [p. 77]
A: 어떤 프로그래머들은 다음과 같은 요령을 사용합니다.

c
코드 복사
if (i == 0) …
를 쓰는 대신, 습관적으로 다음처럼 씁니다:

c
코드 복사
if (0 == i) …
이제 == 연산자를 실수로 =로 썼다고 가정해 봅시다:

c
코드 복사
if (0 = i) …
이 경우 컴파일러는 에러 메시지를 출력하게 됩니다. 왜냐하면 0에 값을 대입하는 건 불가능하기 때문입니다.

저는 이 요령을 사용하지 않습니다. 왜냐하면 이런 코드는 자연스럽지 않게 보이기 때문입니다.
또한, 이 방법은 조건식의 피연산자 중 하나가 lvalue가 아닐 경우에만 사용할 수 있습니다.

다행히도, 많은 컴파일러는 if 조건에서 = 연산자의 의심스러운 사용을 검사할 수 있습니다.
예를 들어 GCC 컴파일러는 -Wparentheses 옵션을 사용하거나, -Wall(전체 경고 활성화)을 사용하면 이 검사를 수행합니다.
GCC에서는 특정한 경우에 이 경고를 무시하고 싶다면, if 조건을 한 번 더 괄호로 감싸면 됩니다:

c
코드 복사
if ((i = j)) …
Q: C 관련 책들을 보면, **복합문(compound statement)**에 대해 들여쓰기와 중괄호 배치가 서로 다른 여러 스타일이 있는 것 같아요.
어떤 스타일이 가장 좋은가요?
A: 『The New Hacker’s Dictionary』(MIT Press, 1996)에 따르면, 들여쓰기 및 중괄호 배치에 관한 대표적인 스타일은 네 가지입니다:

K&R 스타일
Brian Kernighan과 Dennis Ritchie의 『The C Programming Language』에서 사용된 스타일입니다.
이 책에서 사용된 스타일도 이 스타일입니다.
K&R 스타일에서는 왼쪽 중괄호 {를 같은 줄 끝에 씁니다:

c
코드 복사
if (line_num == MAX_LINES) {
    line_num = 0;
    page_num++;
}
이 스타일은 왼쪽 중괄호를 별도 줄에 두지 않음으로써 코드를 간결하게 유지합니다.
단점이라면, 왼쪽 중괄호가 잘 안 보일 수 있다는 점입니다.
(하지만 내부 문장의 들여쓰기로 중괄호 위치는 쉽게 파악할 수 있으므로, 저는 문제되지 않는다고 생각합니다.)
참고로 Java 언어에서 가장 많이 쓰이는 스타일이기도 합니다.

Allman 스타일
Eric Allman(UNIX 유틸리티 sendmail의 저자)의 이름을 딴 스타일입니다.
이 스타일에서는 왼쪽 중괄호를 다음 줄에 별도로 배치합니다:

c
코드 복사
if (line_num == MAX_LINES)
{
    line_num = 0;
    page_num++;
}
이 스타일은 중괄호의 쌍이 눈에 잘 띄게 하며, 짝이 맞는지 쉽게 확인할 수 있습니다.

Whitesmiths 스타일
Whitesmiths C 컴파일러에서 널리 사용된 스타일입니다.
중괄호를 들여쓰는 것이 특징입니다:

c
코드 복사
if (line_num == MAX_LINES)
    {
    line_num = 0;
    page_num++;
    }
GNU 스타일
GNU 프로젝트에서 개발된 소프트웨어에서 사용하는 스타일입니다.
중괄호를 한 번 들여쓰고, 내부 문장은 그보다 더 들여씁니다:

c
코드 복사
if (line_num == MAX_LINES)
  {
    line_num = 0;
    page_num++;
  }
어떤 스타일을 사용할지는 개인의 취향 문제입니다.
어느 스타일이 다른 스타일보다 명백히 낫다는 증거는 없습니다.
결국 어떤 스타일을 고르느냐보다, 그 스타일을 일관되게 적용하는 것이 더 중요합니다.

Q: i가 int 변수이고, f가 float 변수일 때, 다음 조건 표현식의 타입은 무엇인가요?

c
코드 복사
(i > 0 ? i : f)
A: 조건 표현식에 int와 float 값이 혼합되면, 전체 표현식의 타입은 float입니다.
i > 0이 참이면, i의 float 타입으로 변환된 값이 사용됩니다.

Q: C99는 왜 불리언 타입 이름을 더 잘 지은 것으로 하지 않았나요? [p. 85]
A: _Bool이라는 이름은 그다지 세련되지 않죠.
bool이나 boolean 같은 더 일반적인 이름이 사용되지 않은 이유는,
기존 C 프로그램들에서 이미 해당 이름을 매크로나 변수로 정의했을 수도 있기 때문입니다.
이로 인해 옛 코드가 컴파일되지 않게 될 수도 있습니다.

Q: 그런데 왜 _Bool이라는 이름은 옛 프로그램을 깨뜨리지 않죠?
A: C89 표준은 밑줄(_)로 시작하고, 대문자가 뒤따르는 이름은 미래 용도를 위해 예약되어 있다고 명시하고 있습니다.
즉, 프로그래머는 _Bool 같은 이름을 사용하지 않아야 하므로, C99에서 이 이름을 써도 기존 프로그램과 충돌하지 않습니다.

Q: switch 문에 대한 설명에서, 그것이 “가장 일반적인 형태”라고 했는데요. 다른 형태도 있나요? [p. 87]
A: switch 문은 이 장에서 설명한 것보다 조금 더 일반적입니다.
하지만 여기서 다룬 내용으로 대부분의 프로그램에는 충분합니다.

예를 들어, switch 문 안에는 case 키워드로 시작하지 않는 **일반적인 레이블(label)**도 포함될 수 있습니다.
이로 인해 재미있지만 위험한 함정이 발생할 수도 있습니다.
예를 들어 default를 오타로 defualt라고 썼다고 합시다:

c
코드 복사
switch (...) {
    ...
    defualt: ...
}
컴파일러는 이 오류를 감지하지 않을 수도 있습니다.
왜냐하면 defualt는 단순히 일반 레이블로 인식되기 때문입니다.

Q: switch 문에 대해서도 들여쓰기 방식이 여러 가지 있던데, 어떤 방식이 가장 좋나요?
A: 일반적으로 사용되는 두 가지 방식이 있습니다:

1. case 레이블 옆에 문장을 쓰는 방식:

c
코드 복사
switch (coin) {
    case 1: printf("Cent"); break;
    case 5: printf("Nickel"); break;
    case 10: printf("Dime"); break;
    case 25: printf("Quarter"); break;
}
각 case가 printf처럼 간단한 동작 하나만 수행하는 경우라면,
break 문을 같은 줄에 두는 것도 좋습니다.

2. case 레이블 아래에 문장을 들여쓰기 하는 방식:

c
코드 복사
switch (coin) {
    case 1:
        printf("Cent");
        break;
    case 5:
        printf("Nickel");
        break;
    case 10:
        printf("Dime");
        break;
    case 25:
        printf("Quarter");
        break;
}
이 방식의 변형으로, 각 case 레이블을 switch 키워드와 같은 열에 정렬하는 방법도 있습니다.
요약하자면:

각 case에 들어가는 문장이 짧고 간단할 경우 → 첫 번째 방식이 적합

각 case의 문장이 길거나 복잡한 경우 → 두 번째 방식이 더 보기 좋고 유지 관리에 유리합니다.



