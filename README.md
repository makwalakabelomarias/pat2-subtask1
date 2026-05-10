#include <iostream>
#include <string>
#include <cctype>
using namespace std;

int main() {
    map<char, string> morse = {
        {'A', ".-"},   {'B', "-..."}, {'C', "-.-."}, {'D', "-.."},
        {'E', "."},    {'F', "..-."}, {'G', "--."},  {'H', "...."},
        {'I', ".."},   {'J', ".---"}, {'K', "-.-"},  {'L', ".-.."},
        {'M', "--"},   {'N', "-."},   {'O', "---"},  {'P', ".--."},
        {'Q', "--.-"}, {'R', ".-."},  {'S', "..."},  {'T', "-"},
        {'U', "..-"},  {'V', "...-"}, {'W', ".--"},  {'X', "-..-"},
        {'Y', "-.--"}, {'Z', "--.."}
    };

    string message;
    cout << "Enter a message in English (A-Z characters only): ";
    getline(cin, message);

    string fullMorse = "";

    for (char c : message) {
        if (isalpha(c)) {
            char upper = toupper(c);
            cout << upper << ": " << morse[upper] << endl;
            fullMorse += morse[upper] + "   ";
        }
    }

    cout << "Full Morse Code Message: " << fullMorse << endl;

    return 0;
}
