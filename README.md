# EXP 1 : Linear and Circular Convolution

## AIM: 

To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 

// Linear Convolution
clc;

clear;

x = [1 2 3 4];

h = [2 4 8 6];

m = length(x);

n = length(h);

a=0:1:m-1;

b=0:1:n-1;

subplot(3,1,1);

plot2d3(a,x);

xlabel('Time');

ylabel('Amplitude');

title('Graphical Representation of Input Signal X');

subplot(3,1,2);

plot2d3(b,h);

xlabel('Time');

ylabel('Amplitude');

title('Graphical Representation of Impulse Signal h');

for i = 1: n+m-1

conv_sum = 0;

for j = 1:i

if (((i-j+1) <= n)&(j <=m))

conv_sum = conv_sum + x(j)*h(i-j+1);

end;

y(i) = conv_sum;

end;

end;

disp(y,'Convolution Sum using Direct Formula Method = ')

subplot(3,1,3);

plot2d3(y)

title('Graphical Representation of output Signal y');


## PROGRAM (Circular Convolution): 

// Circular Convolution

clc;

clear;

x=[1 2 3 4];

n1=0:1:length(x)-1;

subplot(3,1,1);

plot2d3(n1,x);

xlabel('time');

ylabel('amplitude');

title('input sequence');

h=[2 4 8 6];

n2=0:1:length(h)-1;

subplot(3,1,2);

plot2d3(n2,h);

xlabel('time');

ylabel('amplitude');

title('impulse sequence');

N1=length(x);

N2=length(h);

N=max(N1,N2);

N3=N1-N2;

if(N3>0)

h=[h,zeros(1,N3)];

else

x=[x,zeros(1,abs(N3))];

end

disp(x)

disp(h)

for n=1:N

y(n)=0;

for i=1:N

j=n-i+1;

if(j<=0)

j=N+j;

end

y(n)=y(n)+x(i)*h(j);

end

end

disp(y)

n=0:N-1;

subplot(3,1,3);

plot2d3(n,y);

xlabel('time');

ylabel('amplitude');

title('circular convolution');

## OUTPUT (Linear Convolution): 
<img width="900" height="1600" alt="WhatsApp Image 2026-11-10 at 11 50 53" src="https://github.com/user-attachments/assets/d125014a-d0a2-40a7-bae2-8b41efab22e4" />


## OUTPUT (Circular Convolution): 
<img width="900" height="1600" alt="WhatsApp Image 2026-11-10 at 11 51 00" src="https://github.com/user-attachments/assets/a26143ac-5e47-4cbd-962d-2d0f3ea78ab4" />


## RESULT: 
<img width="1390" height="1600" alt="WhatsApp Image 2026-11-10 at 11 51 12" src="https://github.com/user-attachments/assets/5d3b26ee-3348-45cc-8c92-6f94dbe7e077" />
