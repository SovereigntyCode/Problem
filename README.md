# Problem
include <iostream>
#include <cmath>
using namespace std;

void instructions() {
    cout << "This program calculates the windshield in Fahrenheit \n" ;
    cout << "If you enter the temperature in degrees Fahrenheit (t) and the velocity of the wind (v) it will calculate the wind chill temperature \n ";
    cout << "v must be a greater then or equal to 0 and less than 100 \n";
    cout << "t must be between absolute 0 and 50 degrees Fahrenheit \n";
}
void input (double& t, double& v) {
    cout << "Enter t" ;
     cin >> t ;
    cout << "Enter v" ;
     cin >> v ;
}

double process(double v, double t){
    double windshield;
    windshield = 35.74 + (.6215 * t) - 35.75 * (pow(v,.16)) + .4275 * t * (pow(v,.16));
    return windshield;
}
void output (double t, double v,double windshield){
    cout << t << "_degrees Fahrenheit \n";
    cout << v << "_ MPH \n";
    cout << "Wind chill temp_" << windshield << "_degrees";
}

int main() {
//Declarations
double t, v, windshield;
char ans; 
instructions ();
//Input

input(t, v);
//Processing

windshield = process(v, t);

//Output
output(t, v, windshield);
}
