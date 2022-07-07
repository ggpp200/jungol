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



## code1692 곱셈(time 6m 11s)

```bash
num1 = int(input())
num2 = int(input())
for per in range(3):
    num_right = num2 // (10 ** per) % 10
    print(num1 * num_right)
print(num1 * num2)
```



## code1430 숫자의 개수(time 12m 37s)

```bash
A = int(input())
B = int(input())
C = int(input())
num_list = [0] * 10
value = A * B * C
while value > 0:
    num_list[value % 10] += 1
    value = value // 10

for i in range(10):
    print(num_list[i])


```



## code1071 약수와 배수(time 5m 27s)

```bash
N = int(input())
N_list = list(map(int, input().split()))
divisor_list = []
multiple_list = []
number = int(input())
for one_N in N_list:
    if number % one_N == 0:
        divisor_list.append(one_N)
    if one_N % number == 0:
        multiple_list.append(one_N)
print(sum(divisor_list))
print(sum(multiple_list))
```



## code1402 약수구하기(time 3m 31s)

```bash
N, K = map(int, input().split())
order = 0
value = 0
for N_div in range(1, N):
    if N % N_div == 0:
        order += 1
    if order == K:
        value = N_div
        break
print(value)

```



## code2809 약수(time 9m 19s)

```bash
N = int(input())
sq = int(N ** (1/2))
N_list = []
for N_div in range(1, sq + 1):
    if N % N_div == 0:
        N_list.append(N_div)
        if N_div != N // N_div:
            N_list.append(N // N_div)
N_list.sort()
print(*N_list)

```



## code1658 최대공약수와 최소공배수(time  42m)

```bash
N, M = map(int, input().split())
N_list = [0] * 10001
M_list = [0] * 10001
N_max_idx = 0
M_max_idx = 0
max_idx = 0
min_num = 1
max_num = 1
case = 0
for num in [N, M]:
    case += 1

    while 1 < num:
        for div in range(2, num + 1):
            if num % div == 0:
                num = num // div
                if case == 1:
                    N_list[div] += 1
                    if N_max_idx < div:
                        N_max_idx = div
                else:
                    M_list[div] += 1
                    if M_max_idx < div:
                        M_max_idx = div
if N_max_idx > M_max_idx:
    max_idx = N_max_idx
else:
    max_idx = M_max_idx

for i in range(2, max_idx + 1):

    if N_list[i] < M_list[i]:
        if N_list[i] != 0:
            min_num = min_num * i ** N_list[i]
        if M_list[i] != 0:
            max_num = max_num * i ** M_list[i]
    else:
        if M_list[i] != 0:
            min_num = min_num * i ** M_list[i]
        if N_list[i] != 0:
            max_num = max_num * i ** N_list[i]
print(min_num)
print(max_num)
```



## code1002 최대공약수, 최소공배수(time  45m 41s)

```bash
T = int(input())
number_list = list(map(int, input().split()))
div_list = [[0] * 10001 for _ in range(T)]
list_max_idx = 0
M_max_idx = 0
min_div_all = 1
max_div_all = 1
case = 0
for num in number_list:
    while 1 < num:
        for div in range(2, num + 1):
            if num % div == 0:
                num = num // div
                div_list[case][div] += 1

                if list_max_idx < div:
                    list_max_idx = div
                break

    case += 1

for div in range(2, list_max_idx + 1):

    min_div = 10000
    max_div = 0
    flag = 0
    for i in range(0, T):
        if div_list[i][div] != 0:
            a = div_list[i][div]
            if max_div < div_list[i][div]:
                max_div = div_list[i][div]
            if min_div > div_list[i][div] and flag == 0:
                min_div = div_list[i][div]
        else:
            flag = 1
            min_div = 0
    if min_div != 10000:
        min_div_all = min_div_all * div ** min_div
    if max_div != 0:
        max_div_all = max_div_all * div ** max_div

print(f'{min_div_all} {max_div_all}')
```



## code1523 별삼각형1(time 1h 22m 45s)

