# Digital-Signal-Processing--FIR-LOW-PASS-FILTER-DESIGN
## AIM:
To generate design of low pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Low Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
clc;                
clear all;
close all;

wc = input('Enter the value of cut off frequency: ');
N  = input('Enter the value of filter length: ');

alpha = (N-1)/2;
eps   = 0.001;

% Low Pass Filter Coefficient
n  = 0:1:N-1;
hd = sin(wc*(n-alpha+eps)) ./ (pi*(n-alpha+eps));

% Hamming Window Sequence
wh = 0.54 - 0.46*cos((2*pi*n)/(N-1));

% Final Low Pass Filter
hn = hd .* wh;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'ms');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Low Pass Filter using Hamming Window');
grid on;
```
## OUTPUT:
<img width="696" height="527" alt="image" src="https://github.com/user-attachments/assets/450d97b0-c6fb-4469-8fde-b5f59d655b3c" />


## RESULT:
![WhatsApp Image 2026-04-09 at 10 37 23](https://github.com/user-attachments/assets/65a09c1f-0f2a-442b-a154-83e539794ac5)

