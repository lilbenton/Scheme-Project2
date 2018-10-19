# Scheme-Project2
This is Scheme Project 2 
* PART 1: Ball-val
* PART 2: Count-balls
* PART 3: Color-counts
* PART 4: Bucket-val
* PART 5: Judge 
### Quick Start 
**Make sure you have an apporpriate IDE that implements Scheme. For example, Dr. Racket
````bash 
# Learn Scheme using provided links
# Get proper materials through canvas 
# Make sure to upload the Scheme language using 
  "#lang racket
   (require (planet dyoo/simply-scheme:1:2/simply-scheme))"
````
# Table of Contents 

* [Ball-val](#Ball-val)
* [Count-balls](#Count-balls)
* [Color-counts](#Color-counts)
* [Bucket-val](#Bucket-val)
* [Judge](#Judge)

#### Ball-val

Procedure that takes bucket as the argument and returns the total number of points the bucket is worth. 
```
(define (ball-val ball)
   (let ([W 1]
         [R 10]
         [G 15]
         [B 20])
     (if (equal? ball 'W)
         (display 1))
     (if (equal? ball 'R)
         (display 10))
     (if (equal? ball 'G)
         (display 15))
     (if (equal? ball 'B)
         (display 20))))
```
___

#### Count-balls 
Procedure that takes a color and a bucket as arguments and returns the number of balls in the bucket with the given color. 
Uses the lambda function on an argument c to compare the arguments ball-color and counts them.
```
(define (count-balls ball-color bucket)
        (count (keep (lambda (c) (equal? ball-color c)) bucket)))

```
___

#### Color-counts
Procedure that takes a bucket as its argument adn returns a sentence containing the number of reds, greens, blues, and whites in the bucket. 
```
(define (color-counts bucket)
  (let ([R (count-balls 'R bucket)]
     [W (count-balls 'W bucket)]
     [G (count-balls 'G bucket)]
     [B (count-balls 'B bucket)])
       (display (list R G W B))))
```
___

#### Bucket-val
Procedure that takes a bucket as its argument and returns the total number of points the bucket is worth. 
```
(define (bucket-val bucket)
   (let ([R (count-balls 'R bucket)]
      [W (count-balls 'W bucket)]
      [G (count-balls 'G bucket)]
      [B (count-balls 'B bucket)])
       (let ([val (+ (+ (* R 10) (* W 1)) (+ (* G 15) (* B 20)))])
         (display val))))
```
___

#### Judge 
Procedure that takes BUCKET_1 and BUCKET_2 as arguments and returns who won the game player
```
(define (judge BUCKET_1 BUCKET_2)
    (let ([R1 (count-balls 'R BUCKET_1)]
        [W1 (count-balls 'W BUCKET_1)]
        [G1 (count-balls 'G BUCKET_1)]
        [B1 (count-balls 'B BUCKET_1)]
        [R2 (count-balls 'R BUCKET_2)]
        [W2 (count-balls 'W BUCKET_2)]
        [G2 (count-balls 'G BUCKET_2)]
        [B2 (count-balls 'B BUCKET_2)])
   (let ([sum1 (+ (+ (* R1 10) (* W1 1)) (+ (* G1 15) (* B1 20)))]
        [sum2 (+ (+ (* R2 10) (* W2 1)) (+ (* G2 15) (* B2 20)))])
   (if (equal? sum1 sum2)
       (display "It\'s a Tie .. !"))
   (if (> sum1 sum2)
                (display "Bucket 1, Won .. !"))
   (if (< sum1 sum2)
                (display "Bucket 2, Won .. !")))))

```
___

#### License 
  [Auburn University](/LICENSE)
  
___

## Author
  [Amy Benton](/LICENSE)
