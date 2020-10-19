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
Что делать, если значения заданы в узлах произвольного четырехугольника? В этом случае можно использовать четырехугольную интерполяцию [[1]](https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation), [[2]](http://reedbeta.com/blog/quadrilateral-interpolation-part-2/). Это обобщение билинейной интерполяции на случай произвольного плого четырехугольника.

## Билинейн  а в 
Даны  вершины произвольного четырехугольника $1243$  с координатами (x_n,y_n) и значениями $f_n$. 

```ascii
            X                                
    1 
     X              4
                X
    X
   
```

Рассм$\hat{\varphi} (a, b)$ , 
$$ 
\hat{\varphi}(a,b) =
   \varphi_1 \cdot \left(\frac12-a\right)  \left( \frac12-b\right) +
   \varphi_2 \cdot \left(\frac12+a\right)  \left(\frac12-\right)  + \\
   \varphi_3  \cdot \left(\frac12-a\right)  \left(\frac12+b\right)  + 
   \varphi_4 \cdot  \left(\frac12+a\right) \left(\frac12+b\right) 
$$
где $\varphi \equiv$  $x,y$ или $f$.

Выберем параметры $a=\alpha(x,y), b=\beta(x,y)$ преобразования $\varphi$ так, что
$$
\hat{x}(a,b) = x,\\
\hat{y}(\alpha, \beta) = y; \,
$$
или
$$ 
ifootnotex = \small{
   x_1 \cdot \left(\frac12-a \right)  \left( \frac12right) +
   _2\cdot \left(\frac12+a \right)   \left(\frac12-\beta \right)  + 
  x_3  \cdot \left(\frac12-\alpha \right)  \left(\frac12+\beta \right)  + 
   _4 \cdot  \left(\frac12+\alpha \right) \left(\frac12+b \right) }, .
$$

Если применить преобразовани $\varphi$ к координатам $(x,y)$ точек четырехугольника, то преобразует его в квадрат$[-\frac12;;\frac12]$.

```ascii

    1       2
     X - - X
     |     |
     |     |
     X - - X
    3       4
   ```

$$ 
\hat{\varphi}(phi_1 \cdot \lefta \right]  \ft[ \frac12-\beta \right] +
   \varphi_2 \cdot \lefta \right]  \ft[\frac12-\beta \right] + \\
   \varphi_3  \cdot \lefta \right] \left[\frac12+\beta \right] + 
   \varphi_4 \cdot  \lefta \right]  \left[\f\right,
$$

## Ссылки
[1] https://math.stackexchange.com/questions/2007116/quadrilateral-interpolation
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDk3MzIwMDMsLTE5NzcxMjUzNDksLT
E0NzQ2MDQ2OTAsMTI1ODgxMTU5NCwtMTI2MTAyNzg1MCwtMTU2
NzU1MTQ2MSwzMTc4NjQ0NTUsNDcyNjg1OTk4LDEyNjk0NDk0Mz
ddfQ==
-->