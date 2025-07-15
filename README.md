# Design, not time, limits the effectiveness of food‑waste bans
All the code and descriptions for the extension of OWB

## Data 

## Code

### Data

The main file is called load_the_data.RMD it has its own descriptions. 

Two points: 

1) In VT's data and in CT's data there are 2 alternative inputs (these are also discussed in the paper).
   To check the estimates of the bans using these alternative data, go to  line 3188 and first comment out the three lines under baseline and un-comment the 7 lines below rob check.
   Then, go to line 4152 and comment out the baseline and uncomment the rob check 
   Finally, on the "save the data section" uncomment the relevant lines 
2) Section "Additional supplements of missing data" adds imports and exports from OH and NY assuming similar fractions as for the following years. We ended up not supplementing the data, because we do not know the patterns of the past.
   However, the results of the paper remain if these sections are in included. 

State-specific notes: 


### Expected effects 
No difference from the OWB. The only things that we add are two WCS: one for NJ and one for NY. 
None of these are statewide WCS and this is the reason we originally did not add them to the OWB 

- NY:

- NJ: 

### Placebo 

We produce the following specifications: 

1) Placebo estimates for the first five implemented bans starting in 2006 and ending in 2018 (with all updates to the data and the code)

3) Placebo estimate for the first five implemented bans starting in 2006 and ending in 2022 and in 2023
   - Not exlcuding any years
   - Excluding 2020
   - Excluding 2020-2021
     
   For this case, the excluded years all fall in the evaluation period (they mainly affect the estimation of ATT not the selection of donors). In principle, the optimal |S| produced by these three could be the same, however the ATTs might change so we might see diffrences in the optimal |S| produced by these three different specficiations
So for each placebo_seed we have 6 files: three for ending year 2022 and three for ending year 2023

4) Placebo estimates for the new bans (three: NJ, NY, MD and one that we do not evaluate WA), starting in 2010 and ending in 2022 and in 2023
   - Not exlcuding any years
   - Excluding 2020
   - Excluding 2020-2021
   
   For this case, the excluded years fall in the validation period (they mainly affect the selection of donors).
So for each placebo_seed we have 6 files: three for ending year 2022 and three for ending year 2023


We have the following files: 

A) placebo_06_18.R: this file is for specification number 1. It produces the following csvs: 

   We run this file 5 times for 5 different seeds for the placebo tests: 
   
    - placebo_state_2006_2018_1_excl0_no_sup.csv -- placebo_state_2006_2018_5_excl0_no_sup.csv (this number after the year 2018 signifies the placebo_seed: we run the script for placebo_seed=1:5)
   
B) placebo_06_22_23.R this file is for specification number 2. It produces the following csvs: 

C) 


### Actual Effects 

We have

#### Robustness checks of different input data 

#### Monte Carlo estimates
