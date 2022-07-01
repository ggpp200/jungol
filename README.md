이 문서는 jungol의 알고리즘 문제 풀이 코드를 게시하는 문서임

이 문서는 다음과 같이 이용해야 한다

- 검색 시 `code코드번호`로 검색해야 한다
- 각 문제 별 `코드번호`와 `이름` 과 `걸린시간` 그리고 `풀이코드`가 기재되어 있어야 한다.
- Beginner_coder에서 시작하여 차례대로 풀 것이다.

기본 구성은 아래와 같음

# code1291 구구단(10m)

```bash
def gogodan(start, end):
    if start <= end:
        for one_nine in range(1, 10, 1):
            for s_e in range(start, end + 1):
                if s_e * one_nine < 10:
                    blank = ' '
                else:
                    blank = ''
                print(f'{s_e} * {one_nine} = {blank}{s_e * one_nine}', end='   ')
            print()
    else:
        for one_nine in range(1, 10, 1):
            for s_e in range(start, end - 1, -1):
                if s_e * one_nine < 10:
                    blank = ' '
                else:
                    blank = ''
                print(f'{s_e} * {one_nine} = {blank}{s_e * one_nine}', end='   ')
            print()

output = 0

while output == 0:
    s, e = map(int, input().split())
    if 2 <= s <= 9 and 2 <= e <= 9:
        output = 1
        gogodan(s, e)
    else:
        print("INPUT ERROR!")
```

