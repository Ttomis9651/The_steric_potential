# The_steric_potential
The steric potential in paper "on the design of precision nanomedicin"
%%
% this is for the steric potential from the glycocalyx
% consider only the osmotic pressure component
% The result is not correct, so I want to know the correct result

% parameters
[detaG,R]=meshgrid(0:0.02:1,10:5:100);
R=R*10^-9;                   % the radius of the particle  10-100nm
dS=20*10^-9;                 % the interchain distance between two sydencans each bearing 6 chain  
sigmaHS=(pi*dS^2)/24;        % area of per chain (e.i the density of the chain?)

% formulations
a=4*pi*R.^3;                 % the volume of the particles
b=(1-detaG.^2).^(9/4);       % I don't know what this is from
c=3*sigmaHS^(3/2);
betaUG=(a.*b)/c;

% plot settings
surf(detaG,R,betaUG);        % plot the surface
set(gca,'YScale','log')      % code to get the Logarithmic Coordinate
set(gca,'ZScale','log')
view(50,20);                 % change the view angle   view(az,el)
axis([ 0 1  1*10^-8 100*10^-9 50 12000]);   % set the limitation of all axes
