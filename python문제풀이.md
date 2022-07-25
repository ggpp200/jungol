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



## code2071 파스칼 삼각형(time 1h 23m 39s)

```bash
n, m = map(int, input().split())
pascal_list = []
if m == 2:
    pascal_list = list([0] * 2 * n for _ in range(n))
    pascal_list[n - 1][n - 1] = 1
    for i in range(n-1, -1, -1):
        for j in range(n * 2):
            if pascal_list[i][j] == 0:
                pascal_list[i][j] = ''
            else:
                y = i - 1
                x = j - 1
                if 0 <= y and 0 <= x:
                    pascal_list[y][x] += pascal_list[i][j]
                    x = j
                    if x < n * 2 - 1:
                        pascal_list[y][x] += pascal_list[i][j]

else:
    pascal_list = list([0] * n for _ in range(n))
    pascal_list[0][0] = 1
    for i in range(n):
        for j in range(n):
            if pascal_list[i][j] == 0:
                pascal_list[i][j] = ''
            else:
                y = i + 1
                x = j
                if y < n and x < n - 1:
                    pascal_list[y][x] += pascal_list[i][j]
                    pascal_list[y][x + 1] += pascal_list[i][j]
    if m == 3:
        for i in range(n):
            for j in range(n):
                if i + j < n-1:
                    pascal_list[i][j], pascal_list[n - j - 1][n - i - 1] = pascal_list[n -j - 1][n - i - 1], pascal_list[i][j]
                else:
                    break

for i in range(n):
    print(*pascal_list[i])
```





## code1707 달팽이사각형(time 18m 36s)

```bash
n = int(input())
number = 1
pascal_list = list([0] * n for _ in range(n))
move = 0
di = [0, 1, 0, -1]
dj = [1, 0, -1, 0]
i, j = 0, 0
while 1:
    stop = 0
    pascal_list[i][j] = number
    number += 1
    for corner in range(2):
        new_move = (move + corner) % 4
        y = i + di[new_move]
        x = j + dj[new_move]
        if 0 <= y < n and 0 <= x < n and pascal_list[y][x] == 0:
            i = y
            j = x
            move = new_move
            break
        else:
            stop += 1
    if stop == 2:
        break

for i in range(n):
    print(*pascal_list[i])
```



## code1331 문자마름모(time 1h 54m 12s)

```bash
n = int(input())
alpha_list = list([' '] * (n * 2 - 1) for _ in range((n * 2) - 1))
alpha = 65
di = [1, 1, -1, -1, 0]
dj = [-1, 1, 1, -1, -1]
move = 0
i = 0
j = n - 1
while 1:
    stop = 0
    alpha_list[i][j] = chr(alpha)
    for add in range(3):
        new_move = (move + add) % 5
        y2 = i + di[new_move]
        x2 = j + dj[new_move]
        if 0 <= y2 < ((n * 2) - 1) and 0 <= x2 < ((n * 2) - 1) and alpha_list[y2][x2] == ' ':
            if n - 1 <= x2 + y2 < (n * 3) - 2:
                if abs(x2 - y2) < n:
                    i = y2
                    j = x2
                    move = new_move
                    alpha += 1

                    if alpha > 90:
                        alpha -= 26
                    break

        stop += 1
    if stop == 3:
        break
for idx in range((n * 2) - 1):
    print(*alpha_list[idx])
```



## code1495 대각선 지그재그(time 30m 20s)

```bash
n = int(input())
number = 1
field = list([0] * n for _ in range(n))
di = [1, -1, 0, 1]
dj = [0, 1, 1, -1]
case = 0
i = 0
j = 0
while 1:
    if i == n - 1 and j == 0:
        di = [0, -1, 1, 1]
        dj = [1, 1, 0, -1]
    stop = 0
    field[i][j] = number
    for f_i in range(2):
        y = i + di[(case + f_i) % 4]
        x = j + dj[(case + f_i) % 4]
        if 0 <= y < n and 0 <= x < n and field[y][x] == 0:
            i = y
            j = x
            case = (case + f_i) % 4
            if case % 2 == 0:
                case += 1
            number += 1
            break
        stop += 1
    if stop == 2:
        break

for idx in range(n):
    print(*field[idx])

```



