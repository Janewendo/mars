The latest files. May 5, 2026
0.01mh_earth
0.01mh_mars


0.01mh_earth:

This models a 1D column, 30cm high, 13.5 cm wide
Basalt and perchlorate compose the solid. Perchlorate is 1% of total soild by volume, roughtly by mass.
The main boundary condition is, the inject water on top is in 0.01m/h. 
The general boundary and inital conditons are shown in the boundary_inital_conditons.png
The total injected time is 100 day. The goal is to remove the perchlrorate solide and brings the largest concentration of perchlorate in the soil column to be below 20ug/L.

  What 0.01mh_earth is doing:                                                                                
                                                                                                             
  - It is a 1D vertical column with NXYZ 1 1 100                                                                                          
  - Water infiltrates from the top at: LIQUID_FLUX 1.d-2 m/h                                                                                                          
  - The column is initialized with a very perchlorate-rich dissolved phase plus perchlorate minerals:        
      - initial dissolved Mg++ = 8 M, Ca++ = 8 M, ClO4- = 16 M                                                                                                             
      - solid Mg(ClO4)2(s) and Ca(ClO4)2(s) are also present                                                                                                 
  - Those minerals are kinetically active:                                                                   
      - RATE_CONSTANT -5.0 for both perchlorate salts                                                                                                         
  - So physically the case is:                                                                               
      - infiltration through a dry porous column                                                             
      - dissolution/reprecipitation and transport of perchlorate salts                                       
      - under Earth pressure and 25 C                                                                        
                                                                                                             
 “Earth”:                                                                                                            
  - top and initial gas pressure:                                                                            
      - 101325 Pa                                                                                                                                              
  - temperature:                                                                                             
      - 25 C                                                                                                                                                 
  - Earth-like liquid/gas properties:                                                                        
      - liquid viscosity 8.90e-4 Pa s                                                                        
      - gas density ideal, gas viscosity 1.86e-5 Pa s                                                                                                                    
  - Earth dissolved atmospheric gases:                                                                       
      - CO2(aq) 4.054e-4                                                                                     
      - O2(aq) 0.2                                                                                           
                                                                                                             


0.01mh_mars:                                                           
 
  - same grid: 1 x 1 x 100                                                                                   
  - same infiltration flux: 0.01 m/h                                                                         
  - same mineral loadings for Mg(ClO4)2(s) and Ca(ClO4)2(s)                                                  
  - same perchlorate mineral kinetic rate constants                                                          
  - same initial liquid saturation 0.01                                                                      
  - same residual saturation 0.001                                                                           
  - same solver controls                                                                                     
                                                                                                             
 “Mars”:                                                                            
  - lower gravity:                                                                                           
      - GRAVITY ... -3.71                                                                                                                 
  - much thinner atmosphere:                                                                                 
      - GAS_PRESSURE 600 Pa                                                                                                              
  - colder:                                                                                                  
      - TEMPERATURE -20                                                                                                                     
  - different fluid properties:                                                                              
      - liquid is denser and more viscous in Mars case                                                       
      - gas is much lower density  
	  - liquid viscosity 2.0d-3 Pa s                                                                        
      - gas density 0.013d0, gas viscosity 1.3d-5 Pa s   
  - different atmospheric dissolved gases:                                                                   
      - much more CO2(aq), much less O2(aq) 
	  - CO2(aq) 5.7d-3                                                                                    
      - O2(aq) 1.0d-5   	  
  - lower initial dissolved perchlorate brine:                                                               
      - Mars starts with Mg++ = 5 M, Ca++ = 5 M, ClO4- = 10 M                                                                                                              
                                                                
                                                                                                           