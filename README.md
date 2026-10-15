Задание №1
```python
from itertools import *
tab = ''.split()
pic = ''.split()
print(*range(1, 9 + 1))
for var in permutations(''):
    if all(str(var.index(y) + 1) in tab[var.index(x)] for x, y in pic):
        print(*var)
```

Задание №2
```python
from itertools import *
def f():
    return 
for x1, x2, x3 in product([0, 1], repeat=3):
    t = ((), (), ())
    if len(t) == len(set(t)):
        for p in permutations('xywz', r=4):
            if all(f(**dict(zip(p, line))) == line[-1] for line in t):
                print(*p)
```

Задание №3
```python
#Exel:
=ВПР(D2;Товар!A:F;3;0)

#LibreOffice:

#МосТех:

```

Задание №4
```
Это ваше дерево сюжета
Здесь видно, какие части вы прошли и какие пропустили 
Можете увидеть решения других игроков и, конечно, не только это
```

Задание №5
```python
for n in range(1, 100):
    s = bin(n)[2:]
    if s.count('1') % 2 == 0:
        s += '00'
    else:
        s += '10'
    r = int(s, 2)
    if r > 43:
        print(r)
        break

# Полезные строковые операции:
# s = bin(n)[2:].zfill(8)
# a = "12345"
# print(a[::-1])
# print(a[2:])
# print(sum(map(int, a)))
```

Задание №6
```python
from turtle import *
tracer(0)
screensize(1000, 1000)
k = 20

up()
for x in range(-100, 100):
    for y in range(-100, 100):
        goto(x * k, y * k)
        dot(3)
exitonclick()
```

Задание №7
```python
#Все в целом 
N = 2**i
I = k * i
8 бит = 1 байт
А дальше все 1024

#Музыка
I = stereo/mono * f * i * t
```

Задание №8
```python
c = 0
for x in product("АЕКНТЦ", repeat=5):
    c += 1
    x = "".join(x)
    if c % 2 == 0 and x[0] not in "АЕК" and x.count("Ц") >= 2:
        print(c)
        break
```

Задание №9
```python
f = open('9.txt')
lines = [list(map(int, c.split())) for c in f]
count_lines = 0
for line in lines:
    rep_3 = [c for c in line if line.count(c) == 3]
    rep_1 = [c for c in line if line.count(c) == 1]
    if (len(rep_3) == 3 and len(rep_1) == 3) and rep_3[0] ** 3 < rep_1[0] * rep_1[2] * rep_1[2]:
        count_lines += 1
        print(line)
print(count_lines)
```

Задание №10
```python
from ipaddress import ip_network

net = ip_network("122.131.8.0/255.255.252.0", False)
print("Адрес сети:", net[0])
print("Широковещательный:", net[-1])
print("Наименьший присваемый:", net[1])
print("Наибольший присваемый:", net[-2])
# bin_ip = bin(int(ip))[2:].zfill(32)
```

Задание №11
```python
N = 2**i
I = k * i
8 бит = 1 байт
А дальше все 1024
```

Задание №12
```python
#Сейчас BrainFuck:


#Раньше:
# s = '8' * 68
# while ('222' in s) or ('888' in s):
    # if '222' in s: 
        # s = s.replace('222', '8', 1)
    # else:
        # s = s.replace('888', '2', 1)
# print(s)
```

Задание №13
```python
def f(s, e):
    if s > e or s == 6 or s == 12:
        return 0
    if s == e:
        return 1
    return f(s + 1, e) + f(s * 2, e) + f(s + 3, e)
print(f(3, 16))
```

Задание №14
```python
# Количество заданных цифр
count = 0
a = 3 * 16**2018 - 2*8**1028 - 3 * 4**1100 - 2**1050 - 2022
while a > 0:
    if a % 4 == 3:
        count += 1
    a //= 4
print(count)

# Неизвестная цифра и делимость 
from string import printable
alp = printable[:15]
for x in alp:
    number = int(f'97968{x}15', 15) + int(f'7{x}233', 15)
    if number % 14 == 0:
        print(x, number // 14)
        
# Параметр в выражении и количество нулей 
def zeros_c(n):
    count = 0
    while n > 0:
        if n % 3 == 0:
            count+=1
        n //= 3
    return count

for x in range(1, 2031):
    number = 3**100 - x
    count = zeros_c(number)
    if count == 5:
        print(x)
```

