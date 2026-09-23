KYEGOMBE SHAFIQ J 25/U/08737/PS BCCE
# Credit Card Number Validation

## Introduction

This C++ program checks whether a credit card number is valid. It uses a `vector<int>` to store the individual digits of the card number.

The program checks:

* The number of digits.
* The prefix of the card number.
* The sum of the digits using the required calculation.
* Whether the final sum is divisible by 10.

If all the conditions are satisfied, the card number is considered valid.

## How the Program Works

The card number is first read as a `string` instead of an integer. This makes it easier to handle all the digits, especially for a 16-digit number.

Each character is then converted into an integer and stored in a vector.

For example:

```text
4242424242424242
```

is stored approximately as:

```text
4 2 4 2 4 2 4 2 4 2 4 2 4 2 4 2
```

## Main Functions

### `readCardNumber()`

Reads the card number from the user and stores each digit in a vector.

### `getPrefix()`

Gets the first `k` digits of the card number.

For example:

```cpp
getPrefix(number, 2)
```

gets the first two digits.

### `prefixMatched()`

Checks whether the card starts with one of the accepted prefixes. The program checks for:

```text
4, 5, 37 and 6
```

### `getSize()`

Returns the number of digits in the card number using:

```cpp
number.size()
```

### `sumOfOddPlace()`

Adds the digits from the selected positions in the vector. The loop increases by 2 each time:

```cpp
i += 2
```

### `sumOfDoubleEvenPlace()`

Takes the other selected digits, doubles them and adds the results together.

### `getDigit()`

If doubling a digit gives a two-digit number, this function adds the two digits.

For example:

```text
14 → 1 + 4 = 5
```

### `isValid()`

This is the main validation function. It checks that:

1. The calculated sum is divisible by 10.
2. The prefix is accepted.
3. The card number has between 13 and 16 digits.

If all these conditions are true, it returns `true`; otherwise, it returns `false`.

## Program Output

The `main()` function displays:

* The prefix.
* Whether the prefix matched.
* The size of the card number.
* The sum of the selected digits.
* The sum after doubling the other digits.
* Whether the card number is valid.

## Example

A test number used in the program is:

```text
4242424242424242
```

The program processes the number digit by digit and then performs the required checks before giving the final result.

## Conclusion

The program uses functions to divide the validation into smaller parts. This makes the code easier to follow and allows each function to handle one specific task.

