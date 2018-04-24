# clr
(Charm Library Repository) A repository of Charm libraries.

## Documentation

### random
A simple linear congruential generator implementation of a random number generator.

The algorithm for a random number is `x(n) = ((a * x(n-1)) + c) mod m`.
You can change the values of `x`, `a`, `c` and `m` with the functions `seed`, `multiplier`, `increment` and `modulo`, respectively. 
Each of these functions takes a single integer and sets the corresponding variable to that integer.

Call the `random` function to push a random number with these set variables. All of the variables are already predefined to values that will work, but for proper randomness try to seed the generator with environmental variables such as user input.

Until Charm is fixed, this function will occasionally raise a floating point error. Try not to use a low number in the multiplier variable to minimize the chances of this.

### exponent
An implementation of exponentiation.
```
int int **
```

### for
A Python-style `for` loop implementation.
```
list list for
```
The left argument is the iterable while the right argument is the code.

The items in the iterable are iterated through one-by-one and the code is run one time for each item. Get the item from the code by calling the `item` function.
The items are given to the code in the form of lists; use `i` to unquote these lists before using them.
Replace `for` with `revfor` to iterate backwards.

An example of the `for` function is `[ 5 2 6 ] [ item i put ] for`, which prints each of the numbers in the list in turn.

Note that unlike the `map` function in Charm's prelude, `for` does not expect anything specific from the user. You may do whatever you like to the stack from a `for` block without consequences.

### setrefs
Requires the `for` library.

Defines a single function, `setrefs`, that takes in a list and defines multiple references from the stack.

This is best explained with an example: `4 7 2 [ " first " " second " " third " ] setrefs` defines three named references; `" first "`, which is set to 4, `" second "`, set to 7, and `" third "`, set to 2.

This function is useful for taking arguments in a function in a succinct and readable way.

### modref
Modify a reference according to a function.
```
any list modref
```
Takes an object representing the reference to modify and a list representing the action to perform on it, then performs that action on the reference, redefining the reference to the result of the action.

For example, `" my_ref " [ 1 + ] modref` would add 1 to the `" my_ref "` reference.

### reverse
Requires the `for` library.

Reverse the list on top of the stack.

### sinclude
A simpler version of `include` that makes a few assumptions.

Takes a single string `x` and imports `x.charm` with the namespace `x.`.
