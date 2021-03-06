
Copy of Lesson_6.ipynb
Copy of Lesson_6.ipynb_
Урок 6
Производная функции одной переменной. Часть 1
Определение
На прошлом уроке мы рассмотрели понятия образа и прообраза из теории множеств, а также несколько случаев отображения одного на другое. Через которые в дальнейшем дали определение функциям.

Понятие производной, в свою очередь, характеризует степень изменения образа отображения при (бесконечно) малом изменении прообраза. Производные используются во многих математических дисциплинах, но самое широкое распространение получили в курсе математического анализа и дифференциального исчисления.

Давайте дадим математическое определение производной явной функции. Возьмем функцию  y=f(x) . Возьмем точку  x  и отойдем от нее на расстоянии  Δx . При этом у нас получится два значения функции  f(x)  и  f(x+Δx) . Для определения скорости изменения значения функции от изменения аргумента достаточно найти отношение  f(x+Δx)−f(x)Δx . Но в таком случае мы найдем среднее значение функции на участи от  x  до  x+Δx . Для нахождения изменения функции в конкретной точке, нужно перейти к пределам. Если мы устреми  Δx  к  0 , точка  x+Δx  устремиться к  x . Данный предел как раз и является производной явной функции.
f′(x)=limΔx→0f(x+Δx)−f(x)Δx 


Теперь давайте найдем производную от простой степенной функции  f(x)=x2 , воспользовавшись определением, которое дали выше

(x2)′=limΔx→0(x+Δx)2−x2Δx=limΔx→0x2+2xΔx+(Δx)2−x2Δx=limΔx→0(2x+Δx)=2x 

К счастью для нас существует связь между типом функции и ее производной. Поэтому поиск производных не скатывается к рутинному поиску предела. Для овладения навыком поиска производных явных функций достаточно знать таблицу производных. А так же три дополнительных правила, которые обсудим чуть позже.

Итак, таблица производных основных функций.

a′=0,где a−константа 

(xa)′=axa−1 

(sin(x))′=cos(x) 

(cos(x))′=−sin(x) 

(tg(x))′=1cos2(x) 

(ctg(x))′=−1sin2(x) 

(arcsin(x))′=11−x2−−−−−√ 

(arccos(x))′=−11−x2−−−−−√ 

(arctg(x))′=11+x2 

(arcctg(x))′=−11+x2 

(ax)′=anlna 

(ex)′=en 

(logax)′=1xlna 

(lnx)′=1x 

Существование
Условие существование производной можно понять через условие существования предела. Выделим несколько случаев когда производная в точке не существует.

Например производная не существует, если у предела
limΔx→0f(x+Δx)−f(x)Δx=f′(x) 
значения односторонних пределов в точке  x  не совпадает. Обычно сама функция  f(x)  в этом случае проходит через точку  x  "не гладко". В качестве хорошего примера можно взять функцию  y=|x| 

[ ]
from matplotlib import pylab as plt
import numpy as np
%matplotlib inline

x=np.linspace(-8, 8, 200)
y=np.fabs(x)
plt.plot(x,y)

Так же можно выделить случай, когда точка  х , в которой определена функция  y=f(x) , является граничной и имеет область только с одной стороны. В качестве примера можно взять функцию  y=x−−√ , определенной в нуле. При этом ноль является пограничной точкой. Производная функции равна  y′=12x√ . При этом в нуле производная уже не существует.

[ ]
x=np.linspace(0, 8, 200)
y=np.sqrt(x)
plt.plot(x,y)

Дополнительные правила и свойства
производная от произведения:
(U⋅V)′=U′⋅V+U⋅V′ 

производная от частного:
(UV)′=U′⋅V−U⋅V′V2 

производная от сложной функции:
f′(g(x))=f′⋅g′ 

вынесение константы:
(af(x))′=af′(x) 

производная от суммы:
(f(x)+g(x))′=f′(x)+g′(x) 

Примеры
Начнем с производной от произведения

(x⋅sinx)′=sinx+x⋅cosx 

и от частного

(xsinx)′=sinx−x⋅cosxsin2x 

Так же разберемся с производными от сложных функций. Наверное, всем знакома сказка про Кашея. Смерь его была в игле, игла в яйце, яйце в утке и т.д.. Так вот со сложными функциями так же. Нам нужно понять - на сколько "простых" функций можно разбить сложную, найти производную от каждой и взять произведение. Сколько функций - столько и производных!

(sin(2x+1))′=cos(2x+1)⋅2 

(sin(x2+2x+1))′=cos(x2+2x+1)⋅(2x+2) 

(sin3(x2+2x+1))′=3sin2(x2+2x+1)⋅cos(x2+2x+1)⋅(2x+2) 

(ln(sin3(x2+2x+1)+1))′=1sin3(x2+2x+1)+1⋅3sin2(x2+2x+1)⋅cos(x2+2x+1)⋅(2x+2) 

