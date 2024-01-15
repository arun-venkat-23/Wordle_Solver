# Wordle Solver

This is a C++ implementation of a Wordle solver. Wordle is a word-guessing game where the player tries to guess a hidden five-letter word. After each guess, the player receives feedback on the correctness and position of the guessed letters. 

## Code Explanation

#### Included Libraries
```
#include <ostream>
#include <string>
#include <vector>
#include <fstream>
#include <iostream>
#include <unordered_set>
#include <stdexcept>
#include <unordered_map>
#include <algorithm>
#include <array>
#include<random>
#include<set>
#define CATCH_CONFIG_MAIN
#include "catch.hpp"
```
    ostream: Output stream handling.
    string: String manipulation.
    vector: Dynamic array container.
    fstream: File stream handling.
    iostream: Input/output stream handling.
    unordered_set: Unordered set container for storing unique words.
    stdexcept: Standard exception handling.
    unordered_map: Unordered map container for storing character frequencies.
    algorithm: General algorithms.
    array: Static array container.
    random: Random number generation.
    set: Set container.
    CATCH_CONFIG_MAIN: Macro to define the main function for the Catch framework.
    catch.hpp: Catch framework for unit testing.

#### Function Declaration
```
std::unordered_set<std::string> GetAllValidWords();
std::ostream& operator<<(std::ostream& os, const LetterState& state);
std::ostream& operator<<(std::ostream& os, const WordleLetterStates& states);
```
> GetAllValidWords(): Retrieves valid words of length 5 from a dictionary file.
> operator<< for LetterState: Output stream operator for LetterState enum.
> operator<< for WordleLetterStates: Output stream operator for WordleLetterStates array.

#### Class Declaration: Wordle
```
class Wordle {
  public:
    explicit Wordle(std::string true_word);
    ~Wordle();
    WordleLetterStates CharacterizeWord(const std::string& query);
  private:
    std::string true_word_;
    size_t counter_{0};
};
```
> Wordle: Class to represent the Wordle game.
> explicit Wordle(std::string true_word): Constructor to initialize the Wordle object with the target word.
> ~Wordle(): Destructor to print the number of guesses when the Wordle object is destroyed.
> CharacterizeWord(const std::string& query): Method to characterize a guessed word and provide feedback.

#### Function Definition: PickRandomWord
```
std::string PickRandomWord(const std::unordered_set<std::string>& wds);
```
Function to pick a random word from a set of words.

#### Function Definition: SolveWordle
```
std::string SolveWordle(Wordle& wordle);
```
Function to solve the Wordle game given a Wordle object.

#### Using Section
```
using Catch::Matchers::Equals;
```
Using declaration for Catch framework matchers.

###### Catch Unit Tests

TEST_CASE("WordleTest_chase", "[given_test]") {
  // ... Test case for a specific target word
}

TEST_CASE("WordleTest_cases", "[given_test]") {
  // ... Another test case for a specific target word
}

Unit tests using the Catch framework to verify the correctness of the Wordle solver.

#### LetterState Output Stream Operator
```
std::ostream& operator<<(std::ostream& os, const LetterState& state) {
  // ... Implementation for output stream operator
  return os;
}
```
Output stream operator for the LetterState enum.

#### Helper Functions: ValidateWord and ValidateStates
```
void ValidateWord(const std::string& word);
void ValidateStates(const WordleLetterStates& states);
```
Helper functions to validate a word and the states in the WordleLetterStates array.

#### WordleLetterStates Output Stream Operator
```
std::ostream& operator<<(std::ostream& os, const WordleLetterStates& states) {
  // ... Implementation for output stream operator
  return os;
}
```
Output stream operator for the WordleLetterStates array.

#### CharacterizeWord Method Implementation
```
WordleLetterStates Wordle::CharacterizeWord(const std::string& z) {
  // ... Implementation for CharacterizeWord method
  return states;
}
```
Implementation of the CharacterizeWord method in the Wordle class.

#### Destructor Implementation
```
Wordle::~Wordle() {
  std::cout << "Number of guesses: " << counter_ << std::endl;
}
```
Destructor implementation printing the number of guesses.

#### Wordle Solver Implementation: SolveWordle
```
std::string SolveWordle(Wordle& wordle) {
  // ... Implementation for the Wordle solver
  return answer;
}
```
Implementation of the Wordle solver function.

#### Catch Test Cases (Example)
```
TEST_CASE("WordleTest_chase", "[given_test]") {
  Wordle wordle{"slurp"};
  REQUIRE_THAT(SolveWordle(wordle), Equals("slurp"));
}

TEST_CASE("WordleTest_cases", "[given_test]") {
  Wordle wordle{"tawny"};
  REQUIRE_THAT(SolveWordle(wordle), Equals("tawny"));
}
```
Example test cases using the Catch framework.