```bash
n, m = map(int, input().split())
m3_list = [' '] * (n)
star = 0
case = 0
if 1 <= m <= 3 and 1 <= n <= 100:
    if m == 1:
        star = 1
    elif m == 2:
        star = n
    else:
        star = 1
    for floor in range(n):
        star_output = star
        if m == 1:
            for i in range(star_output):
                print('*', end='')
            star += 1
        elif m == 2:
            for i in range(star_output):
                print('*', end='')
            star -= 1
        elif m == 3:
            i = 0
            while i < n:
                m3_list[n - 1 - i] = '*'
                if i != 0:
                    m3_list.append('*')
                for m3 in m3_list:
                    print(m3, end='')
                print()
                case = 1
                i += 1
            star += 1
            if case == 1:
                break
        print()
else:
    print("INPUT ERROR!")
```



## code1719 별삼각형2(time 1h 12m)

```bash
n, m = map(int, input().split())
first_star_list = [0, 1, 1, n // 2, n // 2]


if 1 <= n < 100 and n % 2 == 1 and 1 <= m <= 4 and m % 1 == 0:
    star = first_star_list[m]
    if m == 1:
        for idx in range(n):
            for _ in range(star):
                print('*', end='')
            if idx - n // 2 < 0:
                star += 1
            else:
                star -= 1
            print()
    elif m == 2:
        for idx in range(n):
            for jdx in range(n // 2 + 1):
                if (n // 2) - jdx < star:
                    print('*', end='')
                else:
                    print(end=' ')
            if idx - n // 2 < 0:
                star += 1
            else:
                star -= 1
            print()
    elif m == 3:
        for idx in range(n):
            for jdx in range(n):
                if n // 2 - star <= jdx <= n // 2 + star:
                    print('*', end='')
                else:
                    print(end=' ')
            if idx - n // 2 < 0:
                star -= 1
            else:
                star += 1
            print()
    else:
        for idx in range(n):
            for jdx in range(n):
                half = n // 2
                if half - star <= jdx <= half + star:
                    if (idx <= half and jdx <= half) or (idx >= half and jdx >= half):
                        print('*', end='')
                    else:
                        print(end=' ')
                else:
                    print(end=' ')
            if idx - n // 2 < 0:
                star -= 1
            else:
                star += 1
            print()


else:
    print("INPUT ERROR!")
```



## code1329 별삼각형3(time 4m 51s)

```bash
N = int(input())
star = 1
before_star = 0

if 1 <= N <= 99 and N % 2 == 1:
    for y_star in range(N):
        for _ in range(before_star):
            print(end=' ')
        for _ in range(star):
            print('*', end='')
        print()
        if y_star < N // 2:
            before_star += 1
            star += 2
        else:
            before_star -= 1
            star -= 2

else:
    print("INPUT ERROR!")
```





## code1641  숫자삼각형(time 56m 42s)

```bash
n, m = map(int, input().split())
number = 1
j_number = 0
before_star = 0

if 1 <= n <= 99 and n % 2 == 1 and 1 <= m <= 3 and m % 1 == 0:
    for i in range(n):
        if m == 1:
            j_number = number
            for j in range((i + 1)):
                if i % 2 == 0 and j != 0:
                    j_number += 1
                elif j != 0:
                    j_number -= 1
                print(j_number, end=' ')
            if i % 2 == 0:
                number += (i + 1) * 2
            else:
                number += 1
            print()

        elif m == 2:
            for j in range(n * 2 - 1):
                if i <= j < n * 2 - i - 1:
                    print(i, end=' ')
                else:
                    print(' ', end=' ')
            print()

        else:
            for j in range(number):
                print(j + 1, end=' ')
            if i < n // 2:
                number += 1
            else:
                number -= 1
            print()

else:
    print("INPUT ERROR!")
```



## code1337  달팽이삼각형(time 1h 22m 06s)

```bash
N = int(input())
number = 0

field = list([''] * N for _ in range(N))
case_list = [[1, 1], [0, -1], [-1, 0]]
case = 0
i = 0
j = 0
while 1:
    field[i][j] = number
    y = i + case_list[case][0]
    x = j + case_list[case][1]
    if 0 <= y < N and 0 <= x < N and field[y][x] == '':

        i = y
        j = x
    else:
        case = (case + 1) % 3
        y2 = i + case_list[case][0]
        x2 = j + case_list[case][1]
        if 0 <= y2 < N and 0 <= x2 < N:
            if field[y2][x2] == '':
                i = y2
                j = x2
            else:
                break
        else:
            break
    number += 1
    if number % 10 == 0:
        number = 0

for line in range(N):
    print(* field[line])
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

