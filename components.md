# Components
This is a list of all (currently implemented) components that are usable in an Ohm circuit.

## Single character

### Components with blocks
These components will execute all components between them and a `;` character (or end of line), called a *block*.

|Component|Description|
|---------|-----------|
|`?`|Pops `a`, and if true, executes its associated block (if statement).|
|`¿`|If this component is between a `?` and `;`, the block from `¿` to `;` will be executed if the condition given to `?` is false (else clause).|
|`:`|Pops `a` and executes its associated block for each element in `a`, with the special components `^` and `_` set as the index and element currently being looped, respectively (foreach loop).|
|`M`|Pops `a` and runs its associated block `a` times.|
|`Å`|Pops `a` and pushes whether all the elements in `a` push `true` from its associated block.|
|`É`|Pops `a` and pushes whether any of the elements in `a` push `true` from its associated block.|
|`░`|Pops `a` and pushes an array containing all elements of `a` for which its associated block pushes `true` (filter/select).|
|`▒`|Same as above, except `false` instead of `true` (reject).|
|`▓`|Pops `a` and pushes an array with the results of running its associated block once for every element in `a` (map/collect).|
|`╠`|Pops `a` and pushes `a` sorted by the results of running its associated block once for every element in `a`.|
|`╨`|Pops `a` and pushes the element in `a` that gives the maximum value from its associated block.|
|`╥`|Pops `a` and pushes the element in `a` that gives the minimum value from its associated block.|
|`╫`|Pops `a` and pushes the elements in `a` that give the minimum and maximum value from its associated block.|
|`∞`|Runs its associated block infinitely.|

### Wire/block flow
|Component|Description|
|---------|-----------|
|`Φ`|Pops `a` and executes the wire at index `a`.|
|`Θ`|Executes the wire at the index before the current one.|
|`Ω`|Executes the wire at the index after the current one.|
|`■`|Pops `a` and breaks out of the current block/wire if `a` is true.|

