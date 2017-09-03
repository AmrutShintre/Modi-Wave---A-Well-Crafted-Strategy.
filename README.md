# Modi-Wave---A-Well-Crafted-Strategy.
Capstone Project


# Positive Factors:-
## Our dependent variable (Labels) is:
* Y: 1 if voted for Modi
* Y: 0 if voted for others

## Independent Variable (Features) is:
* X1: Efficiency
* X2: Marketing
* X3: Personality
* X4: UPA2 Bad Governance
* X5: Selecting efficient candidate for polls
* X6: Performance as a CM
* X7: Struggle from Chaiwala to PM


# Negative Factors:-
## Our dependent variable (Labels) is:
* Y: 1 if voted for Modi
* Y: 0 if voted for others

## Independent Variable (Features) is:
* X1: Terrorism
* X2: Gujarat riots
* X3: Negligence of Poor
* X4: Powerful Image
* X5: relations with specific people
* X6: allegations against UPA-2
* X7: Division of India
* X8: Media transparency
* X9: Muslim Topi case
* X10: Gatbandan situation
* X11: Overemphasis of Gujarat Development
* X12: senior leaders of BJP


# SAS Codes:-
## 1) Chi-Square Analysis -
```
proc  FREQ data=data-nr;
Tables Y *X/All;
run;
```

## 2) Logistic Regression -
###### a) Positive factors for voters:-
```
proc logistic data=nr descending ;
model Y=X1 X2 X3 X4 X5 X6 X7;
selection = stepwise
slstay = 0.2
ctable
lackfit
risklimits;
output out=predic  p=phat  reschi=resi;
run ;
```

###### b) Positive factors for non-voters:-
```
proc logistic data=nr descending ;
model Y=X1 X2 X3 X4 X5 X6 X7;
selection = stepwise
slstay = 0.2
ctable
lackfit
risklimits;
output out=predic  p=phat  reschi=resi;
run ;
```

###### c) Negative factors for voters:-
```
proc logistic data=nr descending ;
model Y=X1 X2 X3 X4 X5 X6 X7 X8 X9 X10 X11 X12;
selection = stepwise
slstay = 0.2
ctable
lackfit
risklimits;
output out=predic  p=phat  reschi=resi;
run ;
```

###### d) Negative factors for non-voters:-
```
proc logistic data=nr descending ;
model Y=X1 X2 X3 X4 X5 X6 X7 X8 X9 X10 X11 X12;
selection = stepwise
slstay = 0.2
ctable
lackfit
risklimits;
output out=predic  p=phat  reschi=resi;
run ;
```
