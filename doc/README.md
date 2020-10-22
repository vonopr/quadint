# Четырехугольная интерполяция

## Введение

### Билинейная интерполяция в прямоугольнике
Отобразить значения $f_{1,2,3,4}$, заданные  в вершинах прямоугольника, на внутренность этого прямоугольника $1234$ можно с помощью преобразования билинейного преобразования $\hat{\eta}_{\varphi}$, примененного к координатам вершин и значениям $f$  в вершинах:
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
\hat{f}(x,y) = 
   f_1 \cdot \left(\frac12-\alpha \right)  \left( \frac12-\beta \right) +
   f_2\cdot \left(\frac12+\alpha \right)   \left(\frac12-\beta \right)  +\\
   f_3  \cdot \left(\frac12+\alpha \right)  \left(\frac12+\beta \right)  + 
   f_4 \cdot  \left(\frac12-\alpha \right) \left(\frac12+\beta \right) , \\
$$
где $x_{-}\equiv x_1=x_4$, $x_{+} \equiv x_2=x_3$,  $y_{-} \equiv y_1=y_2$,  $y_{+} \equiv y_3=y_4$ ,  $(x_n,y_n)$ - координаты вершин.

### Билинейная интерполяция в НЕ-прямоугольнике
Что делать, если значения заданы в узлах произвольного  выпуклого четырехугольника? В этом случае можно построить взаимно-однозначное отображение

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
eyJoaXN0b3J5IjpbLTEyODA3Njk4ODQsMTM3MDMzODk3NCwxMj
UzOTI3MTE5LDIxMDY4Mjg1ODUsMTIyNzk5NzQ5NywtMTQxOTIw
NDUyNCwtMTA1NTU0OTQyMywtMTkyODc4MjAyOCw3MDk0MzUxOD
YsNjA0NDg1NDk1LDE0NTkwMTYyMjAsMTkxMDcxMzU0NywyNzg5
MDM3NTEsMTc4NTgzOTc0OSwtMTk3NzEyNTM0OSwtMTQ3NDYwND
Y5MCwxMjU4ODExNTk0LC0xMjYxMDI3ODUwLC0xNTY3NTUxNDYx
LDMxNzg2NDQ1NV19
-->