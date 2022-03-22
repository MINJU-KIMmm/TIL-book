# Markdown 이란?

- plain-test formatting syntax : plain-text 기반
- 경량형 마크업 언어 light weight markup language
- 확장자 : md

---

# Markdown 기본 문법

## 1. Heading

```markdown
# heading1
## heading2
### heading3
#### heading4
##### heading5
```

- 출력 결과
    
    # heading1
    
    ## heading2
    
    ### heading3
    
    #### heading4
    
    ##### heading5
    

## 2. Line

```markdown
---
```

- 출력 결과
    
    ---
    

## 3. Text attributes

```markdown
**bold**
*italic*
~~strikethrough~~
```

- 출력 결과
    
    **bold**
    
    *italic*
    
    ~~strikethrough~~
    

## 4. Quote 인용

```markdown
> 인용구

> 인용되는 첫번째줄
>> 다시 인용
> (인용 다시 상위 수준으로 변경 시 빈줄)
> ### 인용문 내부 헤더
```

- 출력 결과
	> 인용구
	>> 다시인용

## 5. Bullet list

```markdown
* 1번
* 2번

- 1번
- 2번
```

- 출력 결과
    - 1번
        - 2번
            - 3번

## 6. Link

```markdown
[링크이름](https://velog.io/@mimmimmu)


- 주소만으로 링크
<https://velog.io/@mimmimmu>
```

- 출력결과
    
    [링크이름](https://velog.io/@mimmimmu)
    

    <https://velog.io/@mimmimmu>
    

## 7. Table 표

```markdown
|Header|Description|
|---|---|
|cell1|cell2|
|cell1|cell2|

- 정렬
	- 오른쪽 정렬
		---:
	- 왼쪽 정렬
		:---
	- 가운데 정렬
		:---:
|Header|Description|Description|
|:---|---:|:---:|
|cell1|cell2|cell3|
```

- 출력결과
    
    |Header|Description|
    |---|---|
    |cell1|cell2|
    |cell1|cell2|
    
    
    |Header|Description|Description|
    |:---|---:|:---:|
    |cell1|cell2|cell3|
    

## 8. Code 코드

- 출력결과
    
    ```java
    import java.util.*;
    ```
    
    `인라인코드`
    

## 9. Image 이미지

```markdown
![사진이름](사진경로)
```

---

# GitHub에서만 사용가능한 문법

## 10. Task Lists

```markdown
- [ ] task
- [x] task2
```

- 출력결과
    - [ ]  task
    - [x]  task2

## 11. Emoticon

```markdown
:이모티콘이름:
```

- 출력결과
    
    :bowtie:
    

---

# 기타

## 12. Table of Contents 목차

```markdown
[1. Markdown 이란?](#Markdown 이란?)
[2. Markdown 기본 문법] (#Markdown 기본 문법)

조건: 목차명에 영어는 무조건 소문자, 스페이스가 있을 경우 대신 - 입력
조건: 목차명에 점, 반점, 특수문자, 괄호가 들어갔을 경우 무시해주면 된다.
조건: 목차명은 문자열이 유일해야 해야한다. 유일하지 않으면 가장 가까운 곳으로 가는데 이 때 링크명과 목차명이 같아야 할 때 팁은 위 예제와 같이 [링크명 ] 뒤에 스페이스바로 한 칸 띄어주면 된다.
조건: #으로 제목처리된 곳으로만 갈 수 있다 #이나 ### 처럼 개수는 상관없음. (단, ### 으로 갈때도 목차명에 #한개만 써야함)
```

- 출력결과

[1. Markdown 이란?](#Markdown-이란?)  
[2. Markdown 기본 문법](#Markdown-기본-문법)

## 13. 줄바꿈
```markdown
- 스페이스바 두번 + enter == \n
- <br>
```
- 출력결과

  안녕  
  이건 스페이스바 두번 엔터

  안녕<br>이건 br
