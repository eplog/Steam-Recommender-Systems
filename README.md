# Steam Game Recommendation System ReadMe

Overview: 
I am passionate about video games as they are one of my favorite hobbies, and allow me to connect with friends and relax. 
Thus, I decided to create Steam game to game (labelled Item to Item in notebooks) and user to user collaborative recommender systems. 
I obtained my Steam game and user data (2017) from Kaggle (https://www.kaggle.com/tamber/steam-video-games/version/1). The Steam data consists 
of the following fields: User ID, Game Title and Hours Played.

To start off, I checked the data and noted the data was clean and required no munging. For my next step, I performed 
Exploratory Data Analysis (EDA) to identify trends and highly played games/active users. Pandas, Seaborn and Matplotlib packages
were used to perform EDA on the Steam data.

For my collaborative recommender systems, I used Pandas (dataframes,pivot tables, groupby, etc.), pairwise distance testing several
metrics and StandardScaler to create user to user and game to game recommender systems. I tested several game to game systems, and
filtered the hours played in order to see how the systems changed as a result. There was no one best filter, as certain games performed
better using different filters. For example, when querying Dota 2, the only filter that displayed another Multiplayer Online Battle Arena 
(MOBA) was the filter of greater than 50 hours played. The game displayed was Smite, which actually has a stand alone client in addition
to being on Steam, thus the player base is split and numbers are not representative of the total population. However, Path of Exile 
performed worse when increasing the hours played, as the filter over 50 hours stated the most similar game was a First Person Shooter (FPS). 
The user to user recommender required no filters, and produced using the same methods as the game to game recommender. The metric utilized
for both recommender systems was Spearman's Correlation. I tested a wide variety of metrics (i.e., Euclidean, Hamming, Matching, etc.) and
Spearman's Correlation was the optimal metric. 

Lastly, I tried using a package called svdRec to compare against my manually created recommender systems. The svdRec system solely 
recommended games that were as popular as the game queried, thus I did not investigate further as my manual recommender systems worked
better on the Steam data. The package can be found at: https://github.com/ZWMiller/svdRec.

File Guide:
1) Steam - Item to Item Collaborative Recommendation System with Hours Played Greater than 10: Game to game collaborative recommender
system with hours played filtered to greater than 10.
2) Steam - Item to Item Collaborative Recommendation System with Hours Played Greater than 20: Game to game collaborative recommender
system with hours played filtered to greater than 20.
3) Steam - Item to Item Collaborative Recommendation System with Hours Played Greater than 30: Game to game collaborative recommender
system with hours played filtered to greater than 30.
4) Steam - Item to Item Collaborative Recommendation System with Hours Played Greater than 40: Game to game collaborative recommender
system with hours played filtered to greater than 40.
5) Steam - Item to Item Collaborative Recommendation System with Hours Played Greater than 50: Game to game collaborative recommender
system with hours played filtered to greater than 50.
6) Steam - Item to Item Collaborative Recommendation System: Item to Item Collaborative Recommendation System with no filters applied
7) Steam - svdRec Recommender System: Package used to create a collaborative recommender system. Only tested game to game. 
8) Steam EDA: Exploratory Data Analysis performed on the Steam data.
9) steam_data.csv: Original Steam data acquired from Kaggle.
10) steam_data_w_game_id.csv: Steam Data with a modified Game ID column created by using Pandas .ngroup(). Used in svdRec recommender.
11) steam_data_wo_game_title.csv: Steam data without game title as a feature, used in svdRec recommender.

Next Steps:
1) Acquire more data via the Steam Web API such as game rating, game details and more user data to bolster the recommender systems.
2) Use the newly acquired data from the Steam  Web API as a test set, to test my recommender systems. 
3) Test more filters and utilize clustering to improve upon the recommender systems. 