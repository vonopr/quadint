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

Отображение $(x,y)\overset{\hat{\eta}_{xy}}{=}(\hat{\eta}_x(\alpha,\beta), \hat{\eta}_y(\alpha,\beta))$ биективно отображает точки $P\{1234\}$ прямоугольника на единичный квадрат $\left[-\frac12, \frac12 \right].$

### Билинейная интерполяция в НЕ-прямоугольнике
Что делать, если значения заданы в узлах произвольного  выпуклого четырехугольника $1234$? В этом случае можно преобразовние $\hat{\eta}_{xy}$ координат вершин взаимно-однозначное отображение

 использовать четырехугольную интерполяцию [[1]](https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation), [[2]](http://reedbeta.com/blog/quadrilateral-interpolation-part-2/). Это обобщение билинейной интерполяции на случай произвольного выпуклого четырехугольника.

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
eyJoaXN0b3J5IjpbLTk3Njg0NDg2LDEzOTMyODM0NSwxMzcwMz
M4OTc0LDEyNTM5MjcxMTksMjEwNjgyODU4NSwxMjI3OTk3NDk3
LC0xNDE5MjA0NTI0LC0xMDU1NTQ5NDIzLC0xOTI4NzgyMDI4LD
cwOTQzNTE4Niw2MDQ0ODU0OTUsMTQ1OTAxNjIyMCwxOTEwNzEz
NTQ3LDI3ODkwMzc1MSwxNzg1ODM5NzQ5LC0xOTc3MTI1MzQ5LC
0xNDc0NjA0NjkwLDEyNTg4MTE1OTQsLTEyNjEwMjc4NTAsLTE1
Njc1NTE0NjFdfQ==
-->