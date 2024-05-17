# EX.-NO-2-C-IMPLEMENTATION-OF-DIFFIE-HELLMAN-KEY-EXCHANGE-ALGORITHM

## AIM:
To implement the Diffie-Hellman Key Exchange algorithm using C language.

## ALGORITHM:
  
  STEP-1: Both Alice and Bob shares the same public keys g and p.
  
  STEP-2: Alice selects a random public key a.
  
  STEP-3: Alice computes his secret key A as g a mod p.
  
  STEP-4: Then Alice sends A to Bob.
  
  STEP-5: Similarly Bob also selects a public key b and computes his secret key as B and sends the same back to Alice.
  
  STEP-6: Now both of them compute their common secret key as the other one’s secret key power of a mod p.
  
## PROGRAM:
```
#include <math.h>
#include <stdio.h>
// Power function to return value of a ^ b mod P
long long int power(long long int a, long long int b,
long long int P)
{
if (b == 1)
return a;
else
return (((long long int)pow(a, b)) % P);
}
// Driver program
int main()
{
long long int P, G, x, a, y, b, ka, kb;
// Both the persons will be agreed upon the
// public keys G and P
printf("Enter the value of P:");
scanf("%lld",&P); // A prime number P is taken
printf("The value of P : %lld\n", P);
printf("Enter the value of G:");
scanf("%lld",&G); // A primitive root for P, G is taken
printf("The value of G : %lld\n\n", G);
// Alice will choose the private key a
a = 4; // a is the chosen private key
printf("The private key a for Alice : %lld\n", a);
x = power(G, a, P); // gets the generated key
// Bob will choose the private key b
b = 3; // b is the chosen private key
printf("The private key b for Bob : %lld\n\n", b);
y = power(G, b, P); // gets the generated key
// Generating the secret key after the exchange
// of keys
ka = power(y, a, P); // Secret key for Alice
kb = power(x, b, P); // Secret key for Bob
printf("Secret key for the Alice is : %lld\n", ka);
printf("Secret Key for the Bob is : %lld\n", kb);
return 0;
}
```

## OUTPUT:
![Screenshot 2024-05-17 110342](https://github.com/nandhu6523/EX.-NO-2-C-IMPLEMENTATION-OF-DIFFIE-HELLMAN-KEY-EXCHANGE-ALGORITHM/assets/123856724/9c02df99-8a07-4dad-8da3-10949593508c)


## RESULT:
  Thus the Diffie-Hellman key exchange algorithm had been successfully implemented using C
