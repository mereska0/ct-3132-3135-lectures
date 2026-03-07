---
sticker: emoji//1f51e
banner_y: "67"
---
## Производные и дифф-лы высших порядков 
### Определение 
$$
\begin{gather}
 f : D \to R \\
 \text{если } f \text{ дифф на } D_1 \subset D \Rightarrow f : D_1 \to R \\
 f'' := (f')' , \dots, f^{(n)} := (f^{(n-1)})'  \\\\
 d^2f := d(df), \dots, d^nf = d(d^{n-1}f)
 \end{gather}
$$
### Линейность 
#### Формулировка
$$
\forall \alpha, \beta \in R \quad (\alpha f + \beta g)^{(n)} = \alpha f^{(n)} + \beta g^{(n)} 
$$
#### Док-во
$$
\begin{gather}
n = 1 : (\alpha f + \beta g)' = \alpha f' + \beta g' \\
n = 2 : ((\alpha f + \beta g)')' = \alpha f'' + \beta g'' \\
\dots \text{по мат.индукции}
\end{gather}
$$
### Правило Лейбница
#### Формулировка
$$
f,g \text{ дифф n раз } \Rightarrow (f \cdot g)^{(n)} = \sum^n_{k=0} C_n^k \cdot f^{(k)} \cdot g^{(n-k)}
$$ 
#### Док-во  
$$
\begin{gather}
n = 1 : (f \cdot g)' = f'g + fg', \ \text{По сумме получаетс также} \\
n : (f \cdot g)^{(n)} \\
\text{work in progress...}
\end{gather}
$$
### Многочлен Тейлора
Задача: Найти многочлен $Pn(x,x_0)$ 
$$
\begin{gather}
\begin{cases}
P_n(x_0,x_0) = f(x_0) \\
P_n'(x_0,x_0) = f'(x_0) \\
\dots \\
P^{(n)}_n(x_0,x_0) = f^{(n)}(x_0)\\\\\
\end{cases} \\
] \ P_n(x_0,x_0) = a_0 + a_1(x - x_0) + a_2(x - x_0)^2 + a_3(x - x_0)^3, \dots, a_n(x-x_0)^n \\
P'_n(x_0,x_0) = a_1 + 2a_2(x-x_0) + 3a_3(x-x_0)^2 + ,\dots, n a_n(x-x_0)^{n-2} \\
P''_n(x,x_0) = 2a_2 + 3!(x-x_0) + \dots + n(n-1)a_n(x-x_0)^{n-1} \\

\end{gather}
$$
#### Формула в виде суммы 
$$
\sum_{k = 0}^n \frac{f^{(n)}(x_0)}{k!}(x - x_0)^k
$$
