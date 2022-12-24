# Average Rate (Asian) Option Valuation

The payoff of an Asian option depends on the average of the underling stock price over certain time interval. Since no general analytical solutions for the price of the Asian option is known, a variety of techniques have been proposed to analyze the arithmetic average Asian options. 

These include: Monte Carlo simulation, numerical inversion of the Laplace transformation of the Asian option price derived by Geman and Yor (1993), alternative PDE techniques suggested by Rogers and Shi (1995), and various approximations (for instance, Turnbull and Wakeman (1991), and Curran (1994)). Numerical inversion of the Laplace transform or PDE techniques of Rogers and Shi tend to give inaccurate results for cases of short maturities or small volatilities. Monte Carlo simulation always works well, but it can be computationally inefficient. Since GED’s model is based on Curran (1994), 

Specifically, at time 0, an Asian call/put is valued as the payoff at maturity discounted using risk free rate (ref. https://finpricing.com/lib/IrBasisCurve.html)

 

where K is the strike price, and the average is

 

with wi > 0 as the weights of the arithmetic mean, Sti as the values of the underlying at the averaging time ti, and tn = T as the option maturity date.

The arithmetic mean (3) is difficult to work with, and the approach taken here is to follow Curran (1994) and re-write, for example, the call option value as an iterated expectation

 

where the geometric mean is

 

When the underlying is assumed to follow a geometric Brownian motion process, the geometric
mean is lognormally distributed (Curran (1994), and Musiela and Rutkowski (1998)), and the exterior expectation in (4) reduces to an integral over the lognormally distributed G

 

Where

 

and where g(G) is the density of the geometric average. An approximation to this entails neglecting the
first term C1 and writing

 

which is justified by the fact that the probability of the geometric average being below the strike K while the arithmetic average being above it is small.

We now define all the pieces require to evaluate (9). Given the following process for the underlying,

 

the average drift and volatilities are

 

and the expected value of the logarithm of the equity is

 

For option valuation the equity drift is given by the risk-free rate less the dividend yield, and the average volatilities are implied by market prices of equity options.

Here the mean and variance of the underlying

 

The equity correlations over different horizons are approximated as (i < j)

 





