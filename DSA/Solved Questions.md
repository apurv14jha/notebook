# DSA Solved Questions

## Mathematics

### Count Digits

Count the number of digits in a positive integer.

```javascript
function countDigits(num) {
  // Initialize a counter to keep track of the digit count
  let count = 0;

  // Continue the loop as long as the number is greater than 0
  while (num > 0) {
    // Remove the last digit from the number by dividing by 10 and flooring the result
    num = Math.floor(num / 10);

    // Increment the count for each digit removed
    count++;
  }

  // Return the final count of digits
  return count;
}
```

- **Time Complexity:** O(log n)
- **Auxiliary Space:** O(1)

### Palindrome Number

Check whether a number is Palindrome or not. A palindrome number is a positive integer that remains the same when its digits are reversed.

```javascript
function isPalindrome(n) {
  // Initialize a variable to store the reversed number
  let rev = 0;

  // Create a temporary variable to preserve the original number
  let temp = n;

  // Iterate while the temporary number is not zero
  while (temp !== 0) {
    // Extract the last digit of the temporary number
    let ld = temp % 10;

    // Build the reversed number by multiplying the current reversed number by 10 and adding the last digit
    rev = rev * 10 + ld;

    // Remove the last digit from the temporary number
    temp = Math.floor(temp / 10);
  }

  // Check if the original number and its reversed version are equal
  return rev === n;
}
```

- **Time Complexit:** O(log n)
- **Auxiliary Space:** O(1)
