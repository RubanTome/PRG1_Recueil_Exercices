# Que produit ce code

Déterminer "à la main" ce que poduit ce code.

~~~cpp
#include <cmath>
#include <cstdlib>
#include <iostream>

using namespace std;

double k(double x) { return 2 * (x + 1);        }
double h(double x) { return x * x + k(x) - 1;   }
double g(double x) { return 4 * h(x);           }
double f(double x) { return g(x) + sqrt(h(x));  }

int main() {
    double x1 = f(2),
           x2 = g(h(2)),
           x3 = k(g(2) + h(2)),
           x4 = f(0) + f(1) + f(2),
           x5 = f(-1) + g(-1) + h(-1) + k(-1);
       
   cout << "x1 = " << x1 << endl;
   cout << "x2 = " << x2 << endl;
   cout << "x3 = " << x3 << endl;
   cout << "x4 = " << x4 << endl;
   cout << "x5 = " << x5 << endl;

   return EXIT_SUCCESS;
}
~~~
Affichage : <br>
x1 = f(2) = g(2) + sqrt(h(2)) = 4 * h(2) + sqrt(2 * 2 + k(2) -1) = 4 * ( 2 * 2 + k(2) - 1) + sqrt(2 * 2 + k(2) -1) = 4 * (2 * 2 + 2 * (2+1) - 1) + sqrt(2 * 2 + 2*(2+1)-1) = 4 * (4 + 6 - 1) + sqrt (4 + 6 -1) = 4 * 9 + sqrt(9) = 36 + 3 = 39 <br>
x2 = g(h(2)) = g(2 * 2 + k(2)-1) = g(2 * 2 + 2*(2+1)- 1) = g(4 + 6 -1 ) = g(9) = 4 * h(9) = 4 * (9 * 9 + k(9) -1) = 4 * ( 81 + 2*(9+1) - 1) = 4 * (81 + 20 -1) = 4 * 100 = 400 <br>
x3 = k(g(2) + h(2)) = k(4 * h(2) + 2 * 2 + k(2)-1) = k(4*(2 * 2 + k(2)-1) + 2 * 2 + 2*(2 +1)-1) = 
k(4*(2 * 2) + 2*(2+1)-1 + 2 * 2 + 2 * (2+1)-1) = k(16 + 5 + 4 + 5) = k(30) = 2 * (30+1) = 92
<br>

<details>
<summary>Solution</summary>

~~~
x1 = 39
x2 = 400
x3 = 92
x4 = 62
x5 = 0
~~~
</details>