## code2074 홀수 마방진(time 11m 40s)

```bash
n = int(input())
number = 1
field = list([0] * n for _ in range(n))
di = [1, -1, 0, 1]
dj = [0, 1, 1, -1]
case = 0
i = 0
j = n // 2
while 1:
    if field[i][j] == 0:
        field[i][j] = number
    else:
        break
    if number % n == 0:
        i = i + 1
    else:
        i -= 1
        j -= 1
    if 0 > i:
        i = n - 1
    if i > n - 1:
        i = 0
    if 0 > j:
        j = n - 1
    number += 1
for idx in range(n):
    print(*field[idx])
```



## code1009 각 자리수의 역과 합(time 45m 20s)

```bash
while 1:
    number = int(input())
    case = 0
    if number == 0:
        break
    number_list = []
    while number != 0:
        number_list.append(number % 10)
        number = number // 10
    for i in range(len(number_list)):
        if number_list[i] != 0:
            case = 1
        if case != 0:
            print(number_list[i], end='')
    print('', end=' ')
    print(sum(number_list), end='')
    print()
        


```



## code2811 소수와 합성수(time 29m 15s)

```bash
number_list = list(map(int, input().split()))
for idx in range(len(number_list)):
    cnt = 0
    for i in range(1, int(number_list[idx] ** (1/2)) + 1):
        if number_list[idx] == 1:
            break
        if number_list[idx] % i == 0:
            cnt += 1
    if cnt == 0:
        print('number one')
    elif cnt == 1:
        print('prime number')
    else:
        print('composite number')


```



## code1901 소수 구하기(time  30m)

```bash
def prime(num):
    cnt = 0
    p_i = 2
    while p_i <= num ** (1/2):
        if num % p_i == 0:
            num = num // p_i
            cnt += 1
        else:
            p_i += 1
        if cnt > 1:
            break
    if num != 0:
        cnt += 1
    if cnt == 1:
        return 0
    else:
        return 1




N = int(input())
for test_c in range(N):
    number = int(input())
    num_i = 0
    flag = 0
    while 1:
        if num_i != 0:
            if prime(number - num_i) == 0:
                flag = 1
                print(f'{number - num_i}', end=' ')

        if prime(number + num_i) == 0:
            flag = 1
            print(f'{number + num_i}', end=' ')
        num_i += 1
        if flag == 1:
            break
    print()
```



## code1740 소수(time 1h 1m 58s)

```bash
def prime(num):
    num_div = 2
    num_max = int(num ** (1/2)) + 1
    if num == 1:
        return 0
    while num_div <= num_max:
        if num % num_div == 0 and num != num_div:
            return 0
        else:
            num_div += 1
    return 1


M = int(input())
N = int(input())
prime_list = []
for number in range(M, N + 1):
    if prime(number) == 1:
        prime_list.append(number)
if len(prime_list) > 0:
    print(sum(prime_list))
    print(min(prime_list))
else:
    print(-1)
```



## code2813 소수의 개수(time 2h 44m 14s)

```bash
def make_list():
    prime_list[0] = 1
    prime_list[1] = 1
    l_num = int(2000001 ** (1 / 2) + 1)
    for l_n in range(2, l_num):
        if prime_list[l_n] == 0:
            for l_n_n in range(l_n + 1, l_num):
                if l_n_n % l_n == 0:
                    prime_list[l_n_n] = 1

def prime(num):
    for div in new_list:
        if div < num and num % div == 0:
            return 0
    return 1



M, N = map(int, input().split())
cnt = 0
prime_list = [0] * int(2000001 ** (1 / 2) + 1)
make_list()
new_list = []
for n_l_i in range(len(prime_list)):
    if prime_list[n_l_i] == 0:
        new_list.append(n_l_i)
for number in range(M, N + 1):
    if prime(number) == 1:
        cnt += 1
if M == 1:
    cnt -= 1
print(cnt)
```



## code2814 이진수(time 4m 33s)

