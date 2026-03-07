---
sticker: emoji//1f1eb-1f1f7
---
## Определение
### Локальный максимум
$$
\begin{gather}
f : D \to R \\
\text{Если } \exists V^{\circ}_{x_0} , x_0 \in D, \forall x \in V^{\circ}_{x_0}, f(x) \leq f(x_0) , \text{то } x_0 \text{ наз точкой локального максимума}
\end{gather}
$$
### Локальный минимум 

### Экстремум
Точка локального экстремума называется точка его локального максимума или минимума 
![[Точки экстремума.png|551x551]]

- a - strict min
- e - strict max
- d - strict min
- c - unstrict max
- (c,b) - unstrict max/min
- b - unstrict min

## Теорема Ферма
В точке экстремума если функция дифф то в ней производная равна 0
$$
\begin{gather}
f : <a,b> \to R \\
x_0 - \text{экстремум }, f - \text{дифф в } x_0 \Rightarrow f(x_0)' = 0 \\\\
\frac{f(x_0 + \Delta x) - f(x_0) \leq 0}{\Delta x}  \Rightarrow \text{Зависит от знака } x_0 \\
\Delta x \to 0 \pm: f_{+}(x_0)' \leq 0 \\
\Delta x \to 0 \pm: f_{-}(x_0)' \geq 0
\\ \Rightarrow f(x_0)' \in R \text{ по усл} \\
\Rightarrow f'(x_0) = f'_{\pm}(x_0) = 0

\end{gather}
$$

## Теорема Ролля
$$
\begin{gather}
f \in C[a,b] , \text {Дифф в } (a,b), f(a) = f(b) \\
\Rightarrow \exists \xi \in (a,b) : f'(\xi) = 0 \\\\
\text{Если } f(x) = \text{const} /text{ на } [a,b], \text{ то } f'(x) = 0 \\
\text{по теореме Вейштрасса для непрерывных функц } f \text{ достигает наибольшее и наименьшее знач на } [a,b] \\
\Rightarrow \text{хотя бы одно из наибольшего и наименьшого значения является экстремумом в интервале, тк знаения ф-ии в токе a и b совпадают} \\
\Rightarrow \text{по т. Ферма в этой точке } f' = 0
\end{gather}
$$

## Теорема Лагранжа
$$
\begin{gather}
f \in C[a,b], \text{Дифф в } (a,b) \\
\Rightarrow \exists \xi \in (a,b): f(b) - f(a) = f'(\xi)(b-a) \\
\frac{f(b) - f(a)}{b - a} = f'(\xi) \\\\

F(x) = f(x) - y_{\text{хорда}} = f(x) - (f(a) + \frac{f(b)-f(a)}{b-a})(x-a)
\end{gather}
$$
![[Лагранж.png]]

## Теорема критерий монотонности ф-ии
$$
\begin{gather}
f \in C[a,b], \text{дифф в } (a,b) \\
\Rightarrow 1) f \uparrow(\downarrow) \text{ на } [a,b] \Leftrightarrow f(x) \geq_{(\leq)} 0, \forall x \in (a,b) \\ 
2) f \uparrow (\downarrow) \text{ на } [a,b] \Leftarrow f'(x) >_{(<)} 0, \forall x \in (a,b)\\\\

(\Rightarrow) f \uparrow, \frac{\Delta f}{\Delta x} \geq 0 \\
\Delta x \to 0: f'(x) \geq 0 \\\\
(\Leftarrow) x_1,x_2 \in [a,b] : x_1 < x_2 \Rightarrow \text{по т. Лагранжа } \exists \xi \in (x_1, x_2) :  f(x_2) - f(x_1) = f'(\xi) \cdot (x_2-x_1) \\
\end{gather}
$$
## Предел производной
$$
\begin{gather}
f \in C[a,b], \text{дифф в } (a,b) \\
\exists \lim_{x \to a+} f'(x) = A \in R' \Rightarrow \exists f'_+(a) = A
\end{gather}
$$
## Теорема Лопиталя
$$
\begin{gather}
f,g \text{ дифф в } (a,b) \\
\exists \lim_{x \to a+} \frac{f'(x)}{g'(x)} = A \\\\
1) \lim_{x\to a+} f(x) = \lim_{x \to a+}g(x) = 0  \Rightarrow \exists \lim_{x \to a+} \frac{f(x)}{g(x)} = A\\
2) \lim_{x \to a+} g(x) = \infty \Rightarrow \exists \lim_{x \to a+} \frac{f(x)}{g(x)} = A \\\\




\end{gather}
$$


## Теорема Дарбу

Если производная непрерывна на отрезке то по т. Бальцано-Коши она достигает свои значение на всем промежутке
### Формулировка
Достаточно чтобы ф-ия было дифф. на отрезке чтобы принимать все свои значения на $[a,b]$ 
$$
\begin {gather}
f - \text{дифф на } [a,b] \\
\Rightarrow \forall C \text{ между } f'(a) \text{ и } f'(b) \\
\exists c \in [a,b] : f(c) = C
\end {gather}
$$
### Док-во

$$
\begin{gather}
1) \quad ] f'(a) \cdot f'(b) < 0 \cap f'(a) < 0 < f'(b) \\
 \text{Покажем что } \exists c \in (a,b) : f'(c) = 0 \\
 f - \text{ дифф на } [a,b] \text{ значит непрерывна на } [a,b]
 \text{тогда по т.В f достигает min на } [a,b] \text{ в точке c} \in [a,b] \\
 \circ \ c \in (a,b) \Rightarrow \text{по. т. Ферма } f(c) = 0 \\
 \circ \ c = a \frac{(f(x)-f(a)) \geq 0 }{(x-a) > 0} \geq 0 \\
 \Rightarrow \lim_{x \to a+} \frac{f(x)-f(a)}{x-a} = f_+'(a) = f'(a), \text{но }f'(a) < 0 \text{ по условию} \\
 \circ \ c = b \text{ аналогично} \\
 \\

2) \quad \phi(x) = f(x) - C_x \\
 \phi'(x) = f'(x) - C \\
	 \Rightarrow \text{по 1 пункту } \exists c \in (a,b) : \phi'(x) = 0 \\
	 \Rightarrow f'(c) = C
\end{gather}
$$
### Замечание 1
$$
\begin{gather}
f(x) = |x| \quad [-1, 1] \\
\begin{cases}
1, 0 < x \leq 1 \\
-1, -1 \leq x < 0
\end{cases} \\
\text{тоесть } f \text{ дифф на всем отрезке } [a,b] 
\end{gather}
$$


