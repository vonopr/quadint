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

С помощью билинейного преобразования $(\hat{\eta}_{xy})^{-1}$ отобразим четырехугольник $1243$ в квадрат $[-\frac12;\frac12]^2$. Пусть
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

Можно показать, что преобразование $(\hat{\eta}_{xy})^{-1}$ задает взаимно-однозначное соответствие между точками четырехугольника $1243$ и квадратом $[-\frac12;\frac12]^2$ 


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
eyJoaXN0b3J5IjpbLTIxMDIyMzc3NDQsLTEwNTU1NDk0MjMsLT
E5Mjg3ODIwMjgsNzA5NDM1MTg2LDYwNDQ4NTQ5NSwxNDU5MDE2
MjIwLDE5MTA3MTM1NDcsMjc4OTAzNzUxLDE3ODU4Mzk3NDksLT
E5NzcxMjUzNDksLTE0NzQ2MDQ2OTAsMTI1ODgxMTU5NCwtMTI2
MTAyNzg1MCwtMTU2NzU1MTQ2MSwzMTc4NjQ0NTUsNDcyNjg1OT
k4LDEyNjk0NDk0MzddfQ==
-->