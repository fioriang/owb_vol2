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

   - placebo_state_2006_2018_1_excl0_no_sup.csv through placebo_state_2006_2018_5_excl0_no_sup.cs (the number after the year 2018 signifies the placebo_seed: we run the script for placebo_seed=1:5)
   
B) placebo_06_22_23.R this file is for specification number 2. It produces the following csvs: 

   We run this file 5 times for 5 different seeds for the placebo tests. It produces the following files: 
   
   - placebo_state_2006_2022_1_excl0_no_sup.csv through placebo_state_2006_2022_5_excl0_no_sup.csv (these represent the specification that excludes no years)
   
   - placebo_state_2006_2022_1_excl2020_no_sup.csv through placebo_state_2006_2022_5_excl2020_no_sup.csv (these represent the specification that excludes 2020)
   
   - placebo_state_2006_2022_1_excl2021_no_sup.csv through placebo_state_2006_2022_5_excl2021_no_sup.csv (these represent the specification that excludes 2020--2021)
   
   And then we run this file another 5 times for 5 different seeds for the placebo tests but we change the parameter year_cutoff to 2023. It produces the following files: 

   - placebo_state_2006_2023_1_excl0_no_sup.csv through placebo_state_2006_2023_5_excl0_no_sup.csv (these represent the specification that excludes no years)
   
   - placebo_state_2006_2023_1_excl2020_no_sup.csv through placebo_state_2006_2023_5_excl2020_no_sup.csv (these represent the specification that excludes 2020)
   
   - placebo_state_2006_2023_1_excl2021_no_sup.csv through placebo_state_2006_2023_5_excl2021_no_sup.csv (these represent the specification that excludes 2020--2021)

C) placebo_10_22_23.R this file is for specification number 3. It produces the following csvs: 

   We run this file 5 times for 5 different seeds for the placebo tests. It produces the following files: 
   
   - placebo_state_2010_2022_1_excl0_no_sup.csv through placebo_state_2010_2022_5_excl0_no_sup.csv (these represent the specification that excludes no years)
   
   - placebo_state_2010_2022_1_excl2020_no_sup.csv through placebo_state_2010_2022_5_excl2020_no_sup.csv (these represent the specification that excludes 2020)
   
   - placebo_state_2010_2022_1_excl2021_no_sup.csv through placebo_state_2010_2022_5_excl2021_no_sup.csv (these represent the specification that excludes 2020--2021)
   
   And then we run this file another 5 times for 5 different seeds for the placebo tests but we change the parameter year_cutoff to 2023. It produces the following files: 

   - placebo_state_2010_2023_1_excl0_no_sup.csv through placebo_state_2010_2023_5_excl0_no_sup.csv (these represent the specification that excludes no years)
   
   - placebo_state_2010_2023_1_excl2020_no_sup.csv through placebo_state_2010_2023_5_excl2020_no_sup.csv (these represent the specification that excludes 2020)
   
   - placebo_state_2010_2023_1_excl2021_no_sup.csv through placebo_state_2010_2023_5_excl2021_no_sup.csv (these represent the specification that excludes 2020 and 2021)


### Actual Effects 

We have 2 files: one for the extension one for the new states. These files are well commented they basically include two main functions: 

1) all_results_function: this creates two main files the xy_plot_data_donors that essentially includes the time series for the actual and synthetic state and the bt_with_power_data which is a tibble that inlcudes the ATT, the power, the expected effects and is used to produce the right side of the main figures 
2) save_values_function: this saves all the values that we need for the write up. For example, it saves all the ATTs (both the actual and the absolute values), it saves all the p values, the chosen donors etc. 

They also include a section named "Plots and tables" and is where the main plots of the paper are produced

There are some differences between these two files (see the code for more details)  

A) xy_new_data_all.R (Apart from the above this file also includes one additional section "Robustness Check for CT, VT" where we re-run the analysis for the alternative input data for CT and VT) 
B) xy_new_data_all_new_states.R (Apart from the above this file also includes one additional section "CA check" where we assume that CA's ban went into effect in Jan. 2022. We include this ban in the recent bans and run the analysis in the 2010-2022 and 2010-2023 horizon)

#### Robustness checks of different input data 
This is included in section "Robustness Check for CT, VT" of xy_new_data_all.R
#### Monte Carlo estimates
Basically we re-run the full analysis 100 times for the five different placebo seeds. (There is one such section in xy_new_data_all.R and one in xy_new_data_all_new_states.R.)
This shows us (1) how much our ATT estimates change holding |S| fixed and (2) how much |S| might change (which might bring even larger changes to the ATT)
