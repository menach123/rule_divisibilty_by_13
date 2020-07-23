
### A Rule of Divisibility by 13

When you divide the successive powers of ```10``` by ```13``` you get the following remainders of the integer divisions:
    
```1, 10, 9, 12, 3, 4```

Then the whoel pattern repeats.

Hence the following method: Multiply the right most digit of the number with the left most number in the sequence shown above, the second right most digit ot the second left most digit of the number in the sequence. The cycle goes on and you sum all these products. Repeat this process until the sequence of sums is stationary.


```python
n = 1234567 
```


```python
def check(n):
    string = str(n)
    return sum([(int(string[-(i+1)])* (10**i%13) )for i in range(len(string))])
```


```python
def thirt(n):
        x = n +1
        while x !=n:
            x = n
            n= check(n)
        return x
```


```python
no = 1234567
```


```python
string = str(no)
```


```python
sum([(int(string[-(i+1)])* (10**i%13) )for i in range(len(string))])
```




    178




```python
check(no)
```




    178




```python
thirt(no)
```




    87



```
thirt(8529) == 79
thirt(85299258) == 31
thirt(5634) == 57
thirt(1111111111) == 71
thirt(987654321) == 30
```


```python
print(thirt(8529) == 79)
print(thirt(85299258) == 31)
print(thirt(5634) == 57)
print(thirt(1111111111) == 71)
print(thirt(987654321) == 30)
```

    True
    True
    True
    True
    True
    


```python

```
