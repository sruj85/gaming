
Problem Statement: To Set Up a NodeJS server to simulate Leaderboard for games. 
Deploy on EC2 if possible 
Context
Users can register using phone number and password. Users can login through phone 
number and password and get access token. Each user will be having a user-profile which 
stores basic information of the user. (Name, Age, Location, Email Id, phoneNumber). There 
will be 3 games, each with a unique id. There will be a leaderboard which ranks users based 
on certain criterias (wins, points scored) for each game. There will be an admin who can 
post the result of a game between two players.
Features from the server:
• User need to be authenticated (JWT/OAuth) when using the APIs
• User can update his information except phone number
• Users can get a list of games.
• An Admin will post the result of a game between two users. The payload for the 
result will be - gameId, u1Id, u2Id, scoreU1, scoreU2, win (boolean wrt u1, if true 
then u1 wins else u2 wins).
• Users cannot post game results
• Based on results, an aggregated value will be used to get total points for users for 
each game.
• Users can see aggregated scores of each user for each game (leaderboard).
• Example
o payload1 - {u1Id: 1, u2Id: 2, scoreU1: 30, scoreU2: 40, win: false, gameId:1}
o Payload2 - {u1Id: 2, u2Id: 3, scoreU1: 45, scoreU2: 40, win: true, gameId:1}
o Payload3 - {u1Id: 1, u2Id: 3, scoreU1: 45, scoreU2: 40, win: true, gameId:2}
• For game with gameId 1 leaderboard will be
o U2 -Rank 1, totalWins 2, totalPoints - 85
o U3 - Rank 3, totalWins 0, totalPoints - 40
o U1 - Rank 2, totalWins 0, totalPoints - 30 
• For game with gameId 2 leaderboard will be
o U1 - Rank 1, totalWins 1, totalPoints - 45
o U3 - Rank 2, totalWins 0, totalPoints - 40
Use an appropriate database to handle the problem. The server needs to expose the 
features via APIs based on REST principles and event driven logic to be implemented in 
every possible situation. Additionally, write appropriate test cases to simulate practical 
scenarios that you would want to test the system for. Maintain the code through the course 
of the development on a version control system.This document is the sole property of Parkinnov Funtech Pvt. Ltd. & information presented is
strictly confidential. Don’t duplicate or distribute without the consent of the company.
Submission:
1. Postman collection for the APIs and relevant credentials to test out
2. Access to the code repository hosted on Gitlab/Bitbucket in a private repo
Please Note: You are expected to design APIs on your own
