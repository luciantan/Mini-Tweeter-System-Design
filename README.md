# Mini-Tweeter-System-Design
This project is to discuss how to optimize News Feed System. Push vs Pull?
If you are asked to design a system for Tweeter. Which method would you choose to maintain the usability of your system? 

1: When a user posts a tweet, let the system help the user to forward his tweet to all his friends (large scale, such as 60M). This is NOT a synchronized way. However, the user can tweet very fast, especially for some super stars. He can post a tweet and don't have to wait for the system to tell him that his tweeter has successfully been tweeted to all his followers. 

2: When a user posts a tweet, add the user's tweet to a shared table with all the other users. Add a column to the table Every user gets the new tweet from this big shared table. This is a synchronized way, but every time when user wants to read new tweets, it is slower. 

How would you choose from the above trade-offs?

