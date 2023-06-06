#include <stdio.h>


int add(int a, int b);
int subtract(int a, int b);
int multiply(int a, int b);
float divide(int a, int b);


typedef int (*ArithmeticFunction)(int, int);
typedef float (*DivisionFunction)(int, int);


void process(int a, int b, ArithmeticFunction operation) {
    int result = operation(a, b);
    printf("%d\n", result);
}


void processDivide(int a, int b, DivisionFunction operation) {
    float result = operation(a, b);
    printf("%f\n", result);
}


int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}
float divide(int a, int b) {
    return (float)a / b;
}

int main() {
    process(5, 10, add);
    process(5, 10, subtract);
    process(5, 10, multiply);
    processDivide(5, 10, divide);
    return 0;
}
