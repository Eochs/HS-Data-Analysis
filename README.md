# Hearthstone Data Analysis

A repository for files to scrape data about Hearthstone, and to run analyses on that data.

## decks.csv
* decks.csv contains information about all the constructed decks on hearthpwn.com/decks that got >= 2 upvotes, and that were updated after the Undertaker nerf, or after the Black Rock Mountain release. 
* There are 2369 decks total. 
* The column names are:
 - 'Class': which tells what character class the deck is; Warlock, Druid, etc.
 - 'Deck Type': tells whether the deck is Control, Aggro, Midrange, etc.
 - 'Rating': gives the number of upvotes minus the number of downvotes the deck got. Every deck has a rating of >= 2.
 - 'Dust': how much the deck would cost to create using the in-game currency 'dust'. Around 1200 dust seems to qualify for a 'budget' deck.
 - 'Updated': The date and time the deck was last updated at the time of scraping. The time was formatted using the datetime.strptime method from the python datetime module. 
 - 'Mana Curve': Is an array of length 8, with the value at index i representing the number of cards in the deck with mana cost i. For example [0,4,6,7,6,4,2,1] has 0 cards of mana cost zero, 4 cards of mana cost one, 6 cards of mana cost two, etc.
 - The rest of the columns are names of a card, and each row will have a count of how many of that card are in the deck. Values can be 0, 1, or 2.
* Use pandas.DataFrame.from_csv('decks.csv') to import into a dataframe. 


## CreateDecks.csv
* Scrapes data from hearthpwn.com to populate decks.csv
