# Четырехугольная интерполяция

## Билинейная интерполяция в прямоугольнике
Отобразим значения $f_{1,2,3,4}$, заданные  в вершинах прямоугольника, на внутренность этого прямоугольника $1234$ с помощью преобразования билинейного преобразования $\hat{\eta}_{\varphi}$, примененного к координатам вершин $(x_n,y_n)$ и значениям $f_n$  в вершинах:
$$
\hat{\eta}_{\varphi} (\alpha, \beta) \equiv
  \varphi_1 \cdot (1/2-\alpha )  (1/2-\beta) +  \varphi _2\cdot (1/2+\alpha) (1/2-\beta)  +\\
  \varphi_3  \cdot (1/2+\alpha) (1/2+\beta)  + \varphi_4 \cdot  (1/2-\alpha)(1/2+\beta);\\
x = \hat{\eta}_x(\alpha, \beta) ,\\
y = \hat{\eta}_y(\alpha, \beta) , \\
\hat{f}(\alpha,\beta) =\hat{\eta}_{f}(\alpha,\beta).
$$

Выразим $\alpha$ и $\beta$ через $x$ и $y$ и распишем выражения для $\hat{f}(\alpha,\beta)$:
$$
\alpha = \frac{x-\frac{x_{+}+x_{-}}{2}}{x_{+}-x_{-}},\\
\beta= \frac{y-\frac{y_{+}+y_{-}}{2}}{y_{+}-y_{-}},\\
\hat{f}(\alpha,\beta) = 
   f_1 \cdot \left(\frac12-\alpha \right)  \left( \frac12-\beta \right) +
   f_2\cdot \left(\frac12+\alpha \right)   \left(\frac12-\beta \right)  +\\
   f_3  \cdot \left(\frac12+\alpha \right)  \left(\frac12+\beta \right)  + 
   f_4 \cdot  \left(\frac12-\alpha \right) \left(\frac12+\beta \right) , \\
$$
где $x_{-}\equiv x_1= x_4$, $x_{+} \equiv x_2=x_3$,  $y_{-} \equiv y_1=y_2$,  $y_{+} \equiv y_3=y_4$ ,  $(x_n,y_n)$ - координаты вершин.

Отображение $(x,y)\overset{\hat{\eta}_{xy}}{=}(\hat{\eta}_x(\alpha,\beta), \hat{\eta}_y(\alpha,\beta))$ биективно отображает точки прямоугольника 1234 на единичный квадрат $\left[-\frac12, \frac12 \right]\times\left[-\frac12, \frac12 \right]$.

## Билинейная интерполяция в выпуклом четыр
Что делать, если значения заданы в узлах произвольного  выпуклого четырехугольника $1234$? В этом случае [[1]](#1),[[2]](#2) преобразование $\hat{\eta}_{xy}$ координат точек четырехугольника так же взаимно-однозначно отображает его на единичный квадрат $\left[-\frac12, \frac12 \right]\times\left[-\frac12, \frac12 \right]$.

Оказалось [[2]](#2) , что для обратного преобразования $(\alpha,\beta)\overset{\hat{\eta}^{-1}_{xy}}{= }(\alpha(x,y), \beta(x,y))$ существует явное выражение. Оно было опубликовано в 2015 году. Автор получил его используя обобщенные барицентрические координаты для выпуклых многоугольников.


## Отображение четырехугольника в прямоугольник
Даны  вершины выпуклого четырехугольника $1243$  с координатами $(x_n,y_n)$ и значениями $f_n$. 

```ascii
           2
            X                                
    1 
     X              4
                X
    X
   
```



Можно показать, что якобиан преобразования $\eta_{xy}$ отличен от нуля в любой точке выпуклого четырехугольника,   $(\hat{\eta}_{xy})^{-1}$ задает взаимно-однозначное соответствие между точками  $1243$ и квадратом $[-\frac12;\frac12]^2$, при этом стороны четырехугольника переходят в стороны квадрата.


Границы

## Мусор
$$ 
\small
x = 
   x_1 \cdot \left(\frac12-\alpha \right)  \left( \frac12-\beta \right) +
   x_2\cdot \left(\frac12+\alpha \right)   \left(\frac12-\beta \right)  +\\
   x_3  \cdot \left(\frac12-\alpha \right)  \left(\frac12+\beta \right)  + 
   x_4 \cdot  \left(\frac12+\alpha \right) \left(\frac12+\beta \right) , \\
 y = 
   y_1 \cdot \left(\frac12-\alpha \right)  \left( \frac12-\beta \right) +
   y_2\cdot \left(\frac12+\alpha \right)   \left(\frac12-\beta \right)  +\\ 
   y_3  \cdot \left(\frac12-\alpha \right)  \left(\frac12+\beta \right)  + 
   y_4 \cdot  \left(\frac12+\alpha \right) \left(\frac12+\beta \right).
$$


```ascii

    1       2
     X - - X
     |     |
     |     |
     X - - X
    3       4
   ```


## Литература
<a id="1">[1]</a>Floater M. S. The inverse of a rational bilinear mapping //Computer Aided Geometric Design. – 2015. – Т. 33. – С. 46-50.
<a id="2">[2]</a> Sederberg T. W., Zheng J. Birational quadrilateral maps //Computer Aided Geometric Design. – 2015. – Т. 32. – С. 1-4.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxMzUzMzEyNSwtMTgxNDA0MjYyNCwyMj
E0Njc2MDQsMTM5MzI4MzQ1LDEzNzAzMzg5NzQsMTI1MzkyNzEx
OSwyMTA2ODI4NTg1LDEyMjc5OTc0OTcsLTE0MTkyMDQ1MjQsLT
EwNTU1NDk0MjMsLTE5Mjg3ODIwMjgsNzA5NDM1MTg2LDYwNDQ4
NTQ5NSwxNDU5MDE2MjIwLDE5MTA3MTM1NDcsMjc4OTAzNzUxLD
E3ODU4Mzk3NDksLTE5NzcxMjUzNDksLTE0NzQ2MDQ2OTAsMTI1
ODgxMTU5NF19
-->