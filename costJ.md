function [ J ] = costJ( x,y,theta )
%UNTITLED3 Summary of this function goes here
%   Detailed explanation goes here
    m = size(x,1);
    prediction = x * theta;
    errors = (prediction - y).^2;
    J = 1/(2*m) * sum(errors);
end

x = [1 1;1 2;1 3]
y = [1;2;3]
theta[0;1]
costJ( x,y,theta ) %调用




%logistic回归
function [ jVal,gradient ] = costFunction( theta )
%UNTITLED Summary of this function goes here
%   Detailed explanation goes here
    jVal = (theta(1) - 5)^2 + (theta(2) - 5)^2;
    gradient = zeros(2,1);
    gradient(1) = (theta(1) - 5) * 2;
    gradient(2) = (theta(2) - 5) * 2; 
end

options = optimset('GradObj','on','MaxIter',100);
initialTheta = zeros(2,1)
 [optTheta,functionVal,exitFlag] = fminunc(@costFunction,initialTheta,options)
