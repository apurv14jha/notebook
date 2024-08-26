<!-- # DSA Solved Questions -->

## Mathematics

### Count Digits

Count the number of digits in a positive integer.

#### Solution

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
<hr>

### Palindrome Number

Check whether a number is Palindrome or not. A palindrome number is a positive integer that remains the same when its digits are reversed.

#### Solution

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

- **Time Complexity:** O(log n)
- **Auxiliary Space:** O(1)
<hr>

### Recursive Factorial

Find the factorial of a number recursively.

#### Solution

```javascript
function fact(n) {
  // Check if n is 0
  if (n === 0) {
    // If n is 0, return 1 as the factorial of 0 is 1
    return 1;
  }
  // Calculate the factorial of n by multiplying n with the factorial of (n - 1)
  return n * fact(n - 1);
}
```

- **Time Complexity:** O(n)
- **Auxiliary Space:** O(n)
<hr>

### Trailing Zeros in Factorial

Find the number of zeros present in the end of the factorial of a number.

#### Solution

##### _Explanation_

> The function `countTrailingZeros(n)` calculates the number of trailing zeros in the factorial of a given number `n` (i.e., `n!`). Trailing zeros in a number are created by factors of 10, which are the product of factors 2 and 5. In the factorial of a number, the number of factors of 2 will always be more than or equal to the number of factors of 5, so the count of trailing zeros is determined by the number of times 5 is a factor in the numbers from 1 to `n`. We do that by dividing `n` by increasing powers of 5 (5, 25, 125, etc.), which allows us to count not only the multiples of 5 but also the multiples of higher powers of 5 that contribute additional factors. This ensures that we accurately account for all the factors of 5 in the factorial.
>
> **Example: Calculating the number of trailing zeros in `100!` using the function:**
>
> 1. **First Iteration:** `i = 5`
>
>    - `Math.floor(100 / 5) = 20`
>    - `res = 0 + 20 = 20`
>
> 2. **Second Iteration:** `i = 25`
>
>    - `Math.floor(100 / 25) = 4`
>    - `res = 20 + 4 = 24`
>
> 3. **Third Iteration:** `i = 125` (Since `125 > 100`, the loop ends.)
>
> 4. **Result:** The final value of `res` is 24, meaning `100!` has 24 trailing zeros. Each iteration effectively counts how many times a factor of 5 appears, considering higher powers of 5 as well, which contributes to the total number of trailing zeros.

```javascript
function countTrailingZeros(n) {
  // Initialize a counter to store the number of trailing zeros
  let res = 0;

  // Iterate through multiples of 5 up to n
  for (let i = 5; i <= n; i = i * 5) {
    // Add the integer division of n by i to the result
    res = res + Math.floor(n / i);
  }

  // Return the total count of trailing zeros
  return res;
}
```

- **Time Complexity:** O(log n)
- **Auxiliary Space:** O(1)
<hr>

### HCF of Two Numbers

Find the greatest number that divides both the given numbers perfectly.

#### Solution 1: Euclidean Algorithm

##### _Explanation_

> The function `hcf(a, b)` calculates the Highest Common Factor (HCF) of two given numbers `a` and `b`. The Euclidean algorithm is an efficient method for computing the HCF. It works on the principle that the HCF of two numbers also divides their difference. The algorithm repeatedly replaces the larger number by its difference with the smaller number until the two numbers become equal. This final value is the HCF of the original two numbers.
>
> **Example: Calculating the HCF of `48` and `18` using the function:**
>
> 1. **First Iteration:** `a = 48`, `b = 18`
>
>    - Since `a > b`, subtract `b` from `a`
>    - `a = 48 - 18 = 30`
>
> 2. **Second Iteration:** `a = 30`, `b = 18`
>
>    - Since `a > b`, subtract `b` from `a`
>    - `a = 30 - 18 = 12`
>
> 3. **Third Iteration:** `a = 12`, `b = 18`
>
>    - Since `b > a`, subtract `a` from `b`
>    - `b = 18 - 12 = 6`
>
> 4. **Fourth Iteration:** `a = 12`, `b = 6`
>    - Since `a > b`, subtract `b` from `a`
>    - `a = 12 - 6 = 6`
>
> **Result:** The final value of `a` (or `b`) is `6`, meaning the HCF of `48` and `18` is `6`. Each iteration effectively reduces the problem size by subtracting the smaller number from the larger one until both numbers are equal.

```javascript
function hcf(a, b) {
  // While a and b are not equal, continue the loop
  while (a !== b) {
    // If a is greater than b, subtract b from a
    if (a > b) {
      a = a - b;
    } else {
      // Otherwise, subtract a from b
      b = b - a;
    }
  }

  // Return the final value of a, which is the HCF
  return a;
}
```

- **Time Complexity:** O(log min(a, b))
- **Auxiliary Space:** O(1)

#### Solution 2: Optimized Euclidean Algorithm

##### _Explanation_

> **The optimized Euclidean algorithm** further simplifies the process of computing the HCF. The function `hcf(a, b)` uses a more efficient approach by leveraging the modulo operation. Instead of repeatedly subtracting the smaller number from the larger one, this algorithm reduces the problem size more quickly by taking the remainder of the division of `a` by `b`. This significantly speeds up the computation.
>
> **Example: Calculating the HCF of `48` and `18` using the optimized Euclidean algorithm:**
>
> 1. **First Call:** `hcf(48, 18)`
>
>    - Since `b ≠ 0`, compute `hcf(18, 48 % 18)`
>    - `48 % 18 = 12`
>    - **Next Call:** `hcf(18, 12)`
>
> 2. **Second Call:** `hcf(18, 12)`
>
>    - Since `b ≠ 0`, compute `hcf(12, 18 % 12)`
>    - `18 % 12 = 6`
>    - **Next Call:** `hcf(12, 6)`
>
> 3. **Third Call:** `hcf(12, 6)`
>
>    - Since `b ≠ 0`, compute `hcf(6, 12 % 6)`
>    - `12 % 6 = 0`
>    - **Next Call:** `hcf(6, 0)`
>
> 4. **Fourth Call:** `hcf(6, 0)`
>    - Since `b = 0`, return `a`
>    - **Result:** The HCF of `48` and `18` is `6`.

