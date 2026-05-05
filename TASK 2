data lungcancer_deaths;
set '/home/u64361286/mm424/MYDATA/lungcancer.sas7bdat';
run;
data population;
set '/home/u64361286/mm424/MYDATA/population.sas7bdat';
run;
proc sort data=lungcancer_deaths;
by county;
run;
proc sort data=population;
by county;
run;
data merged;
merge lungcancer_deaths (in=a) population (in=b);
if a then output;
run;
proc print data=merged;
run;
data new_merged;
set merged;
total_deaths = deaths1+deaths2+deaths3+deaths4;
total_population= pop1+pop2+pop3+pop4;
run;
proc sql;
 create table final as 
 select 
 county,
 total_deaths,
 total_population,
 (total_deaths/total_population)*100  as death_ratio format=8.2

 from  work.new_merged;
 quit;
 data ratio_data;
 set ratio_data;
 label death_ratio='mortality rate from lungcancer in male';
 run;
 proc print data=final;
 run;
 
 

