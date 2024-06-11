#include <iostream>
#include <cmath>
#include <string>

using namespace std;

// Function to convert height from meters to feet
double metersToFeet(double meters) {
    return meters * 3.26084;
}

// Function to convert weight from kilograms to pounds
int kilogramsToPounds(int kilograms) {
    return static_cast<int>(kilograms * 2.20462);
}

// Function to determine jacket size
string determineJacketSize(double heightFeet, int weightPounds) {
    if (heightFeet >= 5.9 && heightFeet <= 6.2 && weightPounds >= 65 && weightPounds <= 75) {
        return "Large";
    } else if (heightFeet >= 5.7 && heightFeet <= 5.8 && weightPounds >= 56 && weightPounds <= 65) {
        return "Medium";
    } else if (heightFeet >= 5.2 && heightFeet <= 5.6 && weightPounds >= 50 && weightPounds <= 55) {
        return "Small";
    } else if (heightFeet > 6.2 && weightPounds > 75) {
        return "Extra Large";
    } else if (heightFeet > 5.8 && weightPounds > 65) {
        return "Extra Large";
    } else {
        return "Invalid input";
    }
}

int main() {
    double heightMeters;
    int weightKilograms;

    // Prompt user for height and weight
    cout << "Enter your height in meters: ";
    cin >> heightMeters;
    cout << "Enter your weight in kilograms: ";
    cin >> weightKilograms;

    // Convert height to feet
    double heightFeet = metersToFeet(heightMeters);

    // Convert weight to pounds
    int weightPounds = kilogramsToPounds(weightKilograms);

    // Determine jacket size
    string jacketSize = determineJacketSize(heightFeet, weightPounds);

    // Display the jacket size
    cout << "Your jacket size is: " << jacketSize << endl;

    return 0;
}
