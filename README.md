# Debate Tournament

I built 

## Purpose & Functionality

The tournament I was running used paper ballots, so the biggest challenge was being able to efficiently output ballots for judges that contained all of the student names, and after the rounds input the information on the ballots so rankings could be calculated. Existing online tabulation software could not do this in a way that would allow me to run an efficient tournament. 

The debate tournament was relatively simple to set up. With only 14 teams entered, each team is assigned a code and then random matchups are created with checks to ensure the pairs of teams aren't from the same school or the same matchup has already been scheduled. 

The speech tournament was a bit more complicated. Because events were scheduled simultaneously, it was important to have students entered in two events happening at the same time would be scheduled to go earlier in one and later in another. Additionally, when entering rankings, I needed an efficient way to input the results from the paper ballots. Both of these problems were solved by assigning students codes. A student's code in a given event was incremented or decremented based on their presence in other simultaneous events, allowing each room assignment to be sorted. Then, to input results, the codes simply needed to be entered in order of the ranking on the ballot, which was much less error-prone than using names. 

## Files
`Panel/debate.ipynb` - Jupyter Notebook with debate methods. 

`Panel/codes.txt` - Maps team codes to last name triples

`Panel/prelims.txt` - Output file from running debate script, contains all of the matchups in the preliminary rounds

`Panel/panel.csv` - Contains all the teams entered in the debate tournament. Student names are random concatenations of popular baby names from 1880.

`Speech/roster.csv` - Contains student names and the events they are entered in. Student names are random concatenations of popular baby names from 1880.

`Speech/speech.ipynb` - Jupyter Notebook with speech methods. 

`Speech/*_mb.docx` - Ballot template for each speech event. The create_master_ballot call modifies this template and writes a new word doc with the student names, round and room number filled in. 

### Next Steps

This project was designed to fit the precise needs of the specific tournament I was running. Future modifications will be made to make the functions generalize better. Additionally, the scheme for finding semifinalists could be implemented better, which will include adding a way to break ties in student ranks. This will likely require a different way of storing results. Finally, for the debate tournament, currently matchups are found using randomness and ensuring there aren't repeat or intra-school matchups. This would be better modelled as a constraint satisfaction problem where the most constrained team is assigned a matchup first. 
