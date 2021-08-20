# Scala basics



### Week 2: Higher order functions

Data classes
* self reference is implicit. "this" 라고 씀
* private 함수도 쓸 수 있다. `private def` 
* `require` 사용해서 python assert 같은걸 구현할 수 있음. 
```
class Rational(x: Int, y: Int):
    require (y>0, "denominator must be positive") 
    val numer = x
    val denom = y 
    def add(r: Rational):
        Rational(numer * r.denom + r.numer, denom * r.denom)
```
* assertion 도 가능
```
val x = sqrt(x)
assert(x>=0)
```
* end marker at the end of class, def, if 
```angular2html
class Rational(...):
...
end Rational
```
* extension methods 
class안에 모든 function을 적으면 너무 코드 양이 많아지거나 modular하지 않게 되니까 extension method를 쓰면 다른 파일에도 같은 class에 대한 코드를 쓸 수 있다는 장점이 있다. 
```angular2html
extension(r: Rational)
    def min(s: Rational): Bool = if s.less(r) then s else r
```

* operators 
    * infix notation 