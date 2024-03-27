# Mathematics

#### Some precaution for reading these codes
```
typedef long long int lli;
```

## Modulo
What is modulo ?
- with this we try to avoid overflow problems
- obviously other mathematical usage are there

```
	👉 27 mod 12 = 3
	👉 27 - floor(27/12)*12 = 3
	
	👉 a mod m = a - floor(a/m)*m 		
```

For both positive and negative number 
```
lli mod(lli a, lli m){
    a %= m;
    if(a<0) a+= m;
    return a;
}
```
### Modulo Addition / Substraction

```
👉 Addition : (a+b) % m = ((a%m) + (b%m)) % m
👉 Substraction : (a-b) % m = ((a%m) - (b%m)) % m
```

functions can be used to add and substract
```
lli add(lli a, lli b, lli m) {
    a %= m;   // ensuring a is less than m 
    a += (b%m); // ensuring b is less than m and the sum is in range of 1 to 2m-2
    return a >=m ? a - m : a; // ensuring the sum comes in range of 1 to m-1
}

// similarly
lli sub(lli a, lli b, lli m) {
    a %= m;
    a -= (b%m);
    return a < 0  ? a + m : a;
}

```