# Solution-for-a-1D-Steady-State-Diffusion-Equation
The solution for the 1D steady state diffusion equation (i.e. d^2U/dx^2 = 0), on analytically solving, we get the equation of straight line. I proved the same using MATLAB. 



%%Solving the 1D Steady State Diffusion Equation(i.e. d^2U/dx^2 = 0)

%%
close all
clear all
clc

size_of_the_domain = 1;
number_of_nodes = 5;
%number_of_nodes = input("Enter the number of nodes=");
number_of_elements = linspace(1,number_of_nodes,20);
size_of_a_mesh_element = number_of_elements(2)- number_of_elements(1);

%%
%Boundary Conditions
U(1) = 0;
U(number_of_nodes) = 1;

%%
%Initializing Conditions
U_new(1)= 0;
U_new(number_of_nodes) = 1;
error_magnitude = 1;
maximum_error = 1e-07;
iterations = 0;

%%
%Calculations
while(error_magnitude > maximum_error)
        for i = 2 : (number_of_nodes-1)           
            U_new(i) = (U(i+1)+U(i-1))/2;           
            iterations = iterations + 1;
            
            error_magnitude = abs(U_new(i)- U);
            U = U_new;          
        end
        
        
end
display(iterations)
display(U)
display(

%%
% %Visual Representation
figure (1)
plot(U)
axis([1 5 0 1])
xlabel("number of nodes (n)")
ylabel("velocity (U)")
title("1D Steady State Diffusion Equation - The solution obtained is the equation of straight line")


