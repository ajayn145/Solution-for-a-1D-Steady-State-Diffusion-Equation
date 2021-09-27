PRE-REQUISITES------->

![image](https://user-images.githubusercontent.com/77200332/134896951-f3fb0fa5-c47d-40d3-9fa7-5561b5d87fd9.png)
![FGFGGGG](https://user-images.githubusercontent.com/77200332/134897422-c747fd76-553e-4cde-8f9d-095ca9300739.png)

MAIN PROGRAM------------>


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

%%
%Code in MATLAB
![image](https://user-images.githubusercontent.com/77200332/134783109-f5505b86-6f17-4232-8ed8-f6805acb8863.png)
![image](https://user-images.githubusercontent.com/77200332/134783120-054a2306-fce9-4e31-b676-fa469c034332.png)


%%
%OUTPUT
![image](https://user-images.githubusercontent.com/77200332/134783018-59799e63-7544-4364-8591-7210842df0b0.png)
![image](https://user-images.githubusercontent.com/77200332/134783030-62f91cbf-a8bb-4df8-8af8-345d169bd9d0.png)