### Utility
|Component|Action|Description|
|---------|------|-----------|
|`!`|Pop `a`|Pushes `a!` (factorial).|
|`"`|N/A|Creates a string literal.|
|`#`|Pop `a`|Pushes the range `0..a`.|
|`$`|N/A|Pushes the current value of the register.|
|`%`|Pop `a`, `b`|Pushes `a % b` (modulo).|
|`&`|Pop `a`, `b`|Pushes `a && b` (boolean AND).|
|`'`|Pop `a`|Pushes the character with char code `a`.|
|`(`|Pop `a`|Pushes `a` without the first element.|
|`)`|Pop `a`|Pushes `a` without the last element.|
|`*`|Pop `a`, `b`|Pushes `a * b` (multiplication).|
|`+`|Pop `a`, `b`|Pushes `a + b` (addition).|
|`,`|Pop `a`|Prints `a` to standard output (with trailing newline).|
|`-`|Pop `a`, `b`|Pushes `a - b` (subtraction).|
|`.`|N/A|Creates a character literal (i.e. `.a` ⇒ `'a'`).|
|`/`|Pop `a`, `b`|Pushes `a / b` (division).|
|`<`|Pop `a`, `b`|Pushes `a < b` (less than).|
|`=`|Get `a`|Prints `a` to standard output (with trailing newline)|.
|`>`|Pop `a`, `b`|Pushes `a > b` (greater than).|
|`@`|Pop `a`|Pushes the range `1..a`.|
|`A`|Pop `a`|Pushes the absolute value of `a`.|
|`B`|Pop `a`, `b`|Pushes `a` converted to base `b`.|
|`C`|Pop `a`, `b`|Pushes `a` concatenated with `b`.|
|`D`|Pop `a`|Pushes `a` twice (duplicate).|
|`E`|Pop `a`, `b`|Pushes `a == b` (equality).|
|`F`|N/A|Pushes boolean `false`.|
|`G`|Pop `a`, `b`|Pushes the range `a..b`.|
|`H`|Pop `a`, `b`|Pushes `a.push(b)` (Note that this **does not work** with strings).|
|`I`|N/A|Pushes input from standard input.|
|`J`|Pop `a`|If `a` is an array, pushes `a.join('')`, else pushes `stack.join('')`.|
|`K`|Pop `a`, `b`|Pushes the amount of times that `b` occurs in `a`.|
|`L`|Pop `a`|Prints `a` to standard output (*without* trailing newline).|
|`N`|Pop `a`, `b`|Pushes `a != b` (inequality).|
|`O`|N/A|Removes last element of stack.|
|`P`|Pop `a`|Pushes all primes up to `a`.|
|`Q`|N/A|Reverses stack.|
|`R`|Pop `a`|Pushes `a` reversed.|
|`S`|Pop `a`|Pushes `a` sorted.|
|`T`|N/A|Pushes boolean `true`.|
|`U`|Pop `a`|Pushes `a` uniquified.|
|`V`|Pop `a`|Pushes divisors of `a`.|
|`W`|N/A|Pushes `[stack]` (wrap).|
|`X`|Pop `a`, `b`|Pushes `b` prepended to `a`.|
|`Y`|Pop `a`|Pushes proper divisors of `a`.|
|`Z`|Pop `a`|Pushes `a` split on newlines.|
|`[`|Pop `a`|Pushes `stack[a]`.|
|`\`|Pop `a`|Pushes `!a` (boolean NOT).|
|`]`|Pop `a`|Pushes `a` flattened one level.|
|`^`|N/A|Pushes index of current element in array being looped over.|
|`_`|N/A|Pushes current element in array being looped over.|
|`` ` ``|Pop `a`|Pushes char code of `a`.|
|`a`|Pop `a`, `b`|Pushes `b`, `a` (swap).|
|`b`|Pop `a`|Pushes `a` in binary (base 2).|
|`c`|Pop `a`, `b`|Pushes `a nCr b` (binomial coefficient).|
|`d`|Pop `a`|Pushes `a * 2` (double).|
|`e`|Pop `a`, `b`|Pushes `a nPr b` (permutations).|
|`f`|Pop `a`|Pushes all Fibonacci numbers up to `a`.|
|`g`|Pop `a`, `b`|Pushes the range `a...b`.|
|`j`|Pop `a`, `b`|If `a` is an array, pushes `a.join(b)`, else pushes `stack.join(b)`.|
|`k`|Pop `a`, `b`|Pushes index of `b` in `a`.|
|`l`|Pop `a`|Pushes length of `a`.|
|`m`|Pop `a`|Pushes prime factors of `a`.|
|`n`|Pop `a`|Pushes *exponents* of prime factorization of `a`.|
|`o`|Pop `a`|Pushes full prime factorization of `a`.|
|`p`|Pop `a`|Pushes whether `a` is a prime number.|
|`r`|Pop `a`, `b`, `c`|Pushes `a.tr(b, c)`.|
|`s`|Pop `a`|Pushes `a` as a string.|
|`t`|Pop `a`, `b`|Pushes `a` converted to base 10 from base `b`.|
|`u`|Pop `a`, `b`|Pushes the index of the first occurrence of subarray `b` in `a`.|
|`v`|Pop `a`, `b`|Pushes `a // b` (integer/floor division).|
|`w`|Pop `a`|Pushes `[a]` (wrap).|
|`x`|Pop `a`|Pushes `a` in hexadecimal (base 16).|
|`y`|Pop `a`|Pushes the sign of `a` (`1` if positive, `-1` if negative, `0` if zero).|
|`z`|Pop `a`|Pushes `a` split on spaces.|
|`{`|Pop `a`|Pushes `a` deep flattened.|
|`|`|Pop `a`, `b`|Pushes `a || b` (boolean OR).|
|`}`|Pop `a`|Pushes `a` split into slices of 1 (shorthand for `1σ`).|
|`~`|Pop `a`|Pushes `-a` (negative).|
|`Ç`|Pop `a`, `b`|Pushes an array of each every `b` consecutive elements in `b`.|
|`ü`|N/A|Pushes a space character (` `).|
|`é`|Pop `a`|Pushes `a % 2 == 0` (even).|
|`â`|Pop `a`|Pushes the first `a` prime numbers.|
|`ç`|Pop `a`, `b`|Pushes all possible combinations of length `b` of elements in `a`.|
|`ê`|Pop `a`|Pushes the first `a` Fibonacci numbers.|
|`è`|Pop `a`|Pushes `a % 2 != 0` (odd).|
|`ï`|Pop `a`, `b`|Pushes `a.split(b)`.|
|`î`|Pop `a`|Pushes `a` as an integer.|
|`ì`|Pop `a`|Pushes if `a` is an integer.|
|`Ä`|Pop `a`, `b`|Pushes `a` onto the stack `b` times.|
|`æ`|Pop `a`|Pushes `a` as a palindrome.|
|`ô`|Pop `a`|Pushes `a` as a float.|
|`ö`|Pop `a`|Pushes `a != 0`.|
|`ÿ`|N/A|Pushes empty string (`''`).|
|`Ö`|Pop `a`|Pushes `a == 0`.|
|`Ü`|Pop `a`, `b`|Pushes set union of `a` and `b`.|
|`¢`|Get `a`|Sets the value of the register to `a`.|
|`£`|Pop `a`|Sleeps execution for `a` seconds.|
|`¥`|Pop `a`, `b`|Pushes `a % b == 0` (divisibility).|
|`₧`|Pop `a`|Pushes `a == a.reverse` (palindrome).|
|`ƒ`|Pop `a`|Pushes the `a`th Fibonacci number.|
|`ó`|Pop `a`|Pushes `a` converted to base 10 from binary (base 2).|
|`ú`|Pop `a`|Pushes `a` converted to base 10 from hexadecimal (base 16).|
|`ñ`|Pop `a`|Pushes whether `s` is a Fibonacci number.|
|`Ñ`|N/A|Pushes a newline character (`\n`), functions as a newline inside string literals.|
|`ª`|Pop `a`|Pushes `a[b]` (element at index).|
|`º`|Pop `a`|Pushes 2<sup>`a`</sup>.|
|`⌐`|Pop `a`|Pushes all permutations of `a`.|
|`¬`|Pop `a`|Pushes the power set of `a`.|
|`½`|Pop `a`|Pushes `a / 2` (half).|
|`¼`|N/A|Pushes the current value of the counter.|
|`¡`|N/A|Increments the counter by 1.|
|`«`|Pop `a`, `b`|Pushes `[a, b]` (pair).|
|`»`|Pop `a`|Pushes a *single component* mapped over all values of `a`.|
|`┤`|Pop `a`, `b`|Pushes `a[b, a.length]` (slice from end).|
|`╣`|Pop `a`|Pushes all possible rotations of `a`.|
|`║`|N/A|Creates a base-220 number literal. (i.e. `║Ö╔H╪║` ⇒ `987654321`)|
|`╜`|Pop `a`|Pushes `a` rotated once to the left.|
|`┴`|Pop `a`|Pushes `a` in all upper-case.|
|`┬`|Pop `a`|Pushes `a` in all lower-case.|
|`├`|Pop `a`, `b`|Pushes `a[0, b]` (slice from beginning).|
|`─`|Pop `a`, `b`|Pushes set difference of `a` and `b`.|
|`┼`|N/A|Pushes the first input given.|
|`╟`|Pop `a`|Pushes `a` randomly shuffled.|
|`╚`|Pop `a`, `b`|Pushes `a` with `b` spaces *prepended*.|
|`╔`|Pop `a`, `b`|Pushes `a` with `b` spaces *appended*.|
|`╩`|Pop `a`, `b`|Pushes `a` left-justified to length `b` (with spaces).|
|`╦`|Pop `a`, `b`|Pushes `a` right-justified to length `b` (with spaces).|
|`═`|Pop `a`, `b`, `c`|Pushes `a[b, c]` (slice arbitrarily).|
|`╬`|Pop `a`|Pushes a random element from `a`.|
|`╧`|Pop `a`|Pushes maximum element in `a`.|
|`╤`|Pop `a`|Pushes minimum element in `a`.|
|`╙`|Pop `a`|Pushes `a` rotated once to the right.|
|`╪`|Pop `a`|Pushes minimum and maximum element in `a` as an array in the form `[min, max]`.|
|`┘`|N/A|Pushes the second input given.|
|`┌`|N/A|Pushes the third input given.|
|`█`|N/A|Pushes empty array (`[]`).|
|`▀`|N/A|Creates a compressed string literal (see README).|
|`Γ`|N/A|Pushes -1.|
|`π`|Pop `a`|Pushes the `a`th prime number.|
|`Σ`|Pop `a`|If `a` is an array, pushes the total sum of `a`, else pushes the total sum of the stack.|
|`σ`|Pop `a`, `b`|Pushes `a` split in elements of length `b`.|
|`µ`|Pop `a`|If `a` is an array, pushes the total product of `a`, else pushes the total product of the stack.|
|`τ`|N/A|Pushes the number 10.|
|`δ`|Pop `a`|Pushes an array with the deltas of (distance between) consecutive elements in `a`.|
|`φ`|Pop `a`|Pushes the Euler totient/phi function of `a`.|
|`ε`|Pop `a`, `b`|Pushes whether `b` is in `a`.|
|`∩`|Pop `a`, `b`|Pushes set intersection of `a` and `b`.|
|`≡`|Pop `a`|Pushes `a` three times (triplicate).|
|`±`|Pop `a`, `b`|Pushes the `b`th root of `a`.|
|`≥`|Pop `a`|Pushes `a + 1` (increment).|
|`≤`|Pop `a`|Pushes `a - 1` (decrement).|
|`⌠`|Pop `a`|Pushes `a` rounded *up* to the nearest integer (ceiling).|
|`⌡`|Pop `a`|Pushes `a` rounded *down* to the nearest integer (floor).|
|`÷`|Pop `a`|Pushes `1 / a` (reciprocal).|
|`≈`|Pop `a`|Pushes `a` rounded to the nearest integer.|
|`°`|Pop `a`|Pushes 10<sup>`a`</sup>.|
|`·`|Pop `a`, `b`|Pushes `a` repeated `b` times.|
|`√`|Pop `a`|Pushes the square root of `a`.|
|`ⁿ`|Pop `a`, `b`|Pushes `a`<sup>`b`</sup>.|
|`²`|Pop `a`|Pushes `a` squared.|

