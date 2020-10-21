# Четырехугольная интерполяция

## Введение

### Билинейная интерполяция
Билинейная интерполяция позволяет отобразить значения $f_{1,2,3,4}$, заданные  в вершинах прямоугольника, на внутренность этого прямоугольника $1243$ с помощью преобразования
$$
\hat{f}(x,y) = f_1 \frac{ (x_{+}-x)(y_{+}-y)}{(x_{+}-x_{-})(y_{+}-y_{-})} +
f_2 \frac{(x-x_{-})(y_{+}-y)}{(x_{+}-x_{-})(y_{+}-y_{-})} +\\
+f_3 \frac{(x_{+}-x)(y-y_{-})}{(x_{+}-x_{-})(y_{+}-y_{-})} +
f_4 \frac{(x-x_{-})(y-y_{-})}{(x_{+}-x_{-})(y_{+}-y_{-})},
$$
где $x_{-}\equiv x_1=x_3$, $x_{+} \equiv x_2=x_4$,  $y_{-} \equiv y_1=y_2$,  $y_{+} \equiv y_3=y_4$ ,  $(x_n,y_n)$ - координаты вершин.

### Что делать с НЕ-прямоугольником?
Что делать, если значения заданы в узлах произвольного четырехугольника? В этом случае можно использовать четырехугольную интерполяцию [[1]](https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation), [[2]](http://reedbeta.com/blog/quadrilateral-interpolation-part-2/). Это обобщение билинейной интерполяции на случай произвольного выпуклого четырехугольника.

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

С помощью билинейного преобразования $\hat{\eta}_{xy}$ отобразим четырехугольник $1243$ в квадрат $[-\frac12;\frac12]^2$. Пусть
$$
\hat{\eta}_{xy}(x,y)\equiv(\hat{\eta}_x(x),\hat{\eta}_y(y))
$$

$$
x = \hat{\eta}_x(\alpha, \beta) ,\\
y = \hat{\eta}_y(\alpha, \beta) ; \,
$$


$$ 
\small
\hat{\varphi} (a, b) =
  \varphi_1 \cdot \left(\frac12-a \right)  \left( \frac12-b \right) +
  \varphi _2\cdot \left(\frac12+a \right)  \left(\frac12-b \right)  +\\
  \varphi_3  \cdot \left(\frac12-a \right)  \left(\frac12+b \right)  + 
  \varphi_4 \cdot  \left(\frac12+a \right) \left(\frac12+b \right)
$$
где $\varphi \equiv$  $x,y$ или $f$.

Для этого выберем параметры $a=\alpha(x,y), b=\beta(x,y)$ преобразования $\hat{\varphi}$ так, что
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
eyJoaXN0b3J5IjpbODU1NDk1ODI3LC0xMDU1NTQ5NDIzLC0xOT
I4NzgyMDI4LDcwOTQzNTE4Niw2MDQ0ODU0OTUsMTQ1OTAxNjIy
MCwxOTEwNzEzNTQ3LDI3ODkwMzc1MSwxNzg1ODM5NzQ5LC0xOT
c3MTI1MzQ5LC0xNDc0NjA0NjkwLDEyNTg4MTE1OTQsLTEyNjEw
Mjc4NTAsLTE1Njc1NTE0NjEsMzE3ODY0NDU1LDQ3MjY4NTk5OC
wxMjY5NDQ5NDM3XX0=
-->