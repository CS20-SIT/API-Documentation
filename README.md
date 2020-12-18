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
-	**URL** : `/api/kahoot/rooms`
-	**Method** : `GET`
-	**Auth required** : `Yes`
-	**Parameters** : `None`
-	**Body** :`None`
#### Success Response
-	Status code : `200`
Response Body: `rooms`
### FetchQuiz
-	**URL** : `/api/kahoot/question/:sessionid`
- **Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `sessionid`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `room,question,answerAll,correct`
### fetchRoomHistory
-	**URL** : `/api/kahoot/roomHistory`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `None`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `roomHistory`
### createRoomHistory
-	**URL** : `/api/kahoot/roomHistory`
-	**Method** : `POST`
-	**Auth required** :`None`
-	**Parameters**: `None`
-	**Bod**y : `roomid, pin, isavailable`
#### Success Response
-	**Status code** : `200`
**Response Body**: `room`

### historyPlayer
-	**URL** : `/api/kahoot/roomHistoryplayer`
-	**Method**: `POST`
-	**Auth required**: `Yes`
-	**Parameters** : `None`
-	**Body** : `sessionid, point`
#### Success Response
-	**Status code** : `200`
**Response Body**: `player`
### historyPlayerFirstTime
-	**URL** : `/api/kahoot/roomHistoryplayerFirstTime`
-	**Method**: `POST`
-	**Auth required** : `Yes`
-	**Parameters** : `None`
-	**Body** : `sessionid`
#### Success Response
-	**Status code** : `200`
**Response Body**: `player`
### createQuiz
-	**URL** : `/api/kahoot/createQuiz`
-	**Method**: `POST`
-	**Auth required** : `Yes`
-	**Parameters** : `None`
-	**Body** : `name, description, quesionList, picturepath`
#### Success Response
-	**Status code** : `200`
**Response Body**: `result, question`
### player
-	**URL** : `/api/kahoot/player`
-	**Method**: `POST`
-	**Auth required** : `Yes`
-	**Parameters**: `None`
-	**Body** : `nameforplay`
#### Success Response
-	**Status code** : `201`
**Response Body**: `player`
### fetchExaclyRoom
-	**URL** : `/api/kahoot/sessionid/:pin`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `pin`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchExaclyRoom
-	**URL** : `/api/kahoot/sessionid/:pin`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `pin`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchScoreRank
-	**URL** : `/api/kahoot/getRankScore/:sessionid`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `sessionid`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `rank,score`
### fetchScoreRankForPlayer
-	**URL**: `/api/kahoot/getRankScorePlayer/:sessionid`
-	**Method**: `GET`
-	**Auth required** : `None`
-	**Parameters** : `sessionid`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `rank,score`
### Upload
-	**URL** : `/api/kahoot/getRankScorePlayer/:sessionid`
-	**Method** : `POST`
-	**Auth required** : `None`
-	**Parameters** : `None`
-	**Body** : `None`
#### Success Response
-	**Status code** : `None`
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

### showForum

> Show all forum

- **URL** : `/api/forum`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: ``` json{ data: {forumid: <integer>, titlethread: <varchar>, userid: <uuid>, displayname: <varchar>, posttime: <timestamp>, subtypename: <varchar>, typename: <varchar>}}```
    
    
    
### getCategory

> Show all category

- **URL** : `/api/forum/category`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`
    **Response Body**: ``` json{ data: {typename: <varchar>} }```
    
    
    
### getSubCategory

> Show all sub category

- **URL** : `/api/forum/subcategory`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: ``` json{ data: {typename: <varchar>, subtypename: <varchar>}}```
    
    
### selectForum

> Show information of each forums

- **URL** : `/api/forum/:id`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `id: <integer>`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: ```json{ data : {forumid: <integer>, titlethread: <varchar>, userid: <uuid>, displayname: <varchar>, posttime: <timestamp>, subcategoryiid: <integer>, content: <text>, isdelete: <boolean>, likes:<bigint>, comments:<bigint>, is_like: <uuid>, answerno: <integer>, anstime: <timestamp>, answer: <text> }}```
    
    
    
 ### setLike

> show that is this forum liked ?

- **URL** : `/api/forum/like/:id`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `forumid : <integer>`
- **Body** : `None`



#### Success Response

- **Status code** : `201`

    **Response Body**: `None`
    
    
    
### createComment

> Create new comment

- **URL** : `/api/forum/comment`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : ` {id: <uuid>, comment: <string> }`



#### Success Response

- **Status code** : `200`

    **Response Body**: ``` json{ data: {forumid: <integer>, answerno: <integer>, userid: <uuid>, anstime: <timestamp>, answer: <text>}}```
    
    
    
### setForum

> Create new forum

- **URL** : `/api/forum/create`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{title: <varchar>, comment: <string> }`



#### Success Response

- **Status code** : `200`

    **Response Body**: ``` json{ data: {userid: <uuid>, titlethread: <varchar>, subcategoryiid: <integer>, content: <text>}}```
    
    
    
### selectRoom

> Show all forum in room which you select

- **URL** : `/api/forum/room/:roomname`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `roomname: <varchar>`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: ```json{ data : {forumid: <integer>, titlethread: <varchar>, userid: <uuid>, displayname: <varchar>, posttime: <timestamp>, subtypename: <varchar>, typename: <varchar>, categorytypeid: <integer>, content: <text>, isdelete: <boolean>, likes:<bigint>, comments:<bigint>, is_like: <uuid>, answerno: <integer>, anstime: <timestamp>, answer: <text> }}```
    
    
    
 ### deleteComment

> Delete comment

- **URL** : `/api/forum/comment/:id`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `forumid : <integer>`
- **Body** : `{answerno: <integer> }`



#### Success Response

- **Status code** : `200`

    **Response Body**: `None`
    
    
    
### deleteForum

> Delete forum

- **URL** : `/api/forum/:id`
- **Method** : `DELETE`
- **Auth required** : `Yes`
- **Parameters** : `forumid : <integer>`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: `None`
    
    
    
### editForum

> Edit forum

- **URL** : `/api/forum/:id`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Parameters** : `forumid : <integer>`
- **Body** : `{content: <text>, titlethread: <varchar>, oldcontent: <text> }`



#### Success Response

- **Status code** : `200`

    **Response Body**: `None`
    
  
  
### searchForum

> Search forum

- **URL** : `/api/forum/search`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{search: <string> }`



#### Success Response

- **Status code** : `200`

    **Response Body**: ``` json{ data: {forumid: <integer>, titlethread: <varchar>, userid: <uuid>, displayname: <varchar>, posttime: <timestamp>, subtypename: <varchar>, typename: <varchar>,likes:<bigint>, comments:<bigint>, is_like: <uuid>}}```
    
    
## Group 13
## Group 14
## Group 15
