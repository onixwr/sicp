## define
```scheme
(define pi 3.14)

(define (square x) (* x x))
```

## cond
```scheme
(cond 
  (⟨p1 ⟩ ⟨e1 ⟩)
  (⟨p2 ⟩ ⟨e2 ⟩)
  : : :
  (⟨pn ⟩ ⟨en ⟩)
  (else <ee>)
) 
```
述語(predicate)と結果式(consequent expression) ⟨e⟩の節(clause) で構成。
節とは括弧でくくった式のペアのこと。
最初から評価していき、#tとなった述語に対応する結果式のみ評価します。

結果式は式の列で記述することもできます。

## if
(if ⟨predicate⟩ ⟨consequent⟩ ⟨alternative⟩)

predicateが#tのときconsequentを評価し、#fのときaltenativeを評価する。

# and / or
```scheme
(and ⟨e1⟩ ... ⟨en⟩)
```
e1から順番に評価していき#fとなった時点でその後の式は評価されない。最後の式の評価値を返えす。

```scheme
(or ⟨e1⟩ ... ⟨en⟩)
```
e1から順番に評価していき真(#fではない)となった時点でその後の式は評価されない。最後の式の評価値を返えす。


## lambda
```scheme
(lambda (⟨formal-parameters⟩) ⟨body⟩)
```

```scheme
(lambda (x) (* x x))
```

## let
```scheme
(let 
  (
    (⟨var1⟩ ⟨exp1⟩)
    (⟨var2⟩ ⟨exp2⟩)
    ...
    (⟨varn⟩ ⟨expn⟩)
  )
  ⟨body⟩
)
```
以下と等価です。

```scheme
((lambda (⟨var1⟩ : : : ⟨varn⟩)
  ⟨body⟩)
  (exp1⟩
  ...
  ⟨expn⟩
)

