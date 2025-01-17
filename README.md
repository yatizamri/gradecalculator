
#include <iostream>
#include <iomanip> // For formatting output
int main() {
    int numSubjects;
    double totalMarks = 0, totalWeight = 0;
    // Input: Number of subjects
    std::cout << "Enter the number of subjects: ";
    std::cin >> numSubjects;
    // Arrays to store marks and weights
    double marks[numSubjects], weights[numSubjects];
    // Input: Subject details
    for (int i = 0; i < numSubjects; ++i) {
        std::cout << "\nEnter details for subject " << i + 1 << ":\n";
        std::cout << "Marks obtained (out of 100): ";
        std::cin >> marks[i];
        std::cout << "Weightage (e.g., 0.3 for 30%): ";
        std::cin >> weights[i];
        // Add to totals
        totalMarks += marks[i] * weights[i];
        totalWeight += weights[i];
    }
    // Calculate Weighted Average
    double weightedAverage = totalMarks / totalWeight;
    // Determine Grade
    char grade;
    if (weightedAverage >= 90) {
        grade = 'A';
    } else if (weightedAverage >= 80) {
        grade = 'B';
    } else if (weightedAverage >= 70) {
        grade = 'C';
    } else if (weightedAverage >= 60) {
        grade = 'D';
    } else {
        grade = 'F';
    }
    // Output Results
    std::cout << "\nFinal Results:\n";
    std::cout << "-----------------------\n";
    std::cout << std::fixed << std::setprecision(2); // Format to 2 decimal places
    for (int i = 0; i < numSubjects; ++i) {
        std::cout << "Subject " << i + 1 << ": Marks = " << marks[i] 
                  << ", Weight = " << weights[i] << "\n";
    }
    std::cout << "Weighted Average: " << weightedAverage << "\n";
    std::cout << "Final Grade: " << grade << "\n";
    return 0;
}
