# Четырехугольная интерполяция

## Введение

### Билинейная интерполяция в прямоугольнике
Отобразить значения $f_{1,2,3,4}$, заданные  в вершинах прямоугольника, на внутренность этого прямоугольника $1234$ можно с помощью преобразования билинейного преобразования
$$
\alpha = \frac{x-\frac{x_{+}+x_{-}}{2}}{x_{+}-x_{-}},\\
\beta= \frac{y-\frac{y_{+}+y_{-}}{2}}{y_{+}-y_{-}},\\
\hat{f}(x,y) = 
   f_1 \cdot \left(\frac12-\alpha \right)  \left( \frac12-\beta \right) +
   f_2\cdot \left(\frac12+\alpha \right)   \left(\frac12-\beta \right)  +\\
   f_3  \cdot \left(\frac12+\alpha \right)  \left(\frac12+\beta \right)  + 
   f_4 \cdot  \left(\frac12-\alpha \right) \left(\frac12+\beta \right) , \\
$$
где $x_{-}\equiv x_1=x_3$, $x_{+} \equiv x_2=x_4$,  $y_{-} \equiv y_1=y_2$,  $y_{+} \equiv y_3=y_4$ ,  $(x_n,y_n)$ - координаты вершин.

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

Билинейное преобразование $(\hat{\eta}_{xy})^{-1}$ отображает четырехугольник $1234$ в квадрат $[-\frac12;\frac12]^2$. Пусть
$$
\hat{\eta}_{xy}(\alpha, \beta)\equiv(\hat{\eta}_x(\alpha, \beta),\hat{\eta}_y(\alpha, \beta)),\\
\hat{\eta}_{\varphi} (\alpha, \beta) \equiv
  \varphi_1 \cdot (1/2-\alpha )  (1/2-\beta) +  \varphi _2\cdot (1/2+\alpha) (1/2-\beta)  +\\
  \varphi_3  \cdot (1/2-\alpha) (1/2+\beta)  + \varphi_4 \cdot  (1/2+\alpha)(1/2+\beta),
$$
где $\varphi \equiv$  $x,y$ или $f$. Тогда
$$
x = \hat{\eta}_x(\alpha, \beta) ,\\
y = \hat{\eta}_y(\alpha, \beta) ; \,
$$
или
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

Можно показать, что якобиан преобразования $\eta_{xy}$ отличен от нуля в любой точке выпуклого четырехугольника,   $(\hat{\eta}_{xy})^{-1}$ задает взаимно-однозначное соответствие между точками  $1243$ и квадратом $[-\frac12;\frac12]^2$, при этом стороны четырехугольника переходят в стороны квадрата.


Границы


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
eyJoaXN0b3J5IjpbODk2NjYwNTg0LDEyNTM5MjcxMTksMjEwNj
gyODU4NSwxMjI3OTk3NDk3LC0xNDE5MjA0NTI0LC0xMDU1NTQ5
NDIzLC0xOTI4NzgyMDI4LDcwOTQzNTE4Niw2MDQ0ODU0OTUsMT
Q1OTAxNjIyMCwxOTEwNzEzNTQ3LDI3ODkwMzc1MSwxNzg1ODM5
NzQ5LC0xOTc3MTI1MzQ5LC0xNDc0NjA0NjkwLDEyNTg4MTE1OT
QsLTEyNjEwMjc4NTAsLTE1Njc1NTE0NjEsMzE3ODY0NDU1LDQ3
MjY4NTk5OF19
-->