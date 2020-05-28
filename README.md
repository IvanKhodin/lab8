# Лабораторная работа №8: численные методы решения уравнений в частных производных

#### Выполнил Ходин Иван, 427 группа

## Пример 1:


$$\begin{cases}$$
\frac{\partial u}{\partial t}= a\frac{\partial ^2 u}{\partial x^2}, a>0
\\u(0,t)=0
\\u(1,t)=0
\\u(x,0)=sin(2\pi x)
\end{cases}

Аналитическое решение: $$ u(x,t)=e^{-4\pi ^{2}at}sin(2\pi x) $$

## Теория: 

Рассмотрим задачу о распространении тепла на отрезке в случае простейших краевых условий 1-го рода
$$
u_{t}=a^{2}u_{xx}+f(x,t), 0<x<l, t>0
$$
Начальные условия:
$$
u(x,0)=\mu_{1}(x) \equiv \mu(x)
$$
однородные краевые условия:
$$
u(0,t)=\mu_{2}(t)\equiv 0; u(l, t)= \mu_{3} \equiv 0, t \underline{>}0
$$

Введём в области
$$
\overline{D}= [0;l] \times [0;T]
$$
сетку
$$
\Omega= \omega_{h} \times \omega_{tau}
$$
где
$$
\omega_{h}=\big\{ 0= x_{0} < x_{1} < ... < x_{N} = l \\
x_{n} = x_{0} + nh, h= \frac {x_{N}-x_{0}} {N} \big\}
$$
и
$$
\omega_{\tau}=\big\{ 0=t_{0}<t_{1}<...< t_{M}=T \\
t_{m}= t_{0}+ m\tau, \tau=\frac{T-t_{0}}{M} \big\}
$$

Рассмотрим сеточную функцию $$ y(x_n;t_m)= y^m_n=y $$ на сетке $$ \Omega \equiv \omega_{h,t} $$

После некоторых преобразований получаем разностную схему $$
\begin{cases} \frac{1}{\tau}(y^m+1_n-y^m_n)=a^2\Delta_h \big\{ \sigma \widehat{y}+ (1-\sigma)y \big\} + \Phi^m_n; (x_n, t_m) \in \omega_{h,t} \\
y^0_n=\chi_n; \\
y^m_0= y^m_N= 0 = \chi^m_{0,N} \end{cases} \\ \Delta_h y^m_n= \frac{1}{h^2}(y^m_{n+1}-2y^m_n+y^m_{n-1})
$$ 

## Результат:






## Пример 2:

Уравнение гиперболического типа 

$$
\begin{cases}
\frac{\partial ^2 u}{\partial t^2} = a^2\frac{\partial ^2 u}{\partial y^2}, a^2 > 0
\\u(0,t) = - sin(at)
\\u(\pi,y) = sin(at)
\\u(x,0) = sin(x)
\\ut(x,0) = -acos(x)
\end{cases}
$$

Аналитическое решение: $$ u(x,t) = sin(x - at) $$

## Теория: 

Рассмотрим задачу для уравнения колебаний на отрезке с краевыми условиями 1-го рода (задачу Дирихле)
$$ 
u_{tt}=a^{2}u_{xx}+f(x,t), 0<x<l, t>0 
$$
Начальные условия:
$$
u(x,0)=\mu_{1}(x), u_{t}(x,0)=\mu_{2}(x), t = 0, x \in [0,l] 
$$
краевые условия 1-го рода:
$$
u(0,t)=\mu_{3}(t)\equiv 0; u(l, t)= \mu_{4} \equiv 0, t \geq 0
$$

После некоторых преобразований получим краевую схему:
$$
\frac{y^{m+1}_{n} - 2y + y^{m-1}_{n}}{\tau} = a^2 \frac{y_{n+1} - 2y_{n} + y_{n-1}}{h^2} + \varphi^{m}_{n}
$$
краевые условия: 
$$ 
y^{m}_{0} = \chi^{m}_{3} = \mu_{3}(t_{m}) \equiv 0;  y^{m}_{n} = \chi^{m}_{4} = \mu_{4}(t_{m}) \equiv 0;
$$
начальные условия: 
$$
y^{0}_{n} = \chi_{1}(x_{n}) = \mu_{1}(x_{n})
$$

## Результат:



## Пример 3: 

Уравнение эллиптического типа 

$$
\begin{cases}
\frac{\partial ^2 u}{\partial x^2} + \frac{\partial ^2 u}{\partial y^2} = 0
\\u(0,y) = y
\\u(1,y) = 1 + y
\\u(x,0) = x
\\u(x,1) = 1 + x
\end{cases}
$$

Аналитическое решение: $$ u(x,t) = x + y $$

## Теория:

Рассмотрим задачу о распределении тепла в прямоугольной области:
$$
\begin{cases} u_l=a^2(u_{x_{1}x_1} + u_{x_{2}x_2})+ f(x_1, x_2, t), 0<x_1<l_1, 0< x_2< l_2, 0<l
\\ u|_Г= \mu_Г(l)
\\ u|_{t=0}= \mu(x1, x2) \end{cases}
$$

Рассмотрим в 
$$ 
\overline{D} 
$$ 
равномерную сетку:
$$
\overline{\omega_{h_1, h_2, \tau}}= \big\{ (x_{1n}, x_{2k}, l_m): x1_{1n}= nh_1; n= \overline{1,N}; h_1=\frac{l_1}{N} \\
x_{2k}= kh_2; k= \overline{1,K}; h_1=\frac{l_2}{K} \\
t_m= m\tau; m= \overline{1,M}; \tau=\frac{T}{M} \big\}
$$

После некоторых преобразований получим аппроксимацию основного уравнения задачи:
$$
\frac{1}{\tau}(\widehat y_{n,k}- y_{n,k})= a^2(\Delta_1 + \Delta_2)[\sigma \widehat y_{n,k} + (1- \sigma)y_{n,k} ] + \Phi^m_{n,k} \\
\Delta_2 y=\frac{1}{h^2_2}(y_{n,k+1}- 2y_{n,k} + y_{n,k-1}) \\
\Delta_1 y=\frac{1}{h^2_1}(y_{n+1,k}- 2y_{n,k} + y_{n-1,k})
$$


## Результат: 