## Multi-character

### Arithmetic (`Æ`)
|Component|Action|Description|
|---------|------|-----------|
|`ÆA`|Pop `a`, `b`|Pushes the Ackermann function of `a` and `b`.|
|`ÆC`|Pop `a`|Pushes the cosine of `a` radians.|
|`ÆD`|Pop `a`|Pushes `a` radians converted to degrees.|
|`ÆE`|Pop `a`|Pushes `a` degrees converted to radians.|
|`ÆL`|Pop `a`|Pushes the natural logarithm of `a`.|
|`ÆM`|Pop `a`|Pushes the base 10 logarithm of `a`.|
|`ÆN`|Pop `a`|Pushes the base 2 logarithm of `a`.|
|`ÆS`|Pop `a`|Pushes the sine of `a` radians.|
|`ÆT`|Pop `a`|Pushes the tangent of `a` radians.|
|`Æc`|Pop `a`|Pushes the arccosine of `a`.|
|`Æl`|Pop `a`, `b`|Pushes the base `a` logarithm of `b`.|
|`Æs`|Pop `a`|Pushes the arcsine of `a`.|
|`Æt`|Pop `a`|Pushes the arctangent of `a`.|
|`Æu`|Pop `a`, `b`|Pushes the arctangent of `b / a` (`atan2`).|
|`Æⁿ`|Pop `a`, `b`|Pushes whether `a` is a perfect `b`th power.|
|`Æ²`|Pop `a`|Pushes whether `a` is a perfect square.|

