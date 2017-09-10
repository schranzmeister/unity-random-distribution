# Random Distributions for Unity

* [Overview](#overview)
* [Usage](#usage)
* [Seeding](#seeding)

## Overview
This asset is designed to make it easy to produce random numbers with a given distribution.
It allows you to create independent, seedable generators.

## Usage

The available classes are:

1. `RandomLinear(min, max)` - Use a linear distribution, i.e. all values are equally likely  
    `min`: The minimum value  
    `max`: The maximum value

2. `RandomExponential(min, lambda)` - Use an [exponential distribution](https://en.wikipedia.org/wiki/Exponential_distribution) - higher values are exponentially less likely  
    `min`: The minimum value  
    `lambda`: The rate parameter (1 / expectation)

3. `RandomGaussian(sigma, mu)` - Use a [Gaussian or Normal distribution](https://en.wikipedia.org/wiki/Normal_distribution) - values' probabability drops off with distance from the centre  
    `sigma`: The standard deviation; a measure of the width of the peak  
    `mu`: The mean (expectation) value; the centre of the peak
    
```c#
using Voxus.Random;

var myGenerator = new RandomLinear(0, 100);

// Get a random float between 1 and 100
var randomNumber = myGenerator.Get();
```

## Seeding
All the supplied generators have a `SetSeed()` method that can be used to seed each generator independently.
This is especially useful for something like procedural generation.
