# Design, not time, limits the effectiveness of food‑waste bans
All the code and descriptions for the extension of OWB

## Data 

## Code

### Data

The main file is called load_the_data.RMD it has its own descriptions. 

A few points: 

1) In VT's data and in CT's data there are 2 alternative inputs (these are also discussed in the paper).
   To check the estimates of the bans using these alternative data, go to  line 3188 and first comment out the three lines under baseline and un-comment the 7 lines below rob check.
   Then, go to line 4152 and comment out the baseline and uncomment the rob check 
   Finally, on the "save the data section" uncomment the relevant lines 
2)  Section "Additional supplements of missing data" adds imports and exports from OH and NY assuming similar fractions as for the following years. We ended up not supplementing the data, because we do not know the patterns of the past.
    However, the results of the paper remain if these sections are in included. 

### Expected effects 

### Placebo 

### Actual Effects 

#### Robustness checks of different input data 

#### Monte Carlo estimates