Задание №15
```python
# Самое простое с x и y
for A in range(0, 1000):
    flag = True
    for x in range(0, 1000):
        for y in range(0, 1000):
            F = (x > A) or (y > A) or (x + 2*y < 80)
            if not F:
                flag = False
                break
        if not flag:
            break
    if flag:
        print(A)

# С отрезками
arr = []
P = range(17, 54 + 1)
Q = range(37, 83 + 1)
for left in range (10, 90):
    for right in range(left, 90):
        A = range(left, right + 1)
        flag = True
        for x in range(10, 90):
            F = (x in P) <= (((x in Q) and (x not in A)) <= (x not in P))
            if F == 0:
                flag = False
                break
        if flag:
            arr.append([right - left, left, right])
print(min(arr))

# С делителями 
for A in range(1, 1000):
    flag = True
    for x in range(1, 100_000):
        F = ((x % 2 == 0) <= (x % 3 != 0)) or (x + A >= 100)
        if not F:
            flag = False
            break
    if flag == True:
        print(A)
        
# Неотрицательно
for A in range(1000):
    flag = True
    for x in range(0, 100_000):
        F = (x & 29 != 0) <= ((x & 17 == 0) <= (x & A != 0))
        if F == 0:
            flag = False
            break
    if flag == True:
        print(A)
```

Задание №16
```python
#Через динамику:
f = {}
for n in range(3300):
    if n == 1:
        f[n] = 1
    if n > 1:
        f[n] = n * f[n-1]
print((f[3238]//2 + f[3237]) // f[3236])

# Ручками 
Мы должный представить все через f[3236], чтобы потом подставить в выражение, где само f[3236] сократится
f[3237] = 3237 *  f[3236]
f[3238] = 3238 *  f[3237] = 3238 * 3237 *  f[3236]
Подставляем: 
(3238 * 3237 *  f[3236] // 2 + 3237 *  f[3236]) // f[3236] =
= (3238 * 3237 // 2 +  3237) = 5243940 

# Рекурсия может просто не запустится при больших числах
from sys import setrecursionlimit
setrecursionlimit(10000)

def F(n):
    if n == 1:
        return 1
    elif n > 1:
        return n * F(n - 1)

print(F(2023) // F(2020))
```

Задание №17
```python
# Делимость пары
f = open("LFhIV7dQ8.txt")
arr = [int(x) for x in f]

min_17 = min(c for c in arr if c > 0 and c % 17 == 0)
print(min_17)

pairs = []
for i in range(len(arr) - 1):
    if arr[i] % min_17 == 0 or arr[i + 1] % min_17 == 0:
        pairs.append(arr[i] + arr[i + 1])
print(len(pairs), max(pairs))

# Полезные штучки 
count_5 = len([c for c in arr[i:i+3] if c % 5 == 0])
if count_5 == 1 # 
```

Задание №18
```
Копируем таблицу в ячейку V2. В ячейку V2 прописываем =МАКС(U2;V1)+A1
После этого стираем ячейки, куда мы попасть не можем 
Для потолков и стенок убираем из формулы невозможные варианты 
Выделяем финальные точки и смотрим максимальные 
После этого меняем везде МАКС на МИН и ищем минимальное 
```

Задание №19, 20, 21
```python
#Одна куча камней
def f(s, m):
    if s >= 26:
        return m % 2 == 0
    if m == 0: 
        return 0
    h = [f(s + 1, m - 1), f(s * 2, m - 1)]
    return any(h) if m % 2 != 0 else all(h) # только в 19 при неудачном комментируем весь if
print('19', [s for s in range(1, 26) if f(s, 2)])
print('20', [s for s in range(1, 26) if not f(s, 1) and f(s, 3)])
print('21', [s for s in range(1, 26) if not f(s, 2) and f(s, 4)])

#Две кучи камней
def f2(a, b, m):
    if a * b >= 63:
        return m % 2 == 0
    if m == 0:
        return 0
    h = [f2(a + 1, b, m - 1), f2(a, b + 1, m - 1), f2(a * 2, b, m - 1), f2(a, b * 2, m - 1)]
    return any(h) if m % 2 != 0 else all(h)  # только в 19 при неудачном комментируем весь if
print('19', [s for s in range(1, 32) if f2(2, s, 2)])
print('20', [s for s in range(1, 32) if not f2(2, s, 1) and f2(2, s, 3)])
print('21', [s for s in range(1, 32) if not f2(2, s, 2) and f2(2, s, 4)])
```

Задание №22
```
# Не душный тип
Столбец ID процесса --> Данные --> Текст по столбцам --> с разделителями --> точка с запятой --> общий
Сколько образовалось столбцов, столько и добавляем справа + последние два start и finish
В первую ячейку после ID записываем =ЕСЛИ(C2 = 0; 0; ВПР(C2; $A:$J; 10; 0)) и растягиваем горизонтально до start и fin 
В start пишем =МАКС(F2:H2)+1 (Диапазон выше + 1)
В finish пишем =МАКС(F2:H2)+B2 (Диапазон выше + время исполнения)

# Душный тип

```

Задание №25
```python
# Делители

# Маска
# from fnmatch import *
# for x in range(0, 10**8, 317):
#    if fnmatch(str(x), "12??1*56"):
#        print(x, x // 317)
```