```bash
bin_num = int(input())
cnt = 0
sum_num = 0
while bin_num > 0:
    sum_num += bin_num % 10 * 2 ** (cnt)
    cnt += 1
    bin_num = bin_num // 10
print(sum_num)
```



## code2814 10진수를 2,8,16진수로(time 26m 13s)

```bash
def change(num, T):
    change_list = []
    chr_list = [
        'A', 'B', 'C', 'D', 'E', 'F'
    ]
    c_cnt = 0
    while num > -1:
        mul = T ** (c_cnt - 1)
        if num < mul * T:
            change_list.append(num // mul)
            num = num - mul * (num // mul)

            c_cnt -= 1
        else:
            c_cnt += 1
        if num < T:
            change_list.append(num)
            break
    for c_num in change_list:
        if c_num > 9:
            print(chr_list[c_num - 10], end='')
        else:
            print(c_num, end='')

M, N = map(int, input().split())
change(M, N)
```



## code3106 진법 변환(time 2h 6m 51s)

```bash
def change(before, num, after):
    num_list = []
    dicimal_num = 0
    dicimal_i = 0
    after_list = []
    num_dic = {
                '0': 0, '1': 1, '2': 2, '3': 3, '4': 4,
                '5': 5, '6': 6, '7': 7, '8': 8, '9': 9,
                'A': 10, 'B': 11, 'C': 12, 'D': 13, 'E': 14,
                'F': 15, 'G': 16, 'H': 17, 'I': 18, 'J': 19,
                'K': 20, 'L': 21, 'M': 22, 'N': 23, 'O': 24,
                'P': 25, 'Q': 26, 'R': 27, 'S': 28, 'T': 29,
                'U': 30, 'V': 31, 'W': 32, 'X': 33, 'Y': 34,
                'Z': 35}

    decode_list = [
        'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M',
        'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'
    ]
    for one_num in num:
        num_list.append(num_dic[one_num])
    for list_i in range(len(num_list)):
        dicimal_num += num_list[list_i] * before ** (len(num_list) - list_i - 1)
    if before == 10:
        a = 1
    while dicimal_num > -1:
        floor = after ** dicimal_i
        if dicimal_num < floor * after:
            if dicimal_num // floor > 9:
                after_list.append(decode_list[dicimal_num // floor - 10])
            else:
                after_list.append(str(dicimal_num // floor))
            dicimal_num = dicimal_num - (dicimal_num // floor) * floor
            dicimal_i -= 1
        else:
            dicimal_i += 1
        if dicimal_i == -1:
            break
    word = ''.join(after_list)
    print(word)


while 1:
    AsB = list(input().split())
    if AsB[0] == '0':
        break
    else:
        change(int(AsB[0]), AsB[1], int(AsB[2]))

```



## code4977 실수의 이진수(time 3h)

```b
def make_int(num):
    floor_i = 0
    bin_list = []
    while num >= 0:
        floor = 2 ** floor_i
        if num < floor * 2:
            div = num // floor
            bin_list.append(str(div))
            num = num - div * floor
            floor_i -= 1
        else:
            floor_i += 1
        if num == 0:
            while floor_i >= 0:
                floor_i -= 1
                bin_list.append('0')
            return bin_list

def make_float(num):
    bin_list = []
    for i in range(1, 5):
        if num - 2 ** (-i) >= 0:
            num = num - 2 ** (-i)
            bin_list.append('1')
        else:
            bin_list.append('0')
    return bin_list

N = float(input())
N_int = int(N)
N_float = N - N_int
a = make_int(N_int)
b = make_float(N_float)
if len(a) > 0:
    print(''.join(a), end='')
else:
    print(0, end='')
print('.', end='')
if len(b) > 0:
    print(''.join(b), end='')

```



## code2604 그릇(time  5m 19s)

```bash
bowl_list = input()
before = 0
width = 0
for bowl in bowl_list:
    if before == 0:
        before = bowl
        width += 10
    elif before == bowl:
        width += 5
    else:
        before = bowl
        width += 10
print(width)
```



## code2514 문자열 찾기(time 12m 32s)

