# Playing-With-Recursion
## Few C++ Functions that uses recursion

Recursive function that calculates the power of a number, where the user inputs 
both the base and the exponent. The output include both the input and the result.
```
#include <iostream>
using namespace std;

long long powerof(int base, int power);

int main() {
    int base, power;
    cout << "Enter base number: ";
    cin >> base;
    cout << "Enter power number: ";
    cin >> power;
    cout << base << "^" << power << " = " << powerof(base, power);
    return 0;
}

long long powerof(int base, int power) { //The recursive function
    if (power == 0) return 1;
    else return powerof(base, (power - 1)) * base;
}
```

Recursive function that takes a positive integer and prints its digits in reverse.
```
#include <iostream>
using namespace std;

void reverseof(unsigned int n);

int main() {
    int n;
    cout << "Enter an integer: ";
    cin >> n;
    reverseof(n);
    return 0;
}

void reverseof(unsigned int n) { //The recursive function
    if (n <= 0) return;
    cout << n % 10;
    reverseof(n / 10);
}
```

Recursive function that check if any positive integer n is a prime.
```
#include <iostream>
#include <cmath>
using namespace std;

bool isPrime(int n, int k = 2) { //The recursive function
    if (k > sqrt(n) and n >= k) 
        return true;
    else 
        return (n % k != 0 and n != 1) and isPrime(n, k + 1);
}

int main()  {
    int n = 0;
    while (n >= 0) {
        cout << "\nEnter a number, or a negative integer to terminate: " << endl;
        cin >> n;
        if (isPrime(n)) cout << "true";
        else cout << "false";
    }
    return 0;
}
```

Recursive function that will compare any two doubly linked lists given as arguments. The 
function will return true if both lists have the same values in the same order, and false otherwise.
```
template <typename type>
bool compare(Node<type>* lhs, Node<type>* rhs) {
    if (lhs == nullptr and rhs == nullptr)
        return true;
    else if ((lhs == nullptr and rhs != nullptr) or (lhs != nullptr and rhs == nullptr)) {
        cout << "Lists are not the same size!" << endl;
        return false;
    }
    else
        return (lhs->data == rhs->data) and compare(lhs->next, rhs->next);
}
```
