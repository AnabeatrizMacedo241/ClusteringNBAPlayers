# Clustering NBA Players
Understanding the player's roles in modern NBA.

`K-Means` and `Herarchical Clustering` to make the divisions.

## K-Means

For K-Means, it was first used the Eblow Method to try define the optima number of clusters, but the elbow only starts to appear after a high number of K's like 20. And that is not the best option for our problem.

In order to that, it was applied the Silhouette score to understand the "information gain" from o K to another. IN the picture below, we are able to see that from cluster 8 to 9 there ia higher gain of information than any other K. The best score was 0.43.

![Silhouette](https://user-images.githubusercontent.com/84348494/223659252-56e9293b-f3cb-4116-8490-ea9162e13d27.png)

This is how we calculated the gain to make sure 9 was an interesting number of clusters.

```
Gain = Silhouette_score_2-Silhouette_score_1
Rverse Gain = Silhouette_Score3-Silhouette_score2
Final Metric = Score_absolute_value(Reverse Gain)
Percentual = Sihlouette_score3/(Silhouette_score_2-1)
```

TSNE was also picked to make the dimensionality reduction, becuase it is a algorith that it is better for clustering visulaizations in 2D.

## Hierarchical Clustering

Then, Hierarchical Clustering was implemented to check if 9 was ineed a good cluster to segment the players. 

|![Hierarchical_Clustering](https://user-images.githubusercontent.com/84348494/223669263-e196d3b7-bb27-47a7-9164-bcdac8c1ae99.png)|
|:--:| 
| *Player's Dendogram* |

  
When the highest vertical line is found, we then cross a horizonta line. This line will cut trough every other vertical line 9 times. This means that 9 clusters could albo be interesint for this algorithm. Later, the svore was 0.45.

## Post Modeling

Here are some players in ther respective cluster.

|![Division](https://user-images.githubusercontent.com/84348494/223670529-87cd2cac-5493-493d-ba2b-e2ed3cdde242.png)|
|:--:| 
| *Groups* |

|![Clustering_Analysis](https://user-images.githubusercontent.com/84348494/223670351-8da43c14-da1d-4ea2-861c-b061ca10e3f8.png)|
|:--:| 
| *Peformance by Cluster and Position* |


The `"6th Man"` cluster is composed of players with more playmaking and mid-range shot attempts. They usually have fewer minutes on the court than starters, but more minutes than an average reserve player.

The `"Reserves"` and `"Bench Warmers"` were two really similar clusters. The first one has a little more time on the court and a slight point-per-game advantage. The second has basically no time on the court, but they are often called when the game is already done.

The `"Role Players"` usually start every game and if they do not, they are the first option off the bench. They are able to put up some numbers every night, but they are mostly there to help to stretch the play and help the others get good shots.

The `"Defensive Big Men"` group is composed of players that are able to protect the rim and pressure their opponents. They also have interesting points and rebounds per game. This cluster has more Centers than any other position.

The `"Key Pieces"` is a cluster filled with shooters and some players who can call plays. They are great at finding their teammates while also being able to find good shots for themselves. This cluster has many shooting and point guards.

The `"Rising Stars"` are the players who are on the way to becoming good threats in the NBA. Usually, their primary role is to support the stars of the team, but when needed they are able to take the lead and get some good stats that make them start every game.

The `"Offensive Big Men"`are the players who dominate the interior of the opponent's court. They take more shots from mid-range than long-range, but that does not mean that they are not efficient in the last one. They are the number one rebounders and can also provide good assists to their teammates.

Last but not least, the `"Do it All"`. As the title says, this is a group of players who can do everything and they do everything amazingly. They have the highest points and assists per game. To be a part of this group, players need a 22+ PPG. We have all of the NBA positions in this cluster, and the teams who have these kinds of players rely on them to achieve good performances.

Data: basketball-reference.com
