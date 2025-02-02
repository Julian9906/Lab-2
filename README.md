# Lab-2
#include <stdio.h>
// Exercise 1
void exercise1() {
    int num;
    printf("Enter an integer: ");
    scanf("%d", &num);
    printf("Character: %c\n", num);
}

int main() {
    exercise1();
    return 0;
}

#include <stdio.h>

// Exercise 2
void exercise2() {
    float weight;
    double value;
    printf("Enter your weight in pounds: ");
    scanf("%f", &weight);
    value = 1770.0 * weight * 14.5;
    printf("Your weight in platinum costs $%.4f.\n", value);
}

int main() {
    exercise2();
    return 0;
}

#include <stdio.h>
#include <string.h>

// Exercise 3
void reverseString(char str[]) {
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - i - 1];
        str[len - i - 1] = temp;
    }
}

void exercise3() {
    char word1[50], word2[50], word3[50];
    printf("Enter three words: ");
    scanf("%s %s %s", word1, word2, word3);
    
  reverseString(word1);
  reverseString(word2);
  reverseString(word3);
    
  printf("Reversed: %s %s %s\n", word1, word2, word3);
}

int main() {
    exercise3();
    return 0;
}

#include <stdio.h>
#include <string.h>

// Exercise 4
void exercise4() {
    char name[20], surname[20];
    int age, count = 0;
    float salary, totalSalary = 0.0;
    
   printf("Enter employee details (Name, Surname, Age, Salary):\n");
    for (int i = 0; i < 10; i++) {
        scanf("%s %s %d %f", name, surname, &age, &salary);
        count++;
        totalSalary += salary * 13;
        name[10] = '\0';
        surname[10] = '\0';
        printf("%-3d %-10s %-10s %-3d %.2f %.2f\n", count, name, surname, age, salary, salary * 13);
        if (count % 5 == 0) printf("-----\n");
    }
    printf("Average yearly salary: %.2f\n", totalSalary / 10);
}

int main() {
    exercise4();
    return 0;
}


#include <stdio.h>

// Exercise 5
void exercise5() {
    int days;
    const int DAYS_IN_WEEK = 7;
     for (int i = 0; i < 10; i++) {
        printf("Enter number of days: ");
        scanf("%d", &days);
        printf("%d days = %d weeks & %d days\n", days, days / DAYS_IN_WEEK, days % DAYS_IN_WEEK);
    }
}

int main() {
    exercise5();
    return 0;
}

#include <stdio.h>

// Exercise 6
void exercise6() {
    const float CONVERSION_RATE = 0.92;
    float dollars;
    for (int i = 0; i < 10; i++) {
        printf("Enter amount in dollars: ");
        scanf("%f", &dollars);
        printf("%.2f dollars = %.2f euros\n", dollars, dollars * CONVERSION_RATE);
    }
}

int main() {
    exercise6();
    return 0;
}

#include <stdio.h>

//Exercise 7
int main() {
    int n;
    long long factorial = 1;
    printf("Enter a positive integer: ");
    scanf("%d", &n);
    if (n < 0) {
        printf("Factorial is not defined for negative numbers.\n");
    } else {
        for (int i = 1; i <= n; i++) {
            factorial *= i;  // Multiply the current value of factorial by i
        }
        printf("Factorial of %d is %lld\n", n, factorial);
    } return 0;
}

#include <stdio.h>
#include <math.h>

double zeta_function(double s, int N) {
    double sum = 0.0;
    for (int n = 1; n <= N; n++) {
        sum += 1.0 / pow(n, s);
    }
    return sum;
}

int main() {
    double s;
    int N;
    printf("Enter the value of s (greater than 1): ");
    scanf("%lf", &s);
    printf("Enter the number of terms N for the approximation: ");
    scanf("%d", &N);
if (s <= 1) {
        printf("The Riemann zeta function is not well-defined for s <= 1.\n");
    } else {
        double result = zeta_function(s, N);
        printf("Approximation of the Riemann zeta function for s = %.2lf with N = %d is: %.8lf\n", s, N, result);
    }
 return 0;
}

