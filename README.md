### Project Proposal: MBTI Personalities & Their Effect on Music Taste

**Background:** <br></br>
The Myers-Briggs Type Indicator (MBTI) is a popular method for identifying personality types, dividing people into 16 distinct categories based on 4 dimensions: Extraversion versus Introversion (E/I), Sensing versus Intuition (S/N), Thinking versus Feeling (T/F) and Judging versus Perceiving (J/P). The MBTI helps shed light on people’s behavior, how people make decisions, and preferences in various life aspects, including music. Music significantly influences personal identity and expression, and research indicates that personality traits may shape one's musical tastes. 

**Previous Work:** <br></br>
The paper “Music Preference Correlates of Jungian Types” seeks to find correlations between MBTI personality types and music preferences, utilizing traditional statistical methods. The survey included respondents taking the MBTI test as well as ranking music categories on a scale. Through clustering and regression analysis on categories of music such as jazz/soul/folk, classical, and pop, researchers found results based on the individual aspects of MBTI. For example, People ranking higher in intuition in MBTI liked a broader range of music and had a particular preference for jazz, soul, folk, and classical music. (Pearson & Dollinger, 2003)
	We plan on expanding on the idea of this paper through the use of Spotify data. We are able to extract song data such as danceability, energy, loudness, and others as features to fit a regression or classification model. One aspect that our dataset doesn’t have is a concrete set of music genres for each song because of our current data format, but the research by Pearson & Dollinger highlights how different genres can be meaningful features for finding correlations between music preferences and personality traits.
	The paper “Controlling Spotify Recommendations: Effects of Personal Characteristics on Music Recommender User Interfaces” seeks to uncover the algorithm behind Spotify song recommendation and to what extent a user’s personal characteristics such as personality traits affect the algorithm. The researchers designed a survey to gather respondent’s personality data and ask them to build multiple playlists for use in different situations. The study found significant differences in results and survey usage through differences in personal characteristics such as tech-savviness and Spotify usage.  (Millecamp et al., 2018)
	Although this paper is a bit removed from our research question, the precedent that Spotify songs and their attributes can be used to find correlations between songs and personality types is similar to what we want to do. In particular, the music attributes that Millecamp et al. used in their survey to generate the playlists are the same attributes that are in our Spotify MBTI dataset.

**Motivation:** <br></br>
The exact nature of how specific personality types correlate with musical preferences is still constantly researched, and existing studies have attempted to link the two. It has always been intriguing to our group to understand music's psychological aspect and impact on different personalities. 
Our group loves music and enjoys learning more about it and what we like about it. We want to think more in-depth about what makes people like specific genres of music and why each person has a different and distinct musical taste. What is it about people's personalities that make them like different music? Investigating the association between MBTI profiles and music preferences allows us to understand better how personal characteristics affect music preferences. It would also be interesting to see what recommended playlists would look like for individual MBTI types. 

**Question:** <br></br>
Our research aims to detect how different MBTI personality types can be correlated with specific music preferences. We also want to determine which music features (like tempo, beats, etc.) are significant in predicting different MBTI personality dimensions, like Extrovert vs Introvert, and more. We also want to know if personality traits affect preferences for music of different keys since these elements can shape individual listening experiences. 

**Data Description:** <br></br>
Our proposed data sources include Personality classification Data: 16 Personalities, which is a dataset containing the test taker's responses for each of the test questions we could use to associate with an MBTI. Another source is the Spotify MBTI Playlists which compiled all the user-created playlists that are MBTI themed and calculated the average of each music feature of the playlist. We could also possibly scrape data from the Personality Database website that associates Western songs with a certain personality type to further see the correlation between personality types and music preferences.
To expand on the Spotify MBTI Playlists, we plan on using the Spotify API to transform the dataset from a set of playlists to a set of every single song in the playlists. This way, we can have more individual data for our models and analysis. This is possible with the playlist ID column currently in the dataset, which can be used with the Spotify API to get an array of every single song ID in the playlist. From this array, we can call the Spotify API again to get every single song audio feature for each song. The features in the current dataset are aggregates of the song features, so expanding the dataset will yield the same features. One potential problem with this approach is accessing the playlists with the Spotify API. If any playlist in the Kaggle dataset is private and was added in some way through web scraping, we won’t be able to access the songs in that playlist. However, since the features of each playlist row are exactly the same as the Spotify API audio features, it seems unlikely that the playlists are private.

**Analysis:** <br></br> 
Using the dataset on MBTIs and music features, we will first group the MBTIs according to each dimension using K-Means clustering and designate a column for each dimension in the data-frame. Then, we plan to use logistic regression to analyze the relationship between each personality dimension with specific music features. Through this analysis, any significant attributes of personality will be identified and will be considered as predictors in the predicting model. After the initial analysis has been completed, we plan to use linear regression to further investigate if each personality has a tendency towards certain musical keys when listening to music and if we can predict that as well.

**Timeline:** <br></br>
![image](https://github.com/user-attachments/assets/fc66c46a-6346-441b-87f1-84c2e9691f35)


**References:** <br></br>
Pearson, J. L., & Dollinger, S. J. (2004). Music preference correlates of Jungian 				 types. Personality and individual differences, 36(5), 1005-1008.


Millecamp, M., Htun, N. N., Jin, Y., & Verbert, K. (2018, July). Controlling spotify 				recommendations: effects of personal characteristics on music recommender user 		interfaces. In Proceedings of the 26th Conference on user modeling, adaptation and 		personalization (pp. 101-109).
Boccia, Isabella (2020) "Associations Between Personality Traits and Music Preference," 		Undergraduate Psychology Research Methods Journal: Vol. 1: Iss. 22, Article 2.		https://digitalcommons.lindenwood.edu/cgi/viewcontent.cgi?article=1000&context=psych_journals
	
