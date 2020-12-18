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

### Fetch instructor availability
> Get instructor availability days and times
- **URL** : `/instructor/availabilities`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Headers** : `Token`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```
    {
        "availabilities": [[int],[int],[int],[int],[int]],
        "price": int
    }
    ```

### Update instructor availability
> Update/Insert instructor availability days and times
- **URL** : `/instructor/availabilities`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** :
    ```
    {
        "availabilities": [[int],[int],[int],[int],[int]],
        "price": int
    }
    ```
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Fetch instructor information
> Get List of Instructor who register to be a Private Tutor
- **URL** : `/instructor/list`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```
    {
    "instructors": [
    {
            "id",
            "name": String,
            "info": String,
            "rating": decimal,
            "ratingCount": int,
    }
    ],
    }
    ```
### Fetch Selected Instructor's information
> Get instructor's information
- **URL** : `/instructor/info`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** :
```
 {
	 "id": `instructorId`
 }
```
#### Success Response
-	Status code : `200`
Response Body: 
```
{
 "instructor": {
		"id",
		"name": String,
		"info": String,
		"text": String,
		"rating": decimal,
		"ratingCount": int,
		"price": decimal
   }
}
```
### Fetch Selected Instructor available times
- **URL** : `/instructor/availability`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** :
```
 {
	 "id": `instructorId`,
	 "dates": `YYYY-MM-DD`
 }
```
#### Success Response
-	Status code : `200`
Response Body: 
```
{
 "times": {
	 [ int ]
   }
}
```

### Fetch List of Appointments
> Get List of Appointments that student appointed
- **URL** : `/student/appointments`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
```
{
 "appointments": [
   {
		"id",
		"name": String,
		"info": String,
		"date": `DD MMM YYYY`,
		"startTime": 'HH:MM',
		"endTime": 'HH:MM',
		"isAgree": 'Approved'/'Rejected'/'Pending'
   }
],
}
```

### Insert student appointment
> Insert Appointment that student appointed
- **URL** : `/student/appointments`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** :
```
 {
	 "id",
	 "startTime": timestamp,
	 "endTime": timestamp,
	 "price": int,
	 "members": [{ "id", "name"}]
 }
```
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Fetch instructor's appointment
> Get List of Appointments for instructor
- **URL** : `/instructor/appointments`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
```
{
 "appointment": [
   {
		"appointmentID",
		"id": studentID,
		"name": String,
		"date": `[DD, MM, YYYY]`,
		"startTime": int,
		"endTime": int,
		"status": 'Approved'/'Rejected'/'Pending',
		"members":[{"id","name"}]
   }
],
}
```
### Approve student's Appointment
> Approve or Reject student's Appointment
- **URL** : `/instructor/appointments`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** :
```
 {
	 "appointmentID",
	 "status": boolean
 }
```
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Fetch appointment's rating
> Get List of instructor's reviews
- **URL** : `/instructor/review`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** :
```
 {
	 "id": `instructorId`
 }
```
#### Success Response
-	Status code : `200`
Response Body: 
```
{
	"rating", [{
	  "score": int,
	  "desc": String,
	  "name": String,
	  "date": `YYYYMMDD`
	}]
}
```

### Insert rating of appointment
> Student rate instructor in appointment
- **URL** : `/appointment/review`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** :
```
 {
	  "id": AppointmentID,
	  "score": int,
	  "desc": String,
}
```
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Search students name
> Searching student by first name or last name ( limit 5 )
- **URL** : `/utils/id`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** :
```
 {
	 "name": String,
     "id": UserID
 }
```
#### Success Response
-	Status code : `200`
Response Body: 
```
{
 "students": [
   {
		"id",
		"name": String
   }
],
}
```

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
### Fetch Announcement
> Get Announcement
- **URL** : `/grader/ann`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {id: <integer>, title: <varchar>, description: <text>, adminid: <uuid>, isvisible: <boolean>, time: <timestamp>}}
    ```
### Fetch All contest
> Get Allcontest
- **URL** : `/grader/allcontest`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {conno: <integer>, title: <varchar>, conruletype: <varchar>, description: <text>, starttime: <timestamp>, endtime: <timestamp>, statur: <boolean>, adminid: <uuid>}}
    ```
### Fetch contest annoucement
> Get contestann
- **URL** : `/grader/contestann`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {coannno: <integer>, title: <varchar>, description: <text>, conid: <integer>, adminid: <uuid>, isvisible: <boolean>, time: <time>}}
    ```
 ### Fetch contest All adminlog
> Get Alladminlog
- **URL** : `/grader/alladminlog`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {logno: <integer>, title: <varchar>, detail: <text>, timestamp: <timestamp>, adminid: <uuid>}}
    ```
### Fetch All question
> Get Allquestion
- **URL** : `/grader/allquestion`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {id: <integer>, title: <varchar>, description: <text>, hint: <text>, intputdes: <text>, outputdes: <text>, timelimit: <integer>, memorylimit: <integer>, difficulty: <varchar>, visibility: <boolean>, ruletype: <varchar>, adminid: <uuid>}}
    ```
### Fetch All tag
> Get Alltag
- **URL** : `/grader/alltag`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {tagid: <integer>, tagname: <varchar>}}
    ```
