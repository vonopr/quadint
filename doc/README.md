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

С помощью билинейного преобразования $\hat{\varphi} (a, b)$ отобразим четырехугольник в прямоугольник $[-\frac12;\frac12]^2$.
$$ 
\small
\hat{\varphi} (a, b) =
  \varphi_1 \cdot \left(\frac12-a \right)  \left( \frac12-b \right) +
  \varphi _2\cdot \left(\frac12+a \right)  \left(\frac12-b \right)  +\\
  \varphi_3  \cdot \left(\frac12-a \right)  \left(\frac12+b \right)  + 
  \varphi_4 \cdot  \left(\frac12+a \right) \left(\frac12+b \right)
$$
где $\varphi \equiv$  $x,y$ или $f$.

Выберем параметры $a=\alpha(x,y), b=\beta(x,y)$ преобразования $\varphi$ так, что
$$
\hat{x}(a,b) = x,\\
\hat{y}(\alpha, \beta) = y; \,
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

Если применить преобразование $\varphi$ к координатам $(x,y)$ точек четырехугольника, то преобразует его в квадрат$[-\frac12;;\frac12]$.

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
eyJoaXN0b3J5IjpbNTk5NjEwNDUwLDE0NTkwMTYyMjAsMTkxMD
cxMzU0NywyNzg5MDM3NTEsMTc4NTgzOTc0OSwtMTk3NzEyNTM0
OSwtMTQ3NDYwNDY5MCwxMjU4ODExNTk0LC0xMjYxMDI3ODUwLC
0xNTY3NTUxNDYxLDMxNzg2NDQ1NSw0NzI2ODU5OTgsMTI2OTQ0
OTQzN119
-->