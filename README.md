# Transmutation-ITER
Calculations of transmutation rate for different elements

### Transmutation reaction rate

To calculate the transmutation reaction rate one needs to know the number of nuclei per cm^3, the neutron flux and cross-section of the transmutation reaction, so that:

$R[cm^{-3} s^{-1}] = N[cm^{-3}] \times \sigma[cm^2] \times \Phi[cm^{-2} s^{-1}]$

And if one accounts for the thickness $\delta$, surface area of the first wall $A_{FW}$ and full power year $t_{fpy}$. 

$N_R = N[cm^{-3}] \times \sigma[cm^2] \times \Phi[cm^{-2} s^{-1}] \times A_{FW}[cm^2] \times \delta[cm] \times t_{fpy}[s]$

With this, multiplying by the total volume of the first wall layer, whether that'd be a coating or bulk, we obtain the number of reactions per second. Then, multiplying by the fpy in seconds, one can calculate the number of transmutation reactions per full power year. Assuming a wall made of 100% of the material of study, we can compare the number of new transmutated atoms with the number of original atoms and compare how many of the original atoms transmutated. There are two transmutation reaction values, the first being associated with total transmutation rate, including isotopes, the second and more important is the number of new atoms.

Some important concepts that this code misses are:

- No transportation code, assumes a constant flux at the wall based on the DT campaign at full power.
- Assumes constant thickness of the wall throught its surface area.
- Each neutron that penetrates the wall has always the same probability, the sum of each probabilty of each reaction along the thickness.
- There's no dynamic calculations, this is, accounting for the new nuclei as they are formed.

These first three parameters can overstimate the number of reactions. In general, the probability of the reaction (cross-section) is quite low, but multiplied by the high flux, it reaches significant values. The same neutron can only have one reaction (of the ones considered, since scattering is not included). Therefore, generally, this code overestimates the total transmutation rate that includes isotopes but is quite good for the estimation of the transmutation rate that changes the atomic number. The last parameter is harder to account for.
