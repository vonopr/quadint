# Четырехугольная интерполяция

## Введение

### Билинейная интерполяция в прямоугольнике
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

Отображение $(x,y)\overset{\hat{\eta}_{xy}}{=}(\hat{\eta}_x(\alpha,\beta), \hat{\eta}_y(\alpha,\beta))$ биективно отображает точки $R\{1234\}$ прямоугольника на единичный квадрат $\left[-\frac12, \frac12 \right]\times\left[-\frac12, \frac12 \right]$.

### Билинейная интерполяция в НЕ-прямоугольнике
Что делать, если значения заданы в узлах произвольного  выпуклого четырехугольника $1234$? В этом случае  [[1]](https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation), [[2]](http://reedbeta.com/blog/quadrilateral-interpolation-part-2/).преобразование $\hat{\eta}_{xy}$ координат точек четырехугольника взаимно-однозначное отображает точки $Q\{1234\}$ четырехугольника на единичный квадрат $\left[-\frac12, \frac12 \right]\times\left[-\frac12, \frac12 \right]$.

 использовать четырехугольную интерполяцию Это обобщение билинейной интерполяции на случай произвольного выпуклого четырехугольника.

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


## Ссылки
[1] https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1OTI2NjQ2MiwyMjE0Njc2MDQsMTM5Mz
I4MzQ1LDEzNzAzMzg5NzQsMTI1MzkyNzExOSwyMTA2ODI4NTg1
LDEyMjc5OTc0OTcsLTE0MTkyMDQ1MjQsLTEwNTU1NDk0MjMsLT
E5Mjg3ODIwMjgsNzA5NDM1MTg2LDYwNDQ4NTQ5NSwxNDU5MDE2
MjIwLDE5MTA3MTM1NDcsMjc4OTAzNzUxLDE3ODU4Mzk3NDksLT
E5NzcxMjUzNDksLTE0NzQ2MDQ2OTAsMTI1ODgxMTU5NCwtMTI2
MTAyNzg1MF19
-->