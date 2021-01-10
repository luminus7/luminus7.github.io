---
title: "Basic Markdown 문법"
excerpt: "기본적인 Markdown 문법을 정리해본다."
categories:
    - Blog
tags:
    - Blog
    - Markdown
last_mod_at: 2021-01-06T08:08:00-05:00
toc: true
toc_sticky: true
---

기본적인 텍스트 표기 방식이다.
마크다운은 줄바꿈을 인식하지 않는다.

줄바꿈을 하기 위해서는 라인 끝에 스페이스를 2번  표기해야 한다.

여러가지 강조 표시가 존재한다. 첫번째로 *single asterisks*, 두번째로 _single underscores_, 세번째로 **double asterisks**,
네번째로 __double underscores__, 다섯번째로 ~~cancelline~~가 있다.

# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6

> This is a blockquote.

> This is a first blockquote.
>> This is a second blockquote.
>>> This is a third blockquote.

정렬 목록
1. 봄
2. 여름
3. 가을
4. 겨울

비정렬 목록 *, +, -
* 과자
  * 라면
    * 사탕
+ 과자
  + 라면
    + 사탕

- 과자
  - 라면
    - 사탕

코드 블럭 (백 쿼트 \` 코드 앞뒤로 3회 혹은 물결~ 코드 앞뒤로 3회)

C
```c
#define container_of(ptr, type, member) ({                      \
        const typeof( ((type *)0)->member ) *__mptr = (ptr);    \
        (type *)( (char *)__mptr - offsetof(type,member) );})

void foo_func(type_t *input){
    printk("Hi kernel!");
}
```

Ruby
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello Worldd!")
puts markdown.to_html
```

Cpp
```cpp
#include <iostream>
using namespace std;
int main(){
    int y = SOME_MACRO_REFERENCE;
    int x = 5 + 6;
    cout << "Hello World!" << x << endl();
}
```

Python
```python
# N,M,K 입력
N, M, K = map(int, input().split())

# N개를 공백으로 구분하여 입력받기
data = list(map(int, input().split()))

data.sort()
first = data[N-1]
second = data[N-2]
```

인라인 코드 블럭 (백쿼트 \` 로 감싸진 텍스트)
`#define COMPARE(x,y) ( ((x)<(y))? -1 : ((x)==(y))? 0 : 1)`
수평선
* * *
***
******
- - -
----------------

이미지 삽입
![](https://luminus7.com/assets/favicon/android-chrome-512x512.png){: .align-center}

링크
링크표시법 : [Title](link)
[Google page link](https://google.com)

표

| 항목 | 가격 | 개수 |
|-----|-----|-----|
| 라면 | 800원 | 10개 |
| 과자 | 900원 | 20개 |

작성시 표 앞뒤로 개행필요. 정렬도 가능.

<{{ site.url }}{{ site.baseurl }}>