```javascript
function hcf(a, b) {
  // Base case: If b is 0, the HCF is a
  if (b === 0) {
    return a;
  }
  // Recursive case: Call hcf with b and the remainder of a divided by b
  return hcf(b, a % b);
}
```

- **Time Complexity:** O(log min(a, b))
- **Auxiliary Space:** O(log min(a, b))
<hr>

### LCM of Two Numbers

Find the smallest number divisible by both the given integers.

#### Solution

##### _Explanation_

> We use the Euclidean algorithm to find the HCF. This HCF is then used to find the LCM by using this formula:
>
> LCM x HCF = first number X second number
>
> => **LCM = (first number X second number) / HCF**

```javascript
function hcf(a, b) {
  // Base case: If b is 0, the HCF is a
  if (b === 0) {
    return a;
  }
  // Recursive case: Call hcf with b and the remainder of a divided by b
  return hcf(b, a % b);
}

function lcm(a, b) {
  // Get the LCM by dividing the product of the numbers by the HCF
  return (a * b) / hcf(a, b);
}
```

- **Time Complexity:** O(log min(a, b))
- **Auxiliary Space:** O(log min(a, b))
<hr>

### Check for Prime

Check if a number is a prime number.

#### Solution 1: Efficient Method

##### _Explanation_

> This method of checking if a number `n` is prime takes the efficiency of the basic square root method a step further by incorporating additional optimizations. These optimizations focus on reducing unnecessary checks, making the process faster and more scalable for large numbers.
>
> **Core Idea:**
>
> 1. **Handling Small and Obvious Cases:**
>       - The method quickly handles small numbers and obvious non-prime cases:
>         - `n = 1` is not prime.
>         - `n = 2` and `n = 3` are prime numbers.
>         - Numbers divisible by `2` or `3` (except `2` and `3` themselves) are not prime.
>
> 2. **Optimized Divisor Check:**
>       - Instead of checking every number up to the square root of `n`, the method focuses on numbers that are more likely to be divisors:
>         - It starts checking from `5` and increments by `6` in each loop iteration. This effectively tests numbers of the form `6k ± 1`, which are the only possible forms that prime numbers greater than `3` can take.
>         - This skips all even numbers and multiples of `3`, as they are already filtered out.
>
> 3. **Minimizing Checks:**
>       - The loop checks divisibility by both `i` and `i + 2` in each iteration, covering two potential divisors at once. This reduces the number of iterations compared to a more straightforward approach.
>
> 4. **Conclusion:**
>       - By combining these strategies, this method ensures that only the most likely divisors are considered, making it particularly efficient for determining the primality of large numbers.
>
> This approach balances advanced optimizations with a clear strategy, making it a highly efficient method for prime number checking, especially as the size of `n` increases.

#### Solution 2: More Efficient Method (for large numbers)

##### _Explanation_

> This method enhances the efficiency of prime number checking by incorporating a few optimizations beyond the basic approach. It takes advantage of patterns in prime numbers to minimize unnecessary checks, making it particularly effective for large numbers.
>
> **Core Idea:**
>
> 1. **Initial Special Cases:**
>    - The function first handles specific small cases:
>      - `n = 1` is immediately deemed non-prime.
>      - `n = 2` and `n = 3` are recognized as prime numbers.
>    - It also checks divisibility by `2` and `3` early on since any even number or a multiple of `3` (other than `2` and `3` themselves) cannot be prime.
> 2. **Skipping Even and Multiple of 3 Checks:**
>    - The function then skips checking multiples of `2` and `3` by starting the loop from `5` and incrementing by `6` in each iteration (`i = i + 6`). This approach targets numbers of the form `6k ± 1`, where `k` is a whole number. This is based on the observation that all primes greater than `3` can be expressed as `6k ± 1`.
> 3. **Further Efficiency:**
>    - Within the loop, the function checks for divisibility by `i` and `i + 2`. This covers both numbers of the form `6k - 1` and `6k + 1` in each iteration. By only considering these candidates, the method reduces the number of checks needed, further enhancing efficiency.
> 4. **Conclusion:**
>    - If no divisors are found in this refined loop, the number `n` is confirmed to be prime.
>      This method is particularly useful for checking large numbers, as it minimizes redundant operations and focuses on the most likely candidates for primality.

```javascript
function isPrime(n) {
  // Return false if the number is 1.
  if (n === 1) return false;

  // Return true if the number is 2 or 3.
  if (n === 2 || n === 3) return true;

  // Return false if the number is divisible by 2 or 3.
  if (n % 2 === 0 || n % 3 === 0) return false;

  // Iterate from 5 to the square root of n, incrementing by 6 each time.
  for (let i = 5; i * i <= n; i = i + 6) {
    // Return false if the number is divisible by i or i + 2.
    if (n % i === 0 || n % (i + 2) === 0) return false;
  }

  // If the loop completes without finding a divisor, return true.
  return true;
}
```

- **Time Complexity:** O(√n)
- **Auxiliary Space:** O(1)
<hr>

###