```bash
word_list = input()
K_cnt = 0
I_cnt = 0
idx = 2
while idx < len(word_list):
    if word_list[idx] == 'I':
        if word_list[idx - 2] == 'K':
            if word_list[idx - 1] == 'O':
                K_cnt += 1
            idx += 2

        elif word_list[idx - 2] == 'I':
            if word_list[idx - 1] == 'O':
                I_cnt += 1
            idx += 2
        else:
            idx += 2
    else:
        idx += 1
print(K_cnt)
print(I_cnt)
```



## code2857 세로읽기(time 37m 55s)

```bash
word_list = list(input() for _ in range(5))
on_off = []
for l_i in range(5):
    on_off.append(len(word_list[l_i]))
max_i = 0
for o_i in on_off:
    if max_i < o_i:
        max_i = o_i
i = 0
new_list = []
while max_i > i:
    for j in range(5):
        if on_off[j] > i:
            new_list.append(word_list[j][i])
    i += 1
print(''.join(new_list))
```



## code1880 암호풀기(Message Decoding)(time 49m 57s)

```bash
code_list = input()
word_list = input()

new_list = []
for word in word_list:
    ord_num = ord(word)
    if word == ' ':
        new_list.append(' ')
    elif 64 < ord_num < 91:

        new_list.append(chr(ord(code_list[ord_num - 65]) - 32))
    else:
        new_list.append(chr(ord(code_list[ord_num - 97])))
print(''.join(new_list))

```



## code1535 단어집합2(time 31m 2s)

```bash
overlap = []
while 1:
    word_list = input().split()
    if word_list[0] == 'END':
        break
    for word in word_list:
        if word not in overlap:
            overlap.append(word)
    print(*overlap)
```



## code 4987 STL - String(time 1h 51m 9s)

```bash
S = list(input())
T = list(input())
first_list = []
for idx in range(len(S)):
    if S[idx] == T[0]:
        first_list.append(idx)
while len(first_list):
    cnt = 0
    for i in first_list:
        if i + len(T) - 1 <= len(S):
            if S[i:i + len(T)] == T[0:len(T)]:
                for _ in range(i, i + len(T)):
                    S.pop(i)
                s_i = 0
                while s_i < len(first_list):
                    if first_list[s_i] == i:
                        first_list.pop(s_i)
                        s_i -= 1
                    elif first_list[s_i] > i:
                        first_list[s_i] = first_list[s_i] - len(T)
                    if s_i == len(first_list) - 1:
                        break
                    s_i += 1
                cnt += 1
    if cnt == 0:
        break
print(''.join(S))

```



## code 5096 STL - String 2 (stringstream)(time 16m 39s)

```bash
word_list = list(input().split())
print(*sorted(word_list))
```



## code 1516 단어세기(time 1h 4m 41s)

```bash
while 1:
    word_dict = dict()
    word_list = input().split()
    if word_list == ['END']:
        break
    for word_i in range(len(word_list)):
        key = word_list[word_i]
        if key in word_dict:
            word_dict[key] += 1
        else:
            word_dict[key] = 1
    sort_list = sorted(word_list)
    if sort_list != ['END']:
        before = 0
        for key in sort_list:
            if before != key:
                before = key
                print(f'{key} : {word_dict[key]}')
```



## code3699 변장(time 7h 38m 15s)

```bash
TC = int(input())
for test_case in range(0, TC):
    costume_dict = dict()
    costume_num = int(input())
    costume_list = list(input().split() for _ in range(costume_num))
    for i in range(costume_num):
        key = costume_list[i][1]
        if key in costume_dict:
            costume_dict[key] += 1
        else:
            costume_dict[key] = 2
    value = 1
    key_num = costume_dict.keys()
    for add_value in key_num:
        value = value * costume_dict[add_value]
    print(value - 1)
```



## code1438 색종이(초)(time 21m 37s)

```bash
paper_num = int(input())
template = list([0]*100 for _ in range(100))
for _ in range(paper_num):
    x_y = list(map(int, input().split()))
    for i in range(10):
        for j in range(10):
             template[x_y[1] + i][x_y[0] + j] = 1
sum_num = 0
for i in range(100):
    sum_num += sum(template[i])
print(sum_num)
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

