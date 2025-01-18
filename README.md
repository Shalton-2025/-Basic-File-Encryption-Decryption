#include <iostream>
#include <string>
#include <cctype> // Include for isalpha and toupper

using namespace std;

char encrypt(char input) {
    if (!isalpha(input)) {
        return input; // Return non-alphabetic characters unchanged
    }

    char upperInput = toupper(input); // Convert to uppercase for consistent behavior
    char enChar = 'A' + ('Z' - upperInput);
    return enChar;
}

int main() {
    string plain = "";
    string encPlain = "";
    string decPlain = ""; // For decrypted text

    cout << "Enter plaintext: ";
    getline(cin, plain); // Use getline to read entire lines, including spaces

    for (char c : plain) { // Use range-based for loop for cleaner code
        encPlain += encrypt(c);
    }

    cout << "Encrypted: " << encPlain << endl;

    for (char c : encPlain) {
        decPlain += encrypt(c); // Decrypt using the same function
    }

    cout << "Decrypted: " << decPlain << endl;

    return 0;
}

