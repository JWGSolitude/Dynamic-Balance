% program start
clear;
disp('LAB (VI) matlab program.');
disp('Produced by LCH.')
disp('Last update: 2018/05/01');

% test input
% T1=2;
% T2=2;
% M=[0.608 3.6 2.8;0.464 3.76 2.8];
% P=[99.75 -91.08 -78.07;56.39 -91.08 -78.07];

% input by user
fprintf('\nPlease input mass T1 and T2.(g)\n');
T1=input('T1=');
T2=input('T2=');

fprintf('\nPlease input vibration amplitude.(V)\n');
M(1,1)=input('magR10=');
M(2,1)=input('magR20=');
M(1,2)=input('magR11=');
M(2,2)=input('magR21=');
M(1,3)=input('magR12=');
M(2,3)=input('magR22=');

fprintf('\nPlease input vibration phase.(deg)\n');
P(1,1)=input('degR10=');
P(2,1)=input('degR20=');
P(1,2)=input('degR11=');
P(2,2)=input('degR21=');
P(1,3)=input('degR12=');
P(2,3)=input('degR22=');

% program
R=M.*exp(i.*(P*pi/180));
a=[(R(1,2)-R(1,1))/T1 (R(1,3)-R(1,1))/T1;...
    (R(2,2)-R(2,1))/T2 (R(2,3)-R(2,1))/T2]

if abs(det(a))<1e-3
    %situation about the sigular point of a
    disp('Matrix a cannot inverse. Program end.');
else
W=-a\[R(1,1);R(2,1)];

% display
magW=abs(W);
degW=atan2(imag(W),real(W))*180/pi;
% use atan2 to ensure the degree not to be weird

fprintf('\nThe balance weight and its location is:\n\n');
fprintf('\tmagW1=%.2f(g) degW1=%.2f\n\tmagW2=%.2f(g) degW2=%.2f\n\n',...
    magW(1),degW(1),magW(2),degW(2));
disp('Program end.');
end
