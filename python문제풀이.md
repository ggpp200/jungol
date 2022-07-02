## code1291 구구단(time 10m)

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



## code1341 구구단(time 30s)

```bash
def gogodan(start, end):
    if start <= end:

        for s_e in range(start, end + 1):
            for one_nine in range(1, 10, 1):

                if s_e * one_nine < 10:
                    blank = ' '
                else:
                    blank = ''
                print(f'{s_e} * {one_nine} = {blank}{s_e * one_nine}', end='   ')
                if one_nine % 3 == 0:
                    print()

            print("\n")
    else:
        for s_e in range(start, end - 1, -1):
            for one_nine in range(1, 10, 1):

                if s_e * one_nine < 10:
                    blank = ' '
                else:
                    blank = ''
                print(f'{s_e} * {one_nine} = {blank}{s_e * one_nine}', end='   ')
                if one_nine % 3 == 0:
                    print()

            print("\n")

output = 0

while output == 0:
    s, e = map(int, input().split())
    if 2 <= s <= 9 and 2 <= e <= 9:
        output = 1
        gogodan(s, e)
    else:
        print("INPUT ERROR!")
```



## code1303 숫자사각형1(time 4m 17s)

```bash
n, m = map(int, input().split())
number = 1
while number < n * m + 1:
    print(number,end=' ')
    if number % m == 0:
        print()
    number += 1
```



## code1856 숫자사각형2(time 10m 47s)

```bash
n, m = map(int, input().split())

for hight in range(1, n + 1):
    if hight % 2 == 1:
        for width in range(1, m + 1):
            print((hight - 1) * m + width, end=' ')
    else:
        for width in range(m, 0, -1):
            print((hight - 1) * m + width, end=' ')
    print()
```



## code1304 숫자사각형3(time 1m 48s)

```bash
n = int(input())

for width in range(1, n + 1):
    for hight in range(1, n + 1):
        print((hight - 1) * n + width, end=' ')
    print()
```



## code2046 숫자사각형4(time 7m 37s)

```bash
n, type_s = map(int, input().split())

for width in range(1, n + 1):
    for hight in range(1, n + 1):
        if type_s == 1:
            print(width, end=' ')
        elif type_s == 2:
            if width % 2 == 1:
                print(hight, end=' ')
            else:
                print(n + 1 - hight, end=' ')
        elif type_s == 3:
            print(width * hight, end=' ')
    print()

```



## code1307 문자사각형1(time 18m)

```bash
n = int(input())
for idx in range(n - 1, -1, -1):
    for jdx in range(n - 1, -1, -1):
        number = 65 + idx + jdx * n
        while number > 90:
            number -= 26
        print(chr(number), end=' ')
    print()

```



## code1314 문자사각형2(time 5m 23s)

```bash
n = int(input())
for idx in range(0, n):
    for jdx in range(0, n):
        if jdx % 2 == 0:
            number = 65 + idx + jdx * n
            while number > 90:
                number -= 26
            print(chr(number), end=' ')
        else:
            number = 65 - (idx + 1) + (jdx + 1) * n
            while number > 90:
                number -= 26
            print(chr(number), end=' ')
    print()

```



## code1338 문자삼각형1(time 1h 20m)

```bash
N = int(input())
for idx in range(N):
    number = 65 + idx - N
    add_num = N
    for jdx in range(N):
        if idx + jdx < N-1:
            print('  ',end='')
        else:
            number = add_num + number
            while number > 90:
                number -= 26
            add_num -= 1
            print(chr(number), end=' ')
    print()

```



## code1339 문자삼각형2(time 48m 4s)

```bash
N = int(input())
if 1 <= N <=100 and N % 2 == 1:
    for idx in range(N):
        for jdx in range(N):
            word = 65 + (N // 2 - jdx) ** 2
            if idx >= jdx and N - 1 - idx >= jdx:
                word += idx - jdx
                while word > 90:
                    word = word - 26
                print(chr(word), end=' ')
        print()
else:
    print('INPUT ERROR')
```



## code1146 선택정렬(time  5m)

```
N = int(input())
N_list = list(map(int, input().split()))
for index in range(N - 1):
    min_num = N_list[index]
    idx = index
    for i in range(index, N ):
        if min_num > N_list[i]:
            min_num = N_list[i]
            idx = i
    N_list[index], N_list[idx] = N_list[idx], N_list[index]
    print(*N_list)
```



## code1221 후위표기법1(time 1h 36m 51s)

이거 문제 이해를 잘못하면 바로 70점 나옵니당

```bash
M = int(input())
M_list = list(input().split())
operator_list = ['+', '-', '*', '/']

idx = 2
while len(M_list) > 1:
    while idx < len(M_list):
        if M_list[idx] == '+':
            M_list[idx - 2] = int(M_list[idx - 2]) + int(M_list[idx - 1])
            M_list.pop(idx - 1)
            M_list.pop(idx - 1)
            idx -= 2
        elif M_list[idx] == '-':
            M_list[idx - 2] = int(M_list[idx - 2]) - int(M_list[idx - 1])
            M_list.pop(idx - 1)
            M_list.pop(idx - 1)
            idx -= 2
        elif M_list[idx] == '*':
            M_list[idx - 2] = int(M_list[idx - 2]) * int(M_list[idx - 1])
            M_list.pop(idx - 1)
            M_list.pop(idx - 1)
            idx -= 2
        elif M_list[idx] == '/':
            M_list[idx - 2] = int(M_list[idx - 2]) // int(M_list[idx - 1])
            M_list.pop(idx - 1)
            M_list.pop(idx - 1)
            idx -= 2
        idx += 1
print(M_list[0])
```



## code1169 주사위 던지기1(time 20m 진하피셜)

```bash
N, M = map(int, input().split())
dice_list = []
dice_list2 = []
dice_visit2 = []
dice_list3 = []
dice_visit3 = [True] * 7

def dice(n, m):
    if m == 1:
        if len(dice_list) == n:
            print(*dice_list)
            return
        for num in range(1, 7):
            dice_list.append(num)
            dice(n, m)
            dice_list.pop()
    elif m == 2:
        if len(dice_list2) == n:
            sort_list2 = sorted(dice_list2)
            if sort_list2 not in dice_visit2:
                dice_visit2.append(sort_list2)
                print(*dice_list2)
            return
        for num in range(1, 7):
            dice_list2.append(num)
            dice(n, m)
            dice_list2.pop()
    elif m == 3:
        if len(dice_list3) == n:
            print(*dice_list3)
            return
        for num in range(1, 7):
            if dice_visit3[num] is True:
                dice_list3.append(num)
                dice_visit3[num] = False
                dice(n, m)
                dice_visit3[num] = True
                dice_list3.pop()
dice(N, M)
```

