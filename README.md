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

### sinclude
A simpler version of `include` that makes a few assumptions.

Takes a single string `x` and imports `x.charm` with the namespace `x.`.
