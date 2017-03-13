# Mini-Tweeter-System-Design
This project is to discuss how to optimize News Feed System. Push vs Pull?
If you are asked to design a system for Tweeter. Which method would you choose to maintain the usability of your system? 

1: When a user refreshes his tweeter, the system gathers top 100 tweets from all friends of this user. Then merge them based on time.(May use Merge K Sorted Linked List algorithm). The problem is that reading 100 times from the database is too slow, especially when the database is distributed. Cache may be used to mitigate this issue, but cache is expensive.

2: To resolve the problem of gathering tweets slow. Re-design the system so that when a user posts a tweet, the system helps the user to forward his new tweet to all his followers. Assume that the number of followers is N, the system will add the same tweet into the database for N times, each time the system will assign the authority of seeing this tweet as one of the followers. In this case, more memory is need, but the speed for each users to load their Tweeter is faster. 

How would you choose from the above trade-offs? Considering the fact that the speed of a system is critical for the usability, and the discs are usually cheap, most of the designers may choose the second solution at the first glance. However, The second design implemented the system in an asynchonized way, which made the system not stable in certain cases. For example, when a superstar who has millions of followers, the new tweet from this superstar will be forwarded to all of his followers one by one. If changes happend during the forwarding time, the system is crashed. 

So which one is the best design? The answer is both. There is no best design for all situations or scenarios. The designer need to make their decition based on different situations. 