### Constants (`α`)
**Note**: Because these are constants, they only push to the stack.

|Component|Description|
|---------|-----------|
|`αK`|Pushes all the keys on a keyboard (`` `1234567890-=qwertyuiop[]\asdfghjkl;'zxcvbnm,./ ``).|
|`αc`|Pushes all the consonants (`bcdfghjklmnpqrstvwxyz`).|
|`αe`|Pushes all the consonants **without `y`** (`bcdfghjklmnpqrstvwxz`).|
|`αk`|Pushes the alphabet ordered like it is on a keyboard (`qwertyuiopasdfghjklzxcvbnm`).|
|`αv`|Pushes all the vowels (`aeiou`).|
|`αy`|Pushes all the vowels **including `y`** (`aeiouy`).|
|`αê`|Pushes Euler's constant `e` (`2.718281...`).|
|`αß`|Pushes the normal alphabet (`abcdefghijklmnopqrstuvwxyz`).|
|`απ`|Pushes pi (`3.1415926...`).|

### Extras (`∙`)
|Component|Action|Description|
|---------|------|-----------|
|`∙p`|Pop `a`|Pushes all prefixes of `a`.|
|`∙s`|Pop `a`|Pushes all suffixes of `a`.|
|`∙⌐`|Pop `a`, `b`|Pushes whether `a` and `b` are permutations of each other.|
|`∙*`|Pop `a`, `b`|Pushes an array of size `b` filled with `a`.|
