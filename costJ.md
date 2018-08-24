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
