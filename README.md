# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
~~~
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha= (M -1)/2 // Center Value
for n = 1:M
          if (n ==alpha+1)
          hd(n) = Wc/ %pi ;
          else
          hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);
          end
end

// Rectangular Window
for n = 1:M
W(n) = 1;
end

//Windowing filter coefficients
h = hd.*W;
disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR LPF using Rectangular Window ')

hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR LPF using Rectangular Window');

~~~


# OUTPUT
## CONSOLE

<img width="629" height="436" alt="image" src="https://github.com/user-attachments/assets/10f1e1ca-56a9-4d47-bdfd-acd5608004bf" />

## OUTPUT GRAPH

<img width="1408" height="694" alt="image" src="https://github.com/user-attachments/assets/8643c032-0500-4743-9803-4f68b447e5be" />


# RESULT
Thus design of low pass FIR digital filter waveforms were plotted and output was
verified.
