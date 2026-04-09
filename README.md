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
clc; % clear screen
clear all;
close all;

wc = input('enter the value of cut off frequency: ');
N = input('enter the value of filter: ');

alpha = (N-1)/2;
eps = 0.001;

% High Pass Filter Coefficient
n = 0:1:N-1;

hd = -sin(wc*(n-alpha+eps))./(pi*(n-alpha+eps)); % basic HPF formula
hd(alpha+1) = 1 - wc/pi; % correction at center (n = alpha)

% Blackman Window Sequence
wh = 0.42 - 0.5*cos((2*pi*n)/(N-1)) + 0.08*cos((4*pi*n)/(N-1));

hn = hd .* wh;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

plot(w/pi, abs(h), 'blue');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('High Pass Filter using Blackman Window');
grid on;
```

## OUTPUT:
<img width="553" height="503" alt="Screenshot 2026-04-09 195332" src="https://github.com/user-attachments/assets/68f16501-0a20-4c5a-b28e-1819da5c94cb" />


## RESULT:
![R3](https://github.com/user-attachments/assets/0f6a34d7-1829-4bf9-ac49-5292bf357e9e)

