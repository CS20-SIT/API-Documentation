# API-Documentation
## Manager
### Authentications Route

### Google Authentication

> Redirect to /api/auth/google (do not use axios, just use <a> tag to redirect the URL)

- **URL** : `/api/auth/google`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

  **Response Body**: `None`

#### Example



---

### Google Authentication Callback

> Callback route of Google authentication (use passport)

- **URL** : `/api/auth/google/callback`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: `None`


## Group 01
## Group 02
## Group 03
### FetchRoom
•	**URL** : `/api/kahoot/rooms`
•	**Method** : `GET`
•	**Auth required** : `Yes`
•	**Parameters** : `None`
•	**Body** :`None`
Success Response
•	Status code : `200`
Response Body: `rooms`
### FetchQuiz
•	**URL** : `/api/kahoot/question/:sessionid`
• **Method** : `GET`
•	**Auth required** : `None`
•	**Parameters** : `sessionid`
•	**Body** : `None`
#### Success Response
•	**Status code** : `200`
**Response Body**: `room,question,answerAll,correct`
### fetchRoomHistory
•	**URL** : `/api/kahoot/roomHistory`
•	**Method** : `GET`
•	**Auth required** : `None`
•	**Parameters** : `None`
•	**Body** : `None`
#### Success Response
•	Status code : `200`
Response Body: `roomHistory`
### createRoomHistory
•	**URL** : `/api/kahoot/roomHistory`
•	**Method** : `POST`
•	**Auth required** :`None`
•	**Parameters **: `None`
•	**Bod**y : `roomid, pin, isavailable`
#### Success Response
•	**Status code** : `200`
**Response Body**: `room`

### historyPlayer
•	**URL** : `/api/kahoot/roomHistoryplayer`
•	**Method**: `POST`
•	**Auth required**: `Yes`
•	**Parameters** : `None`
•	**Body** : `sessionid, point`
#### Success Response
•	**Status code** : `200`
**Response Body**: `player`
### historyPlayerFirstTime
•	**URL** : `/api/kahoot/roomHistoryplayerFirstTime`
•	**Method**: `POST`
•	**Auth required** : `Yes`
•	**Parameters** : `None`
•	**Body** : `sessionid`
#### Success Response
•	**Status code** : `200`
**Response Body**: `player`
### createQuiz
•	**URL** : `/api/kahoot/createQuiz`
•	**Method**: `POST`
•	**Auth required** : `Yes`
•	**Parameters** : `None`
•	**Body** : `name, description, quesionList, picturepath`
#### Success Response
•	**Status code** : `200`
**Response Body**: `result, question`
### player
•	**URL** : `/api/kahoot/player`
•	**Method**: `POST`
•	**Auth required** : `Yes`
•	**Parameters**: `None`
•	**Body** : `nameforplay`
#### Success Response
•	**Status code** : `201`
**Response Body**: `player`
### fetchExaclyRoom
•	**URL** : `/api/kahoot/sessionid/:pin`
•	**Method** : `GET`
•	**Auth required** : `None`
•	**Parameters** : `pin`
•	**Body** : `None`
#### Success Response
•	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchExaclyRoom
•	**URL** : `/api/kahoot/sessionid/:pin`
•	**Method** : `GET`
•	**Auth required** : `None`
•	**Parameters** : `pin`
•	**Body** : `None`
#### Success Response
•	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchScoreRank
•	**URL** : `/api/kahoot/getRankScore/:sessionid`
•	**Method** : `GET`
•	**Auth required** : `None`
•	**Parameters** : `sessionid`
•	**Body** : `None`
#### Success Response
•	**Status code** : `200`
**Response Body**: `rank,score`
### fetchScoreRankForPlayer
•	**URL**: `/api/kahoot/getRankScorePlayer/:sessionid`
•	**Method**: `GET`
•	**Auth required** : `None`
•	**Parameters** : `sessionid`
•	**Body** : `None`
#### Success Response
•	**Status code** : `200`
**Response Body**: `rank,score`
### Upload
•	**URL** : `/api/kahoot/getRankScorePlayer/:sessionid`
•	**Method** : `POST`
•	**Auth required** : `None`
•	**Parameters** : `None`
•	**Body** : `None`
#### Success Response
•	**Status code** : `None`
**Response Body**: `result`












## Group 04
## Group 05
## Group 06
## Group 07
## Group 08
## Group 09
## Group 10
## Group 11
## Group 12
## Group 13
## Group 14
## Group 15