### Fetch contest
> Get contest
- **URL** : `/grader/contest`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": integer }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {conno: <integer>, title: <varchar>, conruletype: <varchar>, description: <text>, starttime: <timestamp>, endtime: <timestamp>, status: <boolean>, adminid: <uuid>}}
    ```
### Fetch contest question
> Get contestquestion
- **URL** : `/grader/conntestquestion`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "conno": integer }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {conquestionno: <integer>, id: <integer>, difficulty: <varchar>, visibility: <boolean>, displayName: <varchar>, adminid: <uuid>}}
    ```
### Fetch Non existing question
> Get addexistingquestion
- **URL** : `/grader/addexistingquestion`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": integer }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {id: <integer>, title: <varchar>}}
    ```
### Fetch question
> Get question
- **URL** : `/grader/question`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": integer }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ data: {id: <integer>, title: <varchar>, description: <text>, hint: <text>, intputdes: <text>, outputdes: <text>, timelimit: <integer>, memorylimit: <integer>, difficulty: <varchar>, visibility: <boolean>, ruletype: <varchar>, adminid: <uuid>}}
    ```
### Fetch question sample
> Get questionsample
- **URL** : `/grader/questionsample`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": integer }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ intput: <text>, output: <text>, sampleno: <integer>}}
    ```
### Fetch question tag
> Get questiontag
- **URL** : `/grader/questiontag`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": `questionid` }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ tagid: <integer>, tagname: <varchar>}}
    ```
### Fetch question test case
> Get questiontestcase
- **URL** : `/grader/questiontestcase`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": `questionid` }
#### Success Response
-	Status code : `200`
Response Body: 
    ```json{ questionid: <integer>, fileno: <integer>, filepath: <varchar>}}
    ```
### Insert question test case
> Post questiontestcase
- **URL** : `/grader/questiontestcase`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert Annoucement
> Post Annoucement
- **URL** : `/grader/cann`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"description": String,
		"adminid": String,
		"visible": boolean;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert question
> Post question
- **URL** : `/grader/cquestion`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"description": String,
		"hint": String,
		"intputDes": String,
		"outputDes": String,
		"timeLimit": Integer,
		"memoryLimit": Integer,
		"difficulty": String,
		"visibility": Boolean,
		"ruleType": String,
		"adminid": String,
		"newTags": Array of String,
		"existTags": Array of String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert contest exist question
> Post contestexistquestion
- **URL** : `/grader/ccontestexistquestion`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "conno": Integer,
		"question": Array of Integer,
		"adminid": String,
		"totalquestion": Integer;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert question sample
> Post questionsample
- **URL** : `/grader/ccontestexistquestion`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "questionId": Integer,
		"samples": Array of String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert contest
> Post contest
- **URL** : `/grader/ccontest`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"conRuleType": String,
		"description": String,
		"startTime": String,
		"endTime": String,
		"status": String,
		"adminid": String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert contest annoucement
> Post contestann
- **URL** : `/grader/ccontestann`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"description": String,
		"conId": Integer,
		"adminId": String,
		"isVisible": Boolean;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Insert contest question
> Post contestquestion
- **URL** : `/grader/ccontestquestion`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : { "conid": Integer,
		"questionId": Integer,
		"adminid": String,
		"title": String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`
    
### Update contest
>Put contest
- **URL** : `/grader/econtest`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Body** : { "conno": Integer,
		"title": String,
		"conRuleType": String,
		"description": String,
		"startTime": String,
		"endTime": String,
		"status": String,
		"adminid": String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Update contest annoucement
>Put contestann
- **URL** : `/grader/econtestann`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"description": String,
		"conId": Integer,
		"adminId": String,
		"isVisible": Boolean;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Update question
>Put question
- **URL** : `/grader/equestion`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Body** : { "title": String,
		"description": String,
		"hint": String,
		"intputDes": String,
		"outputDes": String,
		"timeLimit": Integer,
		"memoryLimit": Integer,
		"difficulty": String,
		"visibility": Boolean,
		"ruleType": String,
		"adminid": String,
		"id": Integer;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Update question sample
>Put questionsample
- **URL** : `/grader/equestionsample`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Body** : { "questionId": Integer,
		"sampleNo": Integer,
		"intput": String,
		"output": String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`


### Update question test case
>Put questiontestcase
- **URL** : `/grader/equestiontestcase`
- **Method** : `PUT`
- **Auth required** : `Yes`
- **Body** : { "questionId": Integer,
		"fileNo": Integer,
		"filepath": String;
		}
- **Params** : `none`
#### Success Response
-	Status code : `200`
Response Body: `none`

### Delete question test case
>Delete questiontestcase
- **URL** : `/grader/dquestiontestcase`
- **Method** : `Delete`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": String}
#### Success Response
-	Status code : `200`
Response Body: `none`

### Delete question sample
>Delete questionsample
- **URL** : `/grader/dquestionsample`
- **Method** : `Delete`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": String}
#### Success Response
-	Status code : `200`
Response Body: `none`

### Delete question
>Delete question
- **URL** : `/grader/dquestion`
- **Method** : `Delete`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "id": String,
		"title": String,
		"adminid": String;}
#### Success Response
-	Status code : `200`

### Delete Contest question
>Delete conquestion
- **URL** : `/grader/dconquestion`
- **Method** : `Delete`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : { "questionid": Integer,
		"conid": String,
		"title": String,
		"adminid": String;}
#### Success Response
-	Status code : `200`
Response Body: `none`

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
