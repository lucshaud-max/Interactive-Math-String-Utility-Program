#include <bits/stdc++.h>
using namespace std;


// ---------------------------- Helpers ----------------------------


int getInt(const string &prompt) {
while (true) {
cout << prompt;
long long x; // allow large input before range checks
if (cin >> x) {
return static_cast<int>(x);
} else {
cout << "Invalid input. Please enter a whole number.\n";
cin.clear();
cin.ignore(numeric_limits<streamsize>::max(), '\n');
}
}
}


int getIntInRange(const string &prompt, int low, int high) {
while (true) {
int x = getInt(prompt);
if (x < low || x > high) {
cout << "Please enter a number between " << low << " and " << high << ".\n";
} else {
return x;
}
}
}


int getPositiveInt(const string &prompt) {
while (true) {
int n = getInt(prompt);
if (n <= 0) {
cout << "Please enter a positive integer (> 0).\n";
} else {
return n;
}
}
}


// ---------------------------- Features ----------------------------


// 1) Factorial (while loop)
void factorialCalculator() {
cout << "\n--- Factorial Calculator ---\n";
// Guard against overflow for unsigned long long (max 20!)
int n = getIntInRange("Enter a positive integer (1..20): ", 1, 20);


unsigned long long result = 1;
int i = 1;
while (i <= n) { // required: while loop
result *= i;
++i;
}


cout << "\nFactorial of " << n << " is: " << result << "\n\n";
}


// 2) Number Pyramid (for + nested loops)
void numberPyramid() {
cout << "\n--- Number Pyramid ---\n";
int rows = getIntInRange("Enter number of rows (1..20): ", 1, 20);


// Print left-aligned as in example but visually centered with leading spaces
for (int i = 1; i <= rows; ++i) {
// leading spaces to shape the pyramid
for (int s = 0; s < rows - i; ++s) cout << ' ';
}
