# 🦄Causal Inference and Supervised Learning Methods on 2018 Democratic Primary Elections  

**By Aileen Wu, Nikki Iyer, Carlos Gonzalez, and Sara Tetsu**

_Special thanks to Dominic Liu, without whom, none of this would have been possible._





![IMG_8188](https://github.com/tetsu2001/102-project/assets/98058378/6e7ed604-b019-4ea7-a8ba-373404783c3c)

## About the Data
- The dataset used in our research, ```house.csv``` is an original dataset put together by Aileen Wu and Sara Tetsu. 

- The dataset contains information on candidates who ran in the Democratic Primary Elections for the House of Representatives in 2018. The 632 candidates in our dataset are those who ran in races where the incumbent was not seeking re-election, and were also running unopposed in the primary election (had at least one opponent).
- Data in this dataset were gathered from three sources:
  1. FiveThirtyEight, an American media company now owned by the American Broadcasting Coompany (ABC). 
  2. the Brookings Institute, an independent nonprofit research institution in Washington D.C.
  3. the Federal Elections Commission (FEC), an independent government agency. 

## Column Descriptions

Column | Description 
-------|--------------
`Candidate` | Name of candidate. Supplied by Ballotpedia.
`State` | The state in which the candidate ran. Supplied by Ballotpedia.
`District` | The office and, if applicable, congressional district number for which the candidate ran. Supplied by Ballotpedia.
`Race Primary Election Date` | The date on which the primary was held. Supplied by Ballotpedia.
`General Status` | “On the Ballot” if the candidate won the primary or runoff and has advanced to November; otherwise, “None.” Supplied by Ballotpedia.
`Primary %` | The percentage of the vote received by the candidate in his or her primary. In states that hold runoff elections, we looked only at the first round (the regular primary). In states that hold all-party primaries (e.g., California), a candidate’s primary percentage is the percentage of the total Democratic vote they received. Unopposed candidates and candidates nominated by convention (not primary) are given a primary percentage of 100 but were excluded from our analysis involving vote share. Numbers come from official results posted by the secretary of state or local elections authority; if those were unavailable, we used unofficial election results from the New York Times.
`Partisan Lean` | The FiveThirtyEight partisan lean of the district or state in which the election was held. Partisan leans are calculated by finding the average difference between how a state or district voted in the past two presidential elections and how the country voted overall, with 2016 results weighted 75 percent and 2012 results weighted 25 percent.
`Race` | “White” if we identified the candidate as non-Hispanic white; “Nonwhite” if we identified the candidate as Hispanic and/or any nonwhite race; blank if we could not identify the candidate’s race or ethnicity. To determine race and ethnicity, we checked each candidate’s website to see if he or she identified as a certain race. If not, we spent no more than two minutes searching online news reports for references to the candidate’s race.
`Veteran?` | If the candidate’s website says that he or she served in the armed forces, we put “Yes.” If the website is silent on the subject (or explicitly says he or she didn’t serve), we put “No.” If the field was left blank, no website was available.
`LGBTQ?` | If the candidate’s website says that he or she is LGBTQ (including indirect references like to a same-sex partner), we put “Yes.” If the website is silent on the subject (or explicitly says he or she is straight), we put “No.” If the field was left blank, no website was available.
`Elected Official?` | We used Ballotpedia, VoteSmart and news reports to research whether the candidate had ever held elected office before, at any level. We put “Yes” if the candidate has held elected office before and “No” if not. 
`Self-Funder?` | We used Federal Election Committee fundraising data (for federal candidates) and state campaign-finance data (for gubernatorial candidates) to look up how much each candidate had invested in his or her own campaign, through either donations or loans. We put “Yes” if the candidate donated or loaned a cumulative $400,000 or more to his or her own campaign before the primary and “No” for all other candidates.
`STEM?` | If the candidate identifies on his or her website that he or she has a background in the fields of science, technology, engineering or mathematics, we put “Yes.” If not, we put “No.” If the field was left blank, no website was available.
`Obama Alum?` | We put “Yes” if the candidate mentions working for the Obama administration or campaign on his or her website, or if the candidate shows up on this list of Obama administration members and campaign hands running for office. If not, we put “No.”
`Dem Party Support?` | “Yes” if the candidate was placed on the DCCC’s Red to Blue list before the primary, was endorsed by the DSCC before the primary, or if the DSCC/DCCC aired pre-primary ads in support of the candidate. (Note: according to the DGA’s press secretary, the DGA does not get involved in primaries.) “No” if the candidate is running against someone for whom one of the above things is true, or if one of those groups specifically anti-endorsed or spent money to attack the candidate. If those groups simply did not weigh in on the race, we left the cell blank.
`Emily Endorsed?` | “Yes” if the candidate was endorsed by Emily’s List before the primary. “No” if the candidate is running against an Emily-endorsed candidate or if Emily’s List specifically anti-endorsed or spent money to attack the candidate. If Emily’s List simply did not weigh in on the race, we left the cell blank.
`Gun Sense Candidate?` | “Yes” if the candidate received the Gun Sense Candidate Distinction from Moms Demand Action/Everytown for Gun Safety before the primary, according to media reports or the candidate’s website. “No” if the candidate is running against an candidate with the distinction. If Moms Demand Action simply did not weigh in on the race, we left the cell blank.
`Biden Endorsed?` | “Yes” if the candidate was endorsed by Joe Biden before the primary. “No” if the candidate is running against a Biden-endorsed candidate or if Biden specifically anti-endorsed the candidate. If Biden simply did not weigh in on the race, we left the cell blank.
`Warren Endorsed?` | “Yes” if the candidate was endorsed by Elizabeth Warren before the primary. “No” if the candidate is running against a Warren-endorsed candidate or if Warren specifically anti-endorsed the candidate. If Warren simply did not weigh in on the race, we left the cell blank.
`Sanders Endorsed?` | “Yes” if the candidate was endorsed by Bernie Sanders before the primary. “No” if the candidate is running against a Sanders-endorsed candidate or if Sanders specifically anti-endorsed the candidate. If Sanders simply did not weigh in on the race, we left the cell blank.
`Our Revolution Endorsed?` | “Yes” if the candidate was endorsed by Our Revolution before the primary, according to the Our Revolution website. “No” if the candidate is running against an Our Revolution-endorsed candidate or if Our Revolution specifically anti-endorsed or spent money to attack the candidate. If Our Revolution simply did not weigh in on the race, we left the cell blank.
`Justice Dems Endorsed?` | “Yes” if the candidate was endorsed by Justice Democrats before the primary, according to the Justice Democrats website, candidate website or news reports. “No” if the candidate is running against a Justice Democrats-endorsed candidate or if Justice Democrats specifically anti-endorsed or spent money to attack the candidate. If Justice Democrats simply did not weigh in on the race, we left the cell blank.
`PCCC Endorsed?` | “Yes” if the candidate was endorsed by the Progressive Change Campaign Committee before the primary, according to the PCCC website, candidate website or news reports. “No” if the candidate is running against a PCCC-endorsed candidate or if the PCCC specifically anti-endorsed or spent money to attack the candidate. If the PCCC simply did not weigh in on the race, we left the cell blank.
`Indivisible Endorsed?` | “Yes” if the candidate was endorsed by Indivisible before the primary, according to the Indivisible website, candidate website or news reports. “No” if the candidate is running against an Indivisible-endorsed candidate or if Indivisible specifically anti-endorsed or spent money to attack the candidate. If Indivisible simply did not weigh in on the race, we left the cell blank.
`WFP Endorsed?` | “Yes” if the candidate was endorsed by the Working Families Party before the primary, according to the WFP website, candidate website or news reports. “No” if the candidate is running against a WFP-endorsed candidate or if the WFP specifically anti-endorsed or spent money to attack the candidate. If the WFP simply did not weigh in on the race, we left the cell blank.
`VoteVets Endorsed?` | “Yes” if the candidate was endorsed by VoteVets before the primary, according to the VoteVets website, candidate website or news reports. “No” if the candidate is running against a VoteVets-endorsed candidate or if VoteVets specifically anti-endorsed or spent money to attack the candidate. If VoteVets simply did not weigh in on the race, we left the cell blank.
`No Labels Support?` | “Yes” if a No Labels-affiliated group (Citizens for a Strong America Inc., Forward Not Back, Govern or Go Home, United for Progress Inc. or United Together) spent money in support of the candidate in the primary. “No” if the candidate is running against an candidate supported by a No Labels-affiliated group or if a No Labels-affiliated group specifically anti-endorsed or spent money to attack the candidate. If No Labels simply did not weigh in on the race, we left the cell blank.
