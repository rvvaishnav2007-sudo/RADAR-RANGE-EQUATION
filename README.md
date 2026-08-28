# RADAR-RANGE-EQUATION
#EXP NO 8 EVALUATION OF RADAR RANGE USING PYTHON

Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:


Procedure
1.	Set Up the Python Environment: Ensure that Python is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2.	Import Necessary Libraries: Import the math library in Python.
3.	Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4.	Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power.
5.	Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6.	Execute the Program: Run the Python script to calculate and display the maximum range of the radar.

PROGRAM
~~~
clc;
clear;
clf;


Gt = 30;
Gr = 30;
lambda = 0.03; 
sigma = 1;
Pr = 1e-12; 

Pt = 1:10:10000;
R = ((Pt .* Gt .* Gr .* lambda^2 .* sigma) ./ ...
    ((4*%pi)^3 .* Pr)).^(1/4);


Pt_dB = 10*log10(Pt);
Pr_dB = 10*log10(Pr);


subplot(2,1,1);
plot( R,Pt_dB);
Pt_const = 1000;
Pr_values = 10.^(-15:1:-9);

R2 = ((Pt_const .* Gt .* Gr .* lambda^2 .* sigma) ./ ...
    ((4*%pi)^3 .* Pr_values)).^(1/4);

Pr_dB_values = 10*log10(Pr_values);

subplot(2,1,2);
plot( R2/1000,Pr_dB_values);

~~~

OUTPUT

<img width="737" height="596" alt="Screenshot 2026-08-28 161521" src="https://github.com/user-attachments/assets/04a6b864-3c10-4dc7-85b9-f82537297a4e" />


TABULR COLUMN
<img width="1600" height="1062" alt="WhatsApp Image 2026-08-28 at 4 17 33 PM" src="https://github.com/user-attachments/assets/2dc01bb8-29bc-4b36-81d8-ad2e415e8d1d" />


Result:

Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Python program.
