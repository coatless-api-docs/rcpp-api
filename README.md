# Rcpp API Documentation (`rcpp-api`)

This repository contains the Rcpp API documentation project. The project is 
rooted in providing a much needed face lift to working with one of the most
popular ways to augment _R_ with _C++_. 

## Goal

Provide documentation that lists, describes, and provides an example of each 
known Rcpp data type and function alongside best practices. The documentation 
should be ready for inclusion within Rcpp 0.13.0 scheduled for release in 
Feburary 2017.

## Style

The main style for this documentation will mimic the [Armadillo documentation](http://arma.sourceforge.net/docs.html) 
that involves first listing the different data structures before detailing class
methods and overall function uses. 

Each section should contain:

- Name of data type or function
- Comment as to what arguments are accepted 
- Notes related to any limitations (e.g. 20 parameters) or C++ specific difference. 
- Examples that are written as if they are embedded within a function or main 
  alongside their expected output in comment form.

The following sample echoes the above tenets 

```
## sum( X ) {#sum}

- Compute the overall summation of all elements.

- Supported types are `Integer` or `Numeric` of a `Vector` or `Matrix`. 

- Examples:

// Sample data
NumericVector x = NumericVector::create(3.2, 8.1, 9.5, 8.6, 5.7);

double y = sum(x);
// Output: 35.1

- See also:
    - [rowSums](#rowSums)
    - [colSums](#colSums)
```

Functions that share common features such as the trigonometric and probability
distribution functions should be grouped together under a common banner to
decrease repeative entries. The name of the entry should be `[subject](#subject-ref-tag)`
to allow for "See also" links and inclusion in the Table of Contents.

## Contributing

To contribute, please submit a [Pull Request (PR)](https://github.com/coatless/rcpp-api/pulls)
with the desired documentation change.