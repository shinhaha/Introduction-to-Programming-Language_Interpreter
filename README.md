# Cute_Interpreter
```
Racket과 유사하게 구현한 Interpreter입니다.
exe 파일을 실행한 뒤 아래의 Test Case를 입력합니다.
```
# Project TEST Case
```
1. (define a 1)
a ;; 1출력
2. (define b '(1 2 3))
b ;; '(1 2 3)
3. (define c (- 5 2))
c;; 3
4. (define d '(+ 2 3))
d;;'(+ 2 3)
5. (define test b)
test;; '(1 2 3)
6. (+ a 3) ;; 4
7. (define a 2) ;; 앞에 a가 정의된 후에 새로 정의
(* a 4) ;; 8
8. ((lambda (x) (* x -2)) 3) ;; -6
9. ((lambda (x) (/ x 2)) a) ;; 1
10. ((lambda (x y) (* x y)) 3 5) ;; 15
11. ((lambda (x y) (* x y)) a 5) ;; 10
12. (define plus1 (lambda (x) (+ x 1))) ;; 전역 함수 구현
(plus1 3) ;; 4 
13. (define mul1 (lambda (x) (* x a))) ;; 전역 함수 구현, 전역 변수 포함
(mul1 a) ;; 4 
14. (define plus2
(lambda (x) (+ (plus1 x) 1))) ;;함수 내에서 전역 함수 호출 가능
(plus2 4) ;; 6 
15. (define plus3
(lambda (x) (+ (plus1 x) a))) ;;함수 내에서 전역 함수 호출 가능, 전역 변수 포함
(plus3 a) ;; 5 
16. (define mul2
(lambda (x) (* (plus1 x) -2)))
(mul2 7) ;; -16 
17. (define lastitem
(lambda (ls)
(cond ((null? (cdr ls)) (car ls))
(#T (lastitem (cdr ls)))))) ;;Recursion 구현 
18. (define square (lambda (x) (* x x)))
(define yourfunc (lambda (x func) (func x))
(yourfunc 3 square) ;;함수에서 함수를 인자로 사용가능 
19. (define square (lambda (x) (* x x)))
(define multwo (lambda (x) (* 2 x)))
(define newfun (lambda (fun1 fun2 x) (fun2 (fun1 x))))
(newfun square multwo 10) ;; 
20. (define cube
(lambda (n) (define sqrt (lambda (n) (* n n)))
(* (sqrt n) n))) ;;Nested 함수 구현 
(sqrt 4) ;; 불리면 안됨
```
