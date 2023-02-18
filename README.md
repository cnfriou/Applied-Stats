# Applied-Stats
Applied Statistical Computing - UN2102, Columbia University, Spring 2019

Goals: Simulating probability distributions using the accept-reject method, simulating a
sampling distribution related to the linear regression model.
1 Reject-Accept Method
Let random variable X denote the temperature at which a certain chemical reaction takes
place. Suppose that X has probability density function
(1) f(x) =
{1
9(4 −x2) −1 ≤x ≤2
0 otherwise
Perform the following tasks:
1. Determine the maximum of f(x). Find an envelope function e(x) by using a uniform
distribution for g(x) and setting e(x) = maxx{f(x)}.
2. Using the Accept-Reject Algorithm, write a program that simulates 1000 draws
from the probability density function f(x) from Equation 1.
3. Plot a histogram of your simulated data with the density function f overlayed in the
graph. Label your plot appropriately.
2 Regression and Empirical Size
2.1 Regression
We work with the grocery retailer dataset from Canvas. The description follows:
1
A large national grocery retailer tracks productivity and costs of its facilities closely. Con-
sider a data set obtained from a single distribution center for a one-year period. Each data
point for each variable represents one week of activity. The variables included are num-
ber of cases shipped in thousands (X1), the indirect costs of labor as a percentage of total
costs (X2), a qualitative predictor called holiday that is coded 1 if the week has a holiday
and 0 otherwise (X3), and total labor hours (Y ). Consider the multiple linear regression
model
(2) Yi = β0 + β1 Xi1 + β2 Xi2 + β3 Xi3 + i, i = 1,2,...,52,
and
i
iid∼ N(0,σ2).
Perform the following tasks:
4. Read in the grocery retailer dataset. Name the dataset grocery.
5. Use the least squares equation ˆβ= (XT X)−1XT Y to estimate regression model (2).
To estimate the model, use the linear model function in R, i.e., use lm().
6. Use R to estimate σ2, i.e., compute MSE = 1
n−4
∑n
i=1(Yi − ˆYi)2. To perform this task,
use the residuals function.
2.2 Test for Slope
Now consider investigating if the number of cases shipped (X1) is statistically related to
total labor hours (Y ). To investigate the research question, we run a t-test on the coefficient
corresponding to X1, i.e., we test the null alternative pair
(3) H0 : β1 = 0 versus HA : β1 6= 0.
To run the hypothesis testing procedure, we use the t-statistic
(4) t = ˆβ1
SE( ˆβ1) ,
where ˆβ1 is the second element of the least squares estimator ˆβ= (XT X)−1XT Y and
SE( ˆβ1) is the standard error of ˆβ1. The least squares estimates, estimated standard errors,
t-statistics and p-values for all coefficients β0,β1,β2,β3 are nicely organized in the standard
linear regression output displayed in Table 1. To get this output in R, use the summary()
function on your model.
Test the manager’s claim in (3) using the R functions lm() and summary().
