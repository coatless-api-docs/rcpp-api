# Rcpp API Documentation (`rcpp-api`)

This repository contains the Rcpp API documentation project. The project is 
rooted in providing a much needed face lift to working with one of the most
popular ways to augment _R_ with _C++_. 

## Goal

Provide documentation that lists, describes, and provides an example of each 
known Rcpp data type and function alongside best practices. The documentation 
should be ready for inclusion within Rcpp 1.x.0 scheduled for release in 
January 2018.

## Style

The main style for this documentation will mimic the [Armadillo documentation](http://arma.sourceforge.net/docs.html) 
that involves first listing the different data structures before detailing class
methods and overall function uses. 

Each section should contain:

- Name of data type or function
- Comment as to what arguments are accepted 
- Notes related to any limitations or C++ specific difference (e.g. 20 parameters for `::create()`) 
- Examples that are written as if they are embedded within a function or main 
  alongside their expected output in comment form
    - Vectors or matrices should be written in _uppercase_ and
      follow a logical alphabetic naming progression (e.g. `A`, `B = 2*A`)
    - Scalar should be written in _lowercase_ (e.g. `summed`, `val_summed`)

The following sample echoes the above tenets 

````
```
### sum( X ) {#sum}

- Compute the overall summation of all elements.

- Supported types are `Numeric`, `Integer`, or `Logical` in a `Vector` or `Matrix`. 

- Examples:

```cpp
// Sample data
NumericVector X = NumericVector::create(3.2, 8.1, 9.5, 8.6, 5.7);

double val_sum = sum(X);
// Output: 35.1
```

- See also:
    - [rowSums](#rowSums)
    - [colSums](#colSums)
````

Functions that share common features such as the trigonometric and probability
distribution functions should be grouped together under a common banner to
decrease repeative entries. The name of the entry should be `[subject](#subject-ref-tag)`
to allow for "See also" links and inclusion in the Table of Contents.

## Contributing

To contribute, please submit a [Pull Request (PR)](https://github.com/coatless/rcpp-api/pulls)
with the desired documentation change.