Из особенный производных можно выделить производные от натуральных логарифмов.

(lnx)′=1x 

(ln3x)′=(ln3+lnx)′=1x 

(lnx3)′=(3lnx)′=3x 

(lnsinx⋅(x+1)3(x−4)5)′=cosxsinx+3x+1−5x−4 

Для любой функцию, которую можно представить в степенном виде, производную желательно искать именно в степенном виде.

(x2)′=2x 

(1x2)′=(x−2)′=−2x−3=−2x3 

(x−−√)′=(x12)′=12x−12=12x−−√ 

(1x+1−−−−√)′=((x+1)−12)′=−12(x+1)−32=−12(x+1)3−−−−−−−√ 

Провеять найденные производные можно с помощью библиотеки sympy, которая поддерживает символьную алгебру. Особого прикладного значения это не имеет, т.к. основные данные, с которыми Вы будете сталкиваться в работе, имеют дискретный вид. На следящем уроке мы с Вами разберем как находить производные численно. Аналитический

[ ]
from sympy import *
init_printing()
[ ]
a=Symbol('a') # для одной переменной Symbol
b=Symbol('b')
x=a+b
x


[ ]
c,d=symbols('c d') # для нескольких переменных symbols
y = x.subs(b,(c+d)**2) # подставили значения в х и сохранили в у
y

[ ]
x.expand(a) # х не изменился

[ ]
y.expand(a)

[ ]
z=y.subs({a:3,c:d, d:1}) # так же можно подставлять числа
z

[ ]
print (type(z))
print (type(7/z))
print (type(7.0/z))
print (type(float(7.0/z)))

[ ]
x=Symbol('x')
f=x*sin(x)
diff(f,x)

[ ]
x=Symbol('x')
f=x/sin(x)
f = diff(f,x)
#f = together(f)
f

[ ]
x=Symbol('x')
f=1/sqrt(x+1)
diff(f,x)

[ ]
x=Symbol('x')
f=x**3
diff(f,x)
#diff(g,x)
#diff(f,x,2)
#diff(f,x,3)

Пределы
[ ]
x=Symbol('x')
f=sin(x)/x
f

[ ]
limit (f,x,0)

[ ]
x=Symbol('x')
f=(3*x*tan(4*x))/(1-cos(4*x))
f

[ ]
limit (f,x,0)

[ ]
x=Symbol('x')
f=(23-2*x**2)*(3*x**2+17)**2/(4*x**6+x-1)
f

[ ]
limit (f,x,oo)

[ ]
x=Symbol('x')
f=(sqrt(2)*x**2*sin(4*x))/(1-cos(2*x))**(3/2)
f

[ ]
#limit (f,x,0)
Приближенное вычисление с помощью производных
Мы с Вами дали определение производной явной функции

f′(x)=limΔx→0f(x+Δx)−f(x)Δx 

Если из равенства убрать предел, то значение левой и правой части уже не будут равны. Но при достаточно малом  Δx  будут близки.

f′(x)≈f(x+Δx)−f(x)Δx 

Если выразить  f(x+Δx) , то получим следующее выражение:

f(x+Δx)≈f(x)+f′(x)⋅Δx 

Давайте воспользуется этим выражением для приближенного вычисления  3–√≈1.7320508075688772 

3–√=4−1−−−−√≈4–√+124–√⋅(−1)=2−0.25=1.75 

Как видно, ошибка уже во втором знаке.

Чтобы увеличить точность, необходимо уменьшить приращение. для этого достаточно  3=3.00  и подобрать ближайший хороший корень к  300 

3–√=3.00−−−−√=2.89+0.11−−−−−−−−−√≈2.89−−−−√+122.89−−−−√⋅0.11=1.7+0.112⋅1.7≈1.73235294117647 

Практическое задание
1. Найти производную функции:

y=1x+2x2−5x3+x−−√−x−−√3+3x−−√ 

2. Найти производную функции:

y=x⋅1+x2−−−−−√ 

3. Найти производную функции:

y=2x1−x2 

4*. Найти производную функции:

y=x+x+x−−√−−−−−−√−−−−−−−−−−−√ 

5. Найти производную функции:

y=ln(x+x2+1−−−−−√) 

6. Найти производную функции:

y=x⋅ln(x+x2+1−−−−−√)−x2+1−−−−−√ 

7*. Найти производную функции:

y=arcsin(sinx) 

8*. Вычислить приближенное значение:

sin(10)=sin(π180) 

9**. Написать на python алгоритм, по вычислению значений  sin(x)  для  х∈[0,50] 

Для проверки подойдут данные из таблицы Брадиса

sin(0)=0.0000 

sin(10)=0.0175 

sin(20)=0.0349 

sin(30)=0.0523 

sin(40)=0.0698 

sin(50)=0.0872 

Дополнительные материалы
SymPy
Loading...