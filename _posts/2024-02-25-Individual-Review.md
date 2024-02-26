## Dante's Individual Review
## What I did
- For my actual tangibles for the most recent project I worked on my individual feature, creating a database for all of the clash royale cards, making it so a user's favorite cards get added to a database, admin roles, aswell as some of the login and sign up. For my feature, I worked on displaying the cards from the backend in a way which would look nice. The user then has the ability to favorite any of the cards, but can only have 8 favorited at once. This acts as a form of favoriting cards/deck since the deck in the game can only hold 8 cards. For the databasef for the cards, I used to just use the card data hard coded in my front end, but using a csv file I created a database with all the cards and their unique data. This database would be used for both mine and Ashwin's feature. Next, I connected my front end favoriting code to a completely unique database where the user is able to add cards to the favorited database. Also, I worked heavily on the admin role. The night of our team teach I spent a long time making it so the user's cookie contains their role. Then I made a special page with all of the user data where only users with admin role can view the user database and ordinary users cannot and get hit with an error. Lastly, I worked on small features regarding the sign up and log in. 
## Brief overview of clash royale and features
- Clash royale is a game where the user can collect cards then with their collected cards they can select 8 to form a "deck." With this deck they can then battle others to see who can win. Each card contains a rarity (how hard to obtain), image, and elixir (How much time before you can play it). Features: A deck builder/ card favoriter, a chest opener where you can open chests to collect cards, information about decks and they win rates, a custom deck generator based on survey, and clash royal tourney information. 
## College board requirments
* Instructions for input from one of the following: the user, a device, an online data stream, a file.	
- How I met this requirement: When the user is looking at the grid of cards they can flip the card over by clicking it and they can click teh favorite card button. The favorite card is then added to a unique database for favorited cards. 

Add to deck/ favorite button
<img src="{{site.baseurl}}/images/CBdeck.png" alt="Description of Image">
Favorite card in database
<img src="{{site.baseurl}}/images/CBfdata.png" alt="Description of Image">

* Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the user’s purpose.
- How I met this requirement: For two of features we directly use the database of all the cards that contain the name, level, elixir, rarity, and photo of each card
Database is here:
<img src="{{site.baseurl}}/images/CBcard.png" alt="Description of Image">

* At least one procedure that contributed to the program’s intended purpose where you have defined: the name, return type, one or more parameters.	
- How I met this requirement: This procedure has a name: post, a return: response, added to favorite, and a parameter: user_id and card_id. This is used for for favoriting cards using their card_id for the user's ID
See procedure:
<img src="{{site.baseurl}}/images/CBprocedure.png" alt="Description of Image">

* Calls to your student-developed procedure.	
- How I met this requirement: I met this requirement by using functions such as initcards() and initfavorites(). These are used to display all of the cards and the favorites.

* Instructions for output (tactile, audible, visual, or other) based on input and program functionality.	
- How I met this requirement: I created a container to store all of the favorited cards which are taken from the backend and stored in an array then displayed in a 2 by 4 grid.
See code here: 
<img src="{{site.baseurl}}/images/CBfunction.png" alt="Description of Image">
See output here (N@TM throwback):
<img src="{{site.baseurl}}/images/deck.png" alt="Description of Image">

* An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure	

- How I met this requirement: 
- Sequencing: 
The script starts by declaring variables such as cardData, deck, and savedDecks.

Functions are defined in a sequence loadClashRoyaleCards, addToDeck, removeCardFromDeck,

Initial calls to displayCards() and displaySavedDecks() at the end of the script to initialize the display when the page loads.

- Selection: 

In addToDeck, there's a selection structure to check if a card is already in the deck or if the deck is full before adding a new card.

In removeCardFromDeck, an if statement checks if the card exists in the deck before it's removed.

The sortCards function uses if and else if to decide how to sort the cards based on the criteria and order provided.

In deleteDeck, a confirm dialog is used (which is a form of selection) to confirm the deck deletion.

- Iteration: 

The forEach loop in displayCards that iterates over each card in cardData.items to create and append card elements to the container.

Another forEach loop in displaySavedDecks iterates over each saved deck name to create buttons for opening and deleting decks.

## Video
* Input to program: The user can click the add to deck button in order to favorite the cards
* At least one aspect of functionality of your program: the favorite tab where the users favorited cards are displayed in a 2 by 4 grid
* Output produced by program: The user favorites fards already established in a different database, then the card id and info is stored with the User ID and is then displayed in favorites
* My video is less than 1 minutes, 30mb in size and I do not use narration.

<a href="https://drive.google.com/file/d/1G3QlWPzNot2xnBQAMv9IedKLrnEQ8J5A/view?usp=sharing" title="Link to Video">Click here</a>
