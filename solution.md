```zsh
# Clone the initial repository
git clone git@github.com:eerwitt/command-line-mystery.git
cd command-line-mystery

# Check the status to see if anything is already marked as new (shouldn't be)
git status

# Edit my solution file
subl solution.md

# Commit initial solution
git add solution.md
git commit -a

# Start reading the instructions
less instructions

# Check for clues in the mystery
cd mystery
grep CLUE ./crimescene

# Search for person with the Latte
grep Annabel ./people

# Knock on her door
less streets/Mattapan_Street
# Goto line in file using less: http://stackoverflow.com/questions/8586648/going-to-a-specific-line-number-using-less-in-unix
# in less type 173g
# Try different interviews
less interviews/interview-47246024

less interviews/interview-699607

# Checking for vehicle
less vehicles
# Search in less for vehicles starting with L337 and ending in 9
# in less /L337..9
# Check which are over 6'
# Katie Park
# Mike Bostock
# John Keefe
# Erika Owens
# Matt Waite
# Brian Boyer
# Al Shaw
# Miranda Mulligan
# Joe Germuska
# Jeremy Bowers
# Jacqui Maher

# Check which is male/female and get their names
egrep '((Katie Park)|(Mike Bostock)|(John Keefe)|(Erika Owens)|(Matt Waite)|(Brian Boyer)|(Al Shaw)|(Miranda Mulligan)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1

# Limit down by membership
egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships

# (Jeremy Bowers)|(Brian Boyer)|(Mike Bostock)|(Matt Waite)
# Not MB, wrong car color
# Not MW, wrong car manufacturer
# Not BB, wrong car manufacturer
# JB, it is JB
```

grep -C 3 CLUE crimescene  
*******
Crime Scene Report #912464709392
********
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.


*******
--
--
*******
Crime Scene Report #028615332953
********
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.


*******
--
--
*******
Crime Scene Report #575776622208
********
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

*******
Crime Scene Report #990314688882

 2015-11-16 16:11:59 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master ✓| → grep Annabel people

Annabel Sun	F	26	Hart Place, line 40

Annabel Church	F	38	Buckingham Place, line 179



 2015-11-16 16:47:54 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master U:1 ✗| → grep -C 3 "Annabel" vehicles

--
--
License Plate L2E48EF
Make: BMW
Color: Orange
Owner: Annabel Church
Height: 5'5"
Weight: 201 lbs

--
--
License Plate 0O27BTD
Make: Fiat
Color: Yellow
Owner: Annabel Sun
Height: 5'0"
Weight: 232 lbs

 2015-11-16 17:09:52 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master ↑1 ✓| → head -n 40 streets/Hart_Place | tail -n 1
SEE INTERVIEW #47246024

 2015-11-16 17:09:57 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master ↑1 ✓| → head -n 179 streets/Buckingham_Place | tail -n 1
SEE INTERVIEW #699607
 2015-11-16 17:13:17 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery/interviews
± |master ↑1 U:1 ✗| → cat interview-699607
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

 2015-11-16 17:19:54 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master ↑1 U:1 ✗| → grep -C 3 "L337" vehicles
 2015-11-16 17:19:54 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery/mystery
± |master ↑1 U:1 ✗| → grep -C 3 "L337" vehicles

 2015-11-16 17:47:14 ☆ |ruby-2.2.1| Thomass-MacBook-Air in ~/dev/command-line-mystery
± |master ↑1 U:1 ✗| → grep -A5 "L337" mystery/vehicles 

--
License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
--
