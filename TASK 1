/*quistion 1 part a*/
data patients;
infile datalines delimiter=',';
input name $ admission discharge dementia funding;
duration=discharge-admission;
label duration='length of stay';
datalines;
Lauren,1997,2011,1,0
Toby,2003,2008,0,1
Jason,1996,2008,1,1
Terry,2005,2012,0,1
Sally,2004,2011,0,0
Liam,1999,2012,1,1
Sarah,2001,2012,1,0
;
run;
/*quistion 1 part b*/
proc print data=patients;
run;
/*quistion 1 partc*/
proc format;
    value dementia
    1="yes"
    0="no";
     run;
/*quistion 1 part d*/
proc format;
  value funding
  1="private"
  0="nhs";
  run;
/*quistion 1 part e*/
proc sgplot;
histogram duration;
run;

/* quistion 1 part g*/
data year_admission;
set patients;
if admission > 2000 then year_admission="after 2000";
else year_admission="before 2000";
run;

/* quistion 1 part h*/

proc means data=patients maxdec=1;
var duration;
run;

/* quistion 1 part i */

proc freq data=year_admission;
tables year_admission;
run;
proc freq data=patients;
tables funding dementia;
run;


/* quistion 1 part j*/

proc freq data=year_admission;
tables year_admission * funding/nopercent;
run;
/*quistion 1 part k*/
proc sgplot data=patients;
vbox duration/ category=funding;
run;
  
