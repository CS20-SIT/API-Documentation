# API-Documentation
## Manager
### Authentications Route

### User Login

> Authenticate the use and return the cookie back

- **URL** : `/api/auth/login`

- **Method** : `POST`

- **Auth required** : `No`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
    	email: <String>
    	password: <String>
  }
  ```

#### Success Response

- **Status code** : `200`

  **Cookie**: `jwt`

  **Response Body**: 
  
  ```json
  { 
      success: true, 
      isVerify: <true|false> 
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: 'Email or password is incorrect'
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### User Registration

> Register the new user

- **URL** : `/api/auth/register`

- **Method** : `POST`

- **Auth required** : `No`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
      email: <String>
      password: <String>
      firstname: <String>
      lastname: <String>
  }
  ```

#### Success Response

- **Status code** : `200`

  **Cookie**: `jwt`

  **Response Body**: 

  ```json
  { 
      success: true
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: 'Email is used'
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### User Profile

> Get user profile

- **URL** : `/api/auth/profile`

- **Method** : `GET`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Cookie**: `jwt`

  **Response Body**: 

  ```json
  {
      "userid": <String>,
      "firstname": "<String>,
      "lastname": <String>,
      "birthdate": <String>,
      "initial": <String>,
      "phoneno": <String>,
      "displayname": <String>,
      "bio": <String>,
      "avatar": <String of URL>,
      "createat": <String>,
      "updateat": <String>,
      "id": <String>,
      "role": <String>,
      "email": <String>,
      "verify": <boolean>
  }
  ```

#### Error Response

- **Status code** : `401`

  **Response Body**: 

  ```json
  {
      "success": false,
      "error": "Unauthorize"
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### User Email Verification

> Verify the email that user input

- **URL** : `/api/auth/verify/:token`

- **Method** : `GET`

- **Auth required** : `NO`

- **Parameters** : `None`

- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**: `None but redirect to successful verification page` 

#### Error Response

- **Status code** : `200`

  **Response Body**:` None but redirect to error verification page`

---

### User Logout

> Logout user from the system

- **URL** : `/api/auth/logout`

- **Method** : `GET`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : `None`


#### Success Response

- **Status code** : `200`

  **Response Body**: 

  ```json
  { 
      success: true
  }
  ```
  
#### Error Response
- **Status code** : `401`

  **Response Body**: 

  ```json
  {
      "success": false,
      "error": "Unauthorize"
  }
  ```

---

### Admin Registration

> Register the new admin

- **URL** : `/api/auth/admin/register`

- **Method** : `POST`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
    	email: <String>
    	password: <String>
  }
  ```

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  { 
      success: true
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: 'Username is used'
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### Admin Login

> Let admin login to the system

- **URL** : `/api/auth/admin/login`

- **Method** : `POST`

- **Auth required** : `NO`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
    	email: <String>
    	password: <String>
  }
  ```

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  { 
      success: true
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <'User does not exist' | 'Password is not correct'>
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### Admin Profile

> Return infomation of that admin

- **URL** : `/api/auth/admin/profile`

- **Method** : `GET`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**: 

  ```json
  {
      "displayname": <String>,
      "firstname": <String>,
      "lastname": <String>,
      "avatar": <String>,
      "role": <String>
  }
  ```

#### Error Response

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

### Admin Logout

> Logout admin from the system

- **URL** : `/api/auth/admin/logout`

- **Method** : `GET`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**: 

  ```json
  { 
      success: true
  }
  ```
#### Error Response
- **Status code** : `401`

  **Response Body**: 

  ```json
  {
      "success": false,
      "error": "Unauthorize"
  }
  ```
---

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

---

### Admin Routes

### Admin Edit Profile

> Edit profile of the admin

- **URL** : `/api/admin/editAdminProfile`

- **Method** : `POST`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : It can contain empty string

  ```json
  {
      "firstname": <String>,
      "lastname": <String>,
      "displayname": <String> 
  }
  ```

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  {
      "firstname": <String>,
      "lastname": <String>,
      "displayname": <String> 
  }
  ```

#### Error Response

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### Admin Edit Password

> Edit admin's password

- **URL** : `/api/admin/editPassword`

- **Method** : `POST`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
      "oldPassword": <String>,
      "newPassword": <String>
  }
  ```

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  {
    	"success": true
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: "Old password doesn't match"
  }
  ```

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---

### Admin Edit Profile Picture

> Edit admin's profile picture

- **URL** : `/api/admin/editProfilePic`

- **Method** : `POST`

- **Auth required** : `YES`

- **Parameters** : `None`

- **Body** : Multipart-formdata of profile_picture file

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  {
    	"avatarURL": <String of URL>
  }
  ```

#### Error Response

- **Status code** : `500`

  **Response Body**: 

  ```json
  { 
      success: false, 
      error: <String>
  }
  ```

---


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
### fetchExactlyRoom
-	**URL** : `/api/kahoot/sessionid/:pin`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `pin`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchExactlyRoom
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
-	**URL** : `/api/kahoot/upload/picture`
-	**Method** : `POST`
-	**Auth required** : `Yes`
-	**Parameters** : `None`
-	**Body** : `None`
#### Success Response
-	**Status code** : `None`
**Response Body**: `result`
### checkQuizClose
-	**URL** : `/api/kahoot/checkQuizClose/:sessionid`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `Yes`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `update`
### fetchExactlyRoomAfterStart
-	**URL** : `/api/kahoot/sessionidAfterStart/:pin`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `Yes`
-	**Body** : `None`
#### Success Response
-	**Status code** : `200`
**Response Body**: `exactlyRoom`
### fetchExactlyRoomAfterStart
-	**URL** : `/api/kahoot/closeRoom/:sessionid`
-	**Method** : `GET`
-	**Auth required** : `None`
-	**Parameters** : `Yes`
-	**Body** : `None`
#### Success Response
-	**Status code** : `None`
**Response Body**: `None`












## Group 04
## Group 05
### Fectch Chatlist 
> getChatlist
- **URL** : `/chat/getChatlist`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** :`none`
#### Success Response
- **Status code** : `200`

**Response Body** : 
```
{chatroomid: <integer>, firstName: <varchar>, roomname: <varchar>, message: <varchar>, sendtime: <timestamp>}

```
### Get UserProfile
> getUserprofile
- **URL** : `/chat/getUserprofile`
- **Method** : `GET`
- **Auth required** :`Yes`
- **Body** : `none`
- **Params** : `none`
#### Success Response
- **Status code** : `200`

**Response Body** : 
```
{          userID:  <uuid>, userFirstName: <varchar>, userLastName: <varchar>, userNickName: <varchar>, profilePicture: <filepath>',}
```

### Get InvitationList
> getgetInvitationList
- **URL** : `/chat/getInvitationList`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params**: `none`
#### Success Response
- **Status code** : `200`

**Response Body** : 
```
invitations: [ { invitaionID: <Integer>, chatRoomID: <Integer>, chatRoomName: <varchar>, invitor: <varchar>, profilePicture: <path> }

```

### Get SearchReuslt
> getSearchResult
- **URL**: `/chat/getSearchResult
- **Method**: `GET`
- **Auth required**: `Yes`
- **Body**: `none`
- **Params**: `none`
#### Success Response
- **Status code** : `200`

**Response Body** : 
```
users: [ { userID: <uuid>, userFirstName: <varchar> , userLastName: <varchar> , display: <varchar> , userProfile: <path> }

```

### Accept Invitation
> acceptInvitation
- **URL**: `/chat/acceptInvitation
- **Method**: `POST`
- **Auth required**: `Yes`
- **Body**: 
```
{
	"chatroomid" : Integer
	"userid" : uuid
	" nickname" : String 
	"sender_color" : String  
	"receiver_color" : String  
	"hide" : Boolean
}	
```
- **Params** : `none`

#### Success Response

- **Status code** : `200`

**Response Body** : `Success : true`

### Fetch chatroom message
> getChatroomDetail
- **URL** : `/chat/getChatroomDetail`
- **Method** : `GET`
- **Auth required**: `Yes`
- **Body**:  `none`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 
```
chatRoomID: 2,
chatRoomName: <varchar>,
            themeColor: {
                sendColor: <varchar>,
                recieveColor: <varchar>,
            },
            membersID: [uuid,uuid,uuid,uuid],
messages: [ { system: <Boolean>,
                    	sticker: <Boolean>,
					message: <varchar>,
					sendTime: <timestamp>,
					reader: [
						{
							readerID: <uuid>,
							readTime: <timestamp>,
						},
						{
							readerID: <uuid>,
							readTime: <timestamp>,
						},
						{
							readerID: <uuid>,
							readTime: <timestamp>,
						},
					],
				}
```

### Get Chatroom picture
> getChatRoomProfile

- **URL** : `/chat/getChatRoomProfile`
- **Method** : `GET`
- **Auth required**: `Yes`
- **Body**:  `none`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 
```
{  chatRoomID: <Integer>,  chatRoomProfilePicture: <path>  }
```

### decline Invitation
> declineInvitation
- **URL** : `/chat/declineInvitation`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	invitationid = Integer 
	inviteeid = uuid
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### hideChatroom
> hideChatroom
- **URL** : `/chat/hideChatroom`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	hide = Boolean
	chatroomid = Integer
	userid = uuid
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### leave Chatroom
> leaveChatRoom

- **URL** : `/chat/leaveChatRoom`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	userid = uuid
	chatroomid = Integer
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### deleteChatRoom
> deleteChatRoom

- **URL** : `/chat/deleteChatRoom`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	chatroomid = Integer
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### storeMessage
> sendMessage

- **URL** : `/chat/sendMessage`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	message = String
	sendtime = timestamo
	chatroomid = Integer
	userid = uuid
	issticker = Boolean
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### unsendMessage
> unsendMessage

- **URL** : `/chat/unsendMessage`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	messageid = Integer
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### changeChatColor
> changeThemeColor

- **URL** : `/chat/unsendMessage`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	sender_color = String
	receiver_color = String
	chatroomid = Integer
	userid = uuid
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### changeChatRoomName
> changeChatRoomName

- **URL** : `/chat/unsendMessage`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	roomname = String
	chatroomid = Integer
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### checkRead
> readMessage

- **URL** : `/chat/unsendMessage`
- **Method** : `Post`
- **Auth required**: `Yes`
- **Body**:  `{
	message = Integer
	userid = uuid
	sendtime = timestamp
	hide = Boolean
}`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{ success : true}
```

### getSearchResult (ExistedRoom)
> selectSearchResult

- **URL** : `/chat/selectSearchResult`
- **Method** : `GET`
- **Auth required**: `Yes`
- **Body**:  `none`
- **Params** : `none`
#### Success Response

- **Status code** : `200`

**Response Body** : 

```
{
	chatroomid = Integer
	userid = uuid
	userid = uuid
}
```

## Group 06

### **Fetch Leaderboard Ranking**

> Get Leaderboard Rank

- **URL**:`/api/leaderboard`
- **Method**:`GET`
- **Auth required**:`Yes`
- **Body**:`none`
- **Params**:`none`

#### Success Response

- **Status code**:`200`

    **Response Body**:

    ```
    {
    displayname: String 
    titlename: String
    xp: String
    }
    ```



### **Fetch All Path** 

> Get Path

- **URL**:`/api/learningpath`
- **Method**:`GET`
- **Auth required**:`Yes`
- **Body**:`none`
- **Params**:`none`

#### Success Response

- **Status code**:`200`

    **Response Body**:

    ```
    {
    path_description: String
    path_name: String
    pathid: Integer
    }
    ```



### **Fetch Current Path** 

> Get Current Path

- **URL**:`/api/learningpath/path`
- **Method**:`GET`
- **Auth required**:`Yes`
- **Body**:`none`
- **Params**:`none`

#### Success Response

- **Status code**:`200`

    **Response Body**:

    ```
    {
    complete: Boolean
    node_desc: String
    node_name: String
    nodeid: Integer
    parent_complete: Boolean
    parent_node_id: Integer
    pathid: Integer
    }
    ```

    

### **Fetch Node Exercise** 

> Get Exercise

- **URL**:`/api/learningpath/exercise`
- **Method**:`GET`
- **Auth required**:`Yes`
- **Body**:`none`
- **Params**:`none`

#### Success Response

- **Status code**:`200`

    **Response Body**:

    ```
    {
    answer: String
    complete: Boolean
    nextNode: Integer
    node_name: Boolean
    nodeid: Integer
    path_name: String
    pathid: Integer
    question: String
    }
    ```



### **Fetch Quiz by NodeID** 

> Get quizByNodeId

- **URL**:`/api/learningpath/quizByNodeId`
- **Method**:`GET`
- **Auth required**:`Yes`
- **Body**:`none`
- **Params**:`none`

#### Success Response

- **Status code**:`200`

    **Response Body**:

    ```
    {
    nodeDetail:
        node_desc: String
        node_name: String
        nodeid: Integer
        parent_node_id: Integer
        path_name: String
        pathid: Integer
    questions: Array(4)
        0:nodeid: Integer
        	questionno: Integer
        	questionname: String
        	description: String
          choices: Array(4) 
              0: {choiceno: Integer, answer: String, iscorrect: Boolean}
              1: {choiceno: Integer, answer: String, iscorrect: Boolean}
              2: {choiceno: Integer, answer: String, iscorrect: Boolean}
              3: {choiceno: Integer, answer: String, iscorrect: Boolean}
        1: {nodeid: Integer, questionno: Integer, questionname: String, description: String, choices: Array(4)}
        2: {nodeid: Integer, questionno: Integer, questionname: String, description: String, choices: Array(4)}
        3: {nodeid: Integer, questionno: Integer, questionname: String, description: String, choices: Array(4)}
    }
    ```



### Insert UserProgress for each completed node

> Insert progress and score

- **URL** : `/api/learningpath/completeNode`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

    ```
    score: Integer
    nodeid: Integer
    ```

    

- **Params** : `none`

#### Success Response

- **Status code** : `200`

    **Response Body** :`none`





## Group 07

### Insert Instructor register

> Insert Instructor information

- **URL** : `api/instructor/register`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  {
      "degree" : String
      "expert" : String
      "bio" : String
      "degreepath" : String
      "expertpath" : String
  }
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Insert Upload instructor evidence

> Insert picture of instructor evidence

- **URL** : `api/instructor/upload/evidence`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  Photo File
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Fetch Instructor approve

> get Instructor approve

- **URL** : `api/instructor/profile`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :

  ``` 
  {
  "isverified" : boolean
  "role" : String
  }
  ```

### Fetch Instructor profile

> get Instructor information

- **URL** : `api/instructor/profileDetail`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :

  ``` 
  {
  	"bio" : String
  	"degree" : [String]
  	"expert" : [String]
  }
  ```

### Fetch Instructor course

> Get course that instructor is the owner

- **URL** : `api/instructor/courses`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :

  ``` 
  [
   {
  	"certpath" : String
  	"coursedescription" : String
  	"courseid" : String
  	"coursename" : String
  	"coursepicture" : String
  	"havecert" : boolean
  	"language" : String
  	"ownerid" : String
  	"price" : String
  	"samplevideo" : String
  	"status" : String
   }
  ]
  
  ```

### Update Instructor profile

> Update Instructor information

- **URL** : `api/instructor/Editprofile`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Body** : 

``` 
{
	"degree" : String
    "expert" : String
    "bio" : String
}
```



- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :


### Insert Course create

> Insert Course create information

- **URL** : `api/instructor/course`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  {
  "name" : String
  "picturePath" : String
  "videoPath" : String
  "section" : [
  	{
  	"name" : String
  	"materials" : [{"path" : String}]
  	"questions" : [
  		{
  		"choices" : [String, String, String, String]
  		"correct" : int
  		"q" : String
  		}
  	]
  	"videos" : [
  		{
  		"name" : String
  		"path" : String
  		}
  	]
  	}
  ]
  }
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** : `none`

### Get Course category

> Get Course category

- **URL** : `api/instructor/categories`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Body** : `none`
- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :

  ``` 
  [
  	{
			"cataid" : int
  		"cataname" : String
  	}
  ]
  ```
  

### Insert Upload Course  picture

> Insert picture of the course

- **URL** : `api/instructor/upload/picture`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  Photo File
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Insert Upload Course sample video

> Insert sample video of the course

- **URL** : `api/instructor/upload/sampleVideo`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  Video File
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Insert Upload Section video

> Insert video of the section

- **URL** : `api/instructor/upload/videos`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  Video File
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Insert Upload  Section material

> Insert material of the section

- **URL** : `api/instructor/upload/materials`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  PDF File
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

### Delete Course

> Delete Course

- **URL** : `api/instructor/deletecourse`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Body** : 

  ```
  {
  	"courseid" : String
  }
  ```

  

- **Params** : `none`

#### Success Response

- **Status code** : `200`

  **Response Body** :`none`

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
  
    ```
    { data: {id: <integer>, title: <varchar>, description: <text>, adminid: <uuid>, isvisible: <boolean>, time: <timestamp>}}   
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
    ```
    { data: {conno: <integer>, title: <varchar>, conruletype: <varchar>, description: <text>, starttime: <timestamp>, endtime: <timestamp>, statur: <boolean>, adminid: <uuid>}}
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
    ```
    { data: {coannno: <integer>, title: <varchar>, description: <text>, conid: <integer>, adminid: <uuid>, isvisible: <boolean>, time: <time>}}
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
    ```
    { data: {logno: <integer>, title: <varchar>, detail: <text>, timestamp: <timestamp>, adminid: <uuid>}}
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
    ```
    { data: {id: <integer>, title: <varchar>, description: <text>, hint: <text>, intputdes: <text>, outputdes: <text>, timelimit: <integer>, memorylimit: <integer>, difficulty: <varchar>, visibility: <boolean>, ruletype: <varchar>, adminid: <uuid>}}
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
    ```
    { data: {tagid: <integer>, tagname: <varchar>}}
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
    ```
    { data: {conno: <integer>, title: <varchar>, conruletype: <varchar>, description: <text>, starttime: <timestamp>, endtime: <timestamp>, status: <boolean>, adminid: <uuid>}}
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
    ```
    { data: {conquestionno: <integer>, id: <integer>, difficulty: <varchar>, visibility: <boolean>, displayName: <varchar>, adminid: <uuid>}}
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
    ```
    { data: {id: <integer>, title: <varchar>}}
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
    ```
    { data: {id: <integer>, title: <varchar>, description: <text>, hint: <text>, intputdes: <text>, outputdes: <text>, timelimit: <integer>, memorylimit: <integer>, difficulty: <varchar>, visibility: <boolean>, ruletype: <varchar>, adminid: <uuid>}}
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
    ```
    { intput: <text>, output: <text>, sampleno: <integer>}}
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
    ```
    { tagid: <integer>, tagname: <varchar>}}
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
    ```
    { questionid: <integer>, fileno: <integer>, filepath: <varchar>}}
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

### get sticker from database
>show sticker in sticker store
 - **URL** : `/api/coin/stickers`
 - **Method** : `GET`
 - **Auth required** : `none`
 - **Headers** : `Token`
 - **Body** : `none`
 - **Params** : `none`
#### Success Response
 - Status code : `200`
 - Response Body: 
```
[
	{
	"id":  int,
	"title": String,
	"price":  int,
	"img":  String,
	"type":  int
	}
]
```

  

### Get packSticker in payment store 

> show pack sticker each of sticker in payment sticker store
 - **URL** : `/api/coin/stickers/:id`
 - **Method** : `GET`
 - **Auth required** : `none`
 - **Body** : `none`
 - **Params** : `none`
#### Success Response
 - Status code : `200`
 - Response Body: 
 ```
 {
	"mycoins":  int,
	"stickers":  [
			{
			"stickername":  String,
			"stickerimg": String,
			"stickerprice":  int,
			"stickernumber":  int
			}
	]
}
 ```

### Show sticker owner in history of user

> show sticker which user has.
 - **URL** : `/api/coin/stickerOwner`
 - **Method** : `GET`
 - **Auth required** : `yes`
 - **Body** : `none`
 - **Params** : `none`
#### Success Response
 - Status code : `200`
 - Response Body: 
 ```
 {
	"mycoins":  int,
	"stickers":  [
			{
			"stickername":  String,
			"stickerimg": String,
			"stickerprice":  int,
			"stickernumber":  int
			}
	]
}
 ```


### get daily reward 

> check user ever get daily reward
 - **URL** : `/api/coin/dailyReward`
 - **Method** : `GET`
 - **Auth required** : `yes`
 - **Body** : `none`
 - **Params** : `none`
#### Success Response
 - Status code : `200`
 - Response Body: 
 ```
 {
	"canGet" : boolean
}
 ```

### Show coin owner in history

> show coin owner in history
 - **URL** : `/api/coin/coinOwner`
 - **Method** : `GET`
 - **Auth required** : `yes`
 - **Body** : `none`
 - **Params** : `none`
#### Success Response
 - Status code : `200`
 - Response Body: 
 ```
 {
	"amountofCoin" : int
}
 ```

### Buy Sticker

> update amount coin of user and insert sticker that user buy sticker.
 - **URL** : `/api/coin/buySticker`
 - **Method** : `POST`
 - **Auth required** : `yes`
 - **Body** :
 ```
	 {
		 "stcikerId" : int
	 }
 ```
 - **Params** : `none`
#### Success Response
 - Status code : `201`
 - Response Body: 
 ```
	 {
		"amountofCoin" : int
	 }
 ```

### Buy Coupon in Group 2

> update amount coin of user and insert coupon owner that user buy coupon.
 - **URL** : `/api/coin/buyCoupon`
 - **Method** : `POST`
 - **Auth required** : `yes`
 - **Body** :
 ```
	 {
		 "pcode" : int
	 }
 ```
 - **Params** : `none`
#### Success Response
 - Status code : `201`
 - Response Body: 
 ```
	 {
		"coin" : int
	 }
 ```

### Get coin from Edqiz (Group 3)

> if user who gonna winner Rank 1,2,3, User will get coin for reward.
 - **URL** : `/api/coin/getCoinFromEdqiz`
 - **Method** : `POST`
 - **Auth required** : `yes`
 - **Body** :
 ```
	 {
		 "userIds" : String
	 }
 ```
 - **Params** : `none`
#### Success Response
 - Status code : `201`
 - Response Body: 
 ```
	 {
		"success" : boolean
	 }
 ```

## Group 10

### Fetch question preview
> Get the info of the question

- **URL** : `/api/grader/getPreviewQuestion`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"offset" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "id" : Integer,
	   "title" : String,
	   "description" : String,
	   "difficulty" : String
	}
	```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch  total number of questions

> Get the total number of questions

- **URL** : `/api/grader/countAllQuestion`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `none`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "count" : Integer
	}
	```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch announcement preview
>  Get info of the announcement

- **URL** : `/api/grader/getAnnouncement`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `none`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**: 

    ```json
    [
    	{
        	"id" : Integer,
        	"title" : String,
        	"time" : Timestamp,
        	"displayname" : String
        }
    ]
    ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch contest preview

>  Get info of the the contest

- **URL** : `/api/grader/getPreviewContest`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `none`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**: 

  ```json
  [
  	{
      	"conno": Integer,
      	"title": String,
      	"conruletype": String,
      	"starttime": Timestamp,
      	"endtime": Timestamp,
      	"status": Boolean
      }
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch detail of the contest

>  Get the detail of the contest

- **URL** : `/api/grader/getContestDetail`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**: 

  ```json
  {
      "conno": Integer,
      "title": String,
      "description": String,
      "conruletype": String,
      "starttime": String,
      "endtime": String,
      "status": Boolean,
      "displayname": String
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch the contest announcement

> Get the all visible announcements in the contest

- **URL** : `/api/grader/getContestAnnouncement`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:

    ```json
    [
    	{
        	"coannno": Integer,
        	"title": String,
        	"description": String,
        	"displayname": String,
        	"time": Timestamp
    	}
    ]
    ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch contest problems
> Get all the problem in the particular contest

- **URL** : `/api/grader/getContestProblem`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:

    ```json
    {
     	"id" : Integer,
     	"title" : String,
     	"conquestionno" : int,
     	"difficulty" : String,
        "description" : String
    }
    ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch contest submission
> Get all of the problem submissions in a particular contest

- **URL** : `/api/grader/getContestSubmission`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `"contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	[
		{
	    	"whentime" : Timestamp,
	    	"displayname" : String,
	    	"status" : String,
	    	"conquestionno" : Integer,
	    	"language" : String,
	        "time" : Integer,
	        "memory" : Integer,
	        "score" : Integer
	  	}
	]
	```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

  

### Fetch question tags
> Get all of the question tags 

- **URL** : `/api/grader/getQuestionTag`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	[
		{
	    	"tagid" : Integer,
	    	"tagname" : String
		}
	]
	```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```



### Fetch Question by tag

	> Get the questions by tag

- **URL** : `/api/grader/getQuestionByTag`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"tag": String`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "tagid" : Integer,
	   "title" : String,
	   "description" : String,
	   "difficulty" : String
	}
	```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	


### Fetch preview of the contest home page
> Get the overview details of the contest 

- **URL** : `/api/grader/getHomePreviewContest`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:

    ```json
    {
     	"conno": Integer,
     	"title": String,
     	"description": String,
     	"conruletype": String,
    	"starttime": Timestamp,
    	"endtime": Timestamp
    }
    ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

### Fetch announcement by id

> Get the announcement details from the id of the announcement

- **URL** : `/api/grader/getAnnouncementById`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"id" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  {
   	"conno": Integer,
   	"title": String,
   	"description": String,
   	"conruletype": String,
  	"starttime": Timestamp,
  	"endtime": Timestamp
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  top six of OI ranking

> Get the first six people from OI ranking

- **URL** : `/api/grader/getOIRankingTopSix`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `none`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  [
    {
      "name" : String,
      "totalcorrect" : Integer,
      "avatar" : URL
    }
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  top six of ACM Ranking

> Get the first six people from OI ranking

- **URL** : `/api/grader/getACMRankingTopSix`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `none`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  [
      {
          "name": String,
      	"totalcorrect": Integer,
      	"avatar": URL
      }
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  contest announcement detail

> Get the detail of the announcement in the cotests

- **URL** : `/api/grader/getContestAnnouncementDetail`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"id" : Integer, "contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  {
      "coannno": Integer,
      "title": String,
      "description": String,
      "displayname": String,
      "time": Timestamp
    }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  contest question details 

> Get the details of the problem in the contest

- **URL** : `/api/grader/getContestQuestionDetail`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"id" : Integer, "contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  {
      "conquestionno": Integer,
      "id": Integer,
      "title": String,
      "description": String,
      "hint": String,
      "intputdes": String,
      "outputdes": String,
      "timelimit": Integer,
      "memorylimit": Integer,
      "difficulty": String,
      "ruletype": String,
      "displayname": String
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  question test cases

> Get all of the test cases of the question

- **URL** : `/api/grader/getQuestionTestCase`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"id" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  [
      {
      	"questionid": Integer,
      	"sampleno": Integer,
      	"intput": String,
      	"output": String
  	}
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  question details

> Get the details of the problem that is not in the contest

- **URL** : `/api/grader/getQuestionDetail`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"id" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  {
      "id": Integer,
      "title": String,
      "description": String,
      "hint": String,
      "intputdes": String,
      "outputdes": String,
      "timelimit": Integer,
      "memorylimit": Integer,
      "difficulty": String,
      "ruletype": String,
      "displayname": String
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  question submissions

> Get all of the submissions of that problem

- **URL** : `/api/grader/getQuestionSubmission`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `"questionId" : Integer, "userId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  [
      {
      	"score": Integer,
      	"status": String,
      	"time": Integer,
      	"memory": Integer,
      	"displayname": String,
      	"whentime": Timestamp
    	},
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  number of all questions with tag

> Get the number of all questions that have that tag

- **URL** : `/api/grader/getCountQuestionByTag`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"tag" : String`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  {
   	"count" : Integer	
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Fetch  top five ranks in the contest

> Get name and score of the top five users in the contest

- **URL** : `/api/grader/getContestRanking`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `"contestId" : Integer`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

  **Response Body**:

  ```json
  [
      {
          "displayname" : String
          "totalscore" : Integer
      }
  ]
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

### Submit the question attempt

> Sent the code to the online compiler.

- **URL** : `/api/grader/submission`

- **Method** : `POST`

- **Auth required** : `Yes`

- **Parameters** : `None`

- **Body** : 

  ```json
  {
    "source_code": <base64 encode source-code>,
    "problem_id": <Integer>,
    "language": <Java|C|C++|Python3|Python2>
  }
  ```

#### Success Response

- **Status code** : `201`

  **Response Body**: 

  ```json
  {
    "attemptId" : Integer
    "tokens" : String <base64>
  }
  ```

#### Error Response

- **Status code** : `400`

  **Response Error** :

  ```json
  {
  	"message" : "Error"
  }
  ```

​	

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

### getCategories

> Get Categories

- **URL** : `/api/package/getCategories`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



#### Success Response

- **Status code** : `200`

    **Response Body**: ```{cateid: <integer>, cate_name: <varchar>}```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`
  

### createPackage

> Create package

- **URL** : `/api/package/createPackage`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{packagename: <char>, instructorid: <uuid> ,discount: <numeric>, ispublic: <boolean>, detail: <varchar>, image: <varchar>, cateid: <integer>, packageid: <uuid>,  courseid: <uuid>}`



#### Success Response

- **Status code** : `200`

    **Response Body**: `None`
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`
  
  
  
### deletePackage

> Delete package

- **URL** : `/api/package/delete/package`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{packageid: <uuid>}`



- **Status code** : `200`

    **Response Body**: `None`
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getPackage

> Get package

- **URL** : `/api/package/getPackage`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{ package: {packageid: <uuid>, packagename: <char>, instructorid: <uuid> ,firstname: <varchar>, lastname: <varchar>, discount: <numeric>, detail: <varchar>, image: <varchar>, price: <nemeric> }, courseCount: {courseid: <uuid> , coursename: <varchar>, firstname: <varchar>, lastname: <varchar>,coursepicture: <varchar>, avatar: <varchar>}, instructorList:{firstname: <varchar>, lastname: <varchar>, avatar: <varchar>}, courseList:{courseid: <uuid> , coursename: <varchar>, firstname: <varchar>, lastname: <varchar>,coursepicture: <varchar>, avatar: <varchar>}}```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getAllPackage

> Get all package

- **URL** : `/api/package/getAllPackage`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{instructorid: <uuid>, userid: <uuid> ,packagename: <char>, detail: <varchar>, image: <varchar>, discount: <numeric>, ispublic: <boolean>, cateid: <integer>, firstname: <varchar>, lastname: <varchar> }```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getCoursesOfCreatingPackage

> Get course of creating package

- **URL** : `/api/package/getCoursesOfCreatingPackage`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{courseid: <uuid> , coursename: <varchar>, coursepicture: <varchar>, price: <numeric>,totalPrice: {price: <numeric>}}```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### upload

> Upload package picture

- **URL** : `/api/package/uploadPackagePic`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: `None`
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getCourses

> Get course 

- **URL** : `/api/package/courses`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{courseid: <uuid> , coursename: <varchar>, coursepicture: <varchar>, price: <numeric>, firstname: <varchar>, lastname: <varchar>}```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getCourseFromIds

> Get course from ID

- **URL** : `/api/package/coursesFromIds`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{courseid: <uuid> , coursename: <varchar>, price: <numeric>}```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`
  
  
  
### getInstructorPackage

> Get instructor package

- **URL** : `/api/package/getInstructorPackage`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{price: <numeric>, packageid: <uuid>, packagename: <char>, discount: <numeric>, ispublic: <boolean>, detail: <varchar>, image: <varchar>, cateid: <integer>, cate_name: <varchar> }```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getNumCourses

> Get number of courses

- **URL** : `/api/package/numCourses`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{count: {coursename: <varchar>, courseid: <uuid> ,coursedescription: <varchar>, coursepicture: <varchar>, samplevideo: <varchar>, price: <numeric>, languege: <varchar>, havecert: <boolean>, ownerid: <uuid>, status: <varchar>, certpath: <varchar>} }```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### publishPackage

> Show publish package

- **URL** : `/api/package/publishPackage`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{packageid: <uuid>}`



- **Status code** : `200`

    **Response Body**: ```{packages: {ispublic: <boolean>} }```
    
#### Error Response

- **Status code** : `500`

  **Response Error** : `None`



### getAllCourse

> Get all course

- **URL** : `/api/course/getAllCourse`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{coursename: <varchar>, courseid: <uuid> ,coursedescription: <varchar>, coursepicture: <varchar>, samplevideo: <varchar>, price: <numeric>, languege: <varchar>, havecert: <boolean>, ownerid: <uuid>, status: <varchar>, certpath: <varchar>, instructorid: <uuid>, userid: <uuid> , isverified: <boolean>, createat: <timestamp>, approveat: <timestamp>, approver: <uuid>, avatar: <varchar>, wallpaper: <varchar>, biography: <varchar>, firstname: <varchar>, lastname: <varchar>, birthdate: <date>, initial: <varchar>, phoneno: <varchar>, display: <varchar>, bio: <varchar>,updateat: <timestamp>,cataid: <integer>, cataname: <varchar>, courseid: <uuid>}```
    
#### Error Response

- **Status code** : `400`

  **Response Error** : `None`



### searchCourse

> Search course

- **URL** : `/api/course/search`
- **Method** : `POST`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{ data: {coursename: <varchar>, courseid: <uuid> ,coursedescription: <varchar>, coursepicture: <varchar>, samplevideo: <varchar>, price: <numeric>, languege: <varchar>, havecert: <boolean>, ownerid: <uuid>, status: <varchar>, certpath: <varchar>}}```
    
#### Error Response

- **Status code** : `404`

  **Response Error** : `None`
  
  
  
### getCourse

> Get course

- **URL** : `/api/course/getCourse`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{ firstname: <varchar>, lastname: <varchar>, coursename: <varchar>, coursepicture: <varchar>,  price: <numeric>, ownerid: <uuid>, courseid: <uuid>}```
    
#### Error Response

- **Status code** : `400`

  **Response Error** : `None`
  
  

  
### getCategory

> Get category

- **URL** : `/api/course/getCategory`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{ category: {cataname: <varchar>}}```



### searchCategory

> Search category of course

- **URL** : `/api/course/categorySearch/:cataname`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `{cataname: <varchar>}`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{coursename: <varchar>, courseid: <uuid> ,coursedescription: <varchar>, coursepicture: <varchar>, samplevideo: <varchar>, price: <numeric>, languege: <varchar>, havecert: <boolean>, ownerid: <uuid>, status: <varchar>, certpath: <varchar>, instructorid: <uuid>, userid: <uuid> , isverified: <boolean>, createat: <timestamp>, approveat: <timestamp>, approver: <uuid>, avatar: <varchar>, wallpaper: <varchar>, biography: <varchar>, firstname: <varchar>, lastname: <varchar>, birthdate: <date>, initial: <varchar>, phoneno: <varchar>, display: <varchar>, bio: <varchar>,updateat: <timestamp>,cataid: <integer>, cataname: <varchar>, courseid: <uuid>}```
    
#### Error Response

- **Status code** : `404`

  **Response Error** : `None`



### createReview

> Create review

- **URL** : `/api/review/create`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `{userid: <uuid>, courseid: <uuid>, reviewrate: <numeric>, comment: <char>, date: <date>}`



- **Status code** : `201`

    **Response Body**: `None`



### getReview

> Get review

- **URL** : `/api/review`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`



- **Status code** : `200`

    **Response Body**: ```{ reviewrate: <numeric>, count:{ reviewrate: <numeric>, comment: <char>, date: <date>, displayname: <varchar>, avatar: <varchar> }, data:{ reviewrate: <numeric>, comment: <char>, date: <date>, displayname: <varchar>, avatar: <varchar> } }```



## Group 14

### Fetch Global Event
> Get the info of the global event

- **URL** : `/api/event/getGlobalEvent`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "eventid": <Integer>,
	   "title": String,
	   "startdate": date,
	   "enddate": date,
	   "starttime": time,
	   "endtime": time,
	   "detail": String,
	   "place": String,
	   "lastupdate": timestamp,
	   "typeid": <Integer>,
	   "adminid": <Integer>
	}
	```

### Fetch Course Event
> Get the info of the course event

- **URL** : `/api/event/getCourseEvent`
- **Method** : `GET`
- **Auth required** : `No`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "eventid": <Integer>,
	   "courseid": <Integer>,
	   "instructorid": <Integer>,
	   "title": String,
	   "startdate": date,
	   "enddate": date,
	   "starttime": time,
	   "endtime": time,
	   "datail": String,
	   "place": String,
	   "lastupdate": timestamp,
	   "typeid": <Integer>
	}
	```
	
### Fetch Event In Month Year
> Search event by month and year

- **URL** : `/api/event/getEventInMonthYear`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "startdate": date,
	   "enddate": date
	}
	```

### Fetch Event In Month Year
> Search event by month and year by Admin

- **URL** : `/api/event/getAdminEventInMonthYear`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "startdate": date,
	   "enddate": date
	}
	```

### Fetch Event
> Get the info of the event

- **URL** : `/api/event/getEvent`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `"eventid": <Integer>`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "eventid": <Integer>,
	   "courseid": <Integer>,
	   "instructorid": <Integer>,
	   "title": String,
	   "startdate": date,
	   "enddate": date,
	   "starttime": time,
	   "endtime": time,
	   "detail": String,
	   "place": String,
	   "lastupdate": timestamp,
	   "typeid": <Integer>
	}
	```

### Fetch Student Course
> Get the info of the course who student enrolled

- **URL** : `/api/event/getMyCourse`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "courseid": <Integer>,
	   "coursename": String
	}
	```

### Fetch Admin Event
> Get the info of the admin event

- **URL** : `/api/event/getAdminEvent`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `"eventid": <Integer>`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "eventid": <Integer>,
	   "title": String,
	   "startdate": date,
	   "enddate": date,
	   "starttime": time,
	   "endtime": time,
	   "detail": String,
	   "place": String,
	   "lastupdate": timestamp,
	   "typeid": <Integer>,
	   "adminid": <Integer>
	}
	```
	
### Fetch Overview Each Day Event by Instructor
> Get the info of the overview each day event by instructor

- **URL** : `/api/event/getEventbyDate`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `"date": date`
- **Body** : `None`

#### Success Response

- **Status code** : `200`

    **Response Body**:
    
	```json
	{
	   "title": String,
	   "startdate": date,
	   "enddate": date
	}
	```

### Create Course Event by Instructor
> Create Course Event

- **URL** : `/api/event/createEvent`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "title": String,
		"startdate": date,
		"enddate": date,
		"starttime": time,
		"endtime": time,
		"datail": String,
		"place": String,
		"instructorid": <Integer>,
		"courseid": <Integer>
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`

### Create Global Event by Admin
> Create Global Event

- **URL** : `/api/event/createAdminEvent`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "title": String,
		"startdate": date,
		"enddate": date,
		"starttime": time,
		"endtime": time,
		"datail": String,
		"place": String,
		"adminid": <Integer>
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`

### Edit Event by Instructor
> Edit event by instructor

- **URL** : `/api/event/eEvent`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "title": String,
		"startdate": date,
		"enddate": date,
		"starttime": time,
		"endtime": time,
		"datail": String,
		"place": String
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`

### Edit Event by Admin
> Edit event by admin

- **URL** : `/api/event/eAdminEvent`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "title": String,
		"startdate": date,
		"enddate": date,
		"starttime": time,
		"endtime": time,
		"datail": String,
		"place": String
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`
	
### Delete Global Event by Admin
> Delete Global Event

- **URL** : `/api/event/dAdminEvent`
- **Method** : `DELETE`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "id": String
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`

### Delete Course Event by Instructor
> Delete Course Event

- **URL** : `/api/event/dEvent`
- **Method** : `DELETE`
- **Auth required** : `Yes`
- **Parameters** : `None`
- **Body** : { "id": String
		}

#### Success Response

- **Status code** : `200`
	
	**Response Body**: `None`
	
## Group 15
#### Fetch Wishlist
> Get Wishlist

- **URL** : '/api/user/getWishlist'
- **Method** : `GET`
- **Auth required** : `YES`
- **Parameters** : `condition : <String>`
- **Body** : `NONE`
		
#### Success Response
	
- **Status code** : `200`
	
	**Response Body**: {
	"userid":  String,
	"courseid": String,
	"addtime":  datetime,
	"coursename":  String,
	"coursepicture":  String,
	"price" : int ,
	"firstnname" : String ,
	"lastname" : String 
	}
	
	
#### Fetch My Course
> Get Purchased Courses for User

- **URL** : `/api/user/getMycourse`
- **Method** : `GET`
- **Auth required** : `YES`
- **Parameters** : `condition : <String> , finish : <String> , orderby : <datetime>`
- **Body** : `NONE`

#### Success Response
	
- **Status code** : `200`

	**Response Body**: {  
	"userid" :  String,
	"courseid": String,
	"addtime" : datetime,
	"lastvisit" : datetime,
	"isfinished" : boolean,
	"coursename" : String,
	"coursepicture" : String,
	"firstname" : String ,
	"lastname" : String
	}
	
#### Delete Wishlist
> Delete Wishlist
- **URL** : `/api/user/deleteWishlist`
- **Method** : `POST`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : `NONE`

#### Success Response
	
- **Status code** : `200`

	**Response Body** : `NONE`
	
#### Fetch Profile
> Get Profile
- **URL** : `/api/user/getProfile`
- **Method** : `GET`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : `NONE`

#### Success Response
	
- **Status code** : `200`
	
	**Response Body** : {
	"avatar" : String,
	"firstname" : String,
	"lastname" : String,
	"email" : String,
	"birthdate" : datetime,
	"createat" : datetime,
	"bio" : String , 
	"phoneno" : String
	}
	
#### Edit Profile
> Edit Profile
- **URL** : `/api/user/postEditProfile`
- **Method** : `PATCH`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : { `avatar : <String> , firstname : <String> , lastname : <String> , birthdate : <datetime> , bio : <String>` }

#### Success Response
	
- **Status code** : `200`

	**Response Body** : `NONE`

#### Fetch CheckPassword
> Check the password
- **URL** : `/api/user/getCheckPassword`
- **Method** :	`GET`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : { `password : <String>} 

#### Success Response
	
- **Status code** : `200`

	**Response Body** : {
	"match" : boolean
	}
	
#### Change Password
> Change current password into new one
- **URL** : `/api/user/postNewPassword`
- **Method** :  `PATCH`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** :  { `password : <String>}

#### Success Response
	
- **Status code** : `200`

	**Response Body** : `NONE`
	
#### Upload Picture 
> Upload profile picture
- **URL** : `/api/user/upload/picture
- **Method** :  `POST`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : { `files: <pictureFiles> ` }

#### Success Response
- **Status code** : `200`

	**Response Body** : 
	{  "linkUrl": String ,
	   "fieldname" : String 
	  }
#### Fetch Certificate
> Get Certificate
- **URL** : `/api/user/certificate`
- **Method** :  `GET`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : `NONE`
#### Success Response
	
- **Status code** : `200`
	
	**Response body** : {
	"firstName" : String,
	"lastName" : String,
	"courseid": String,
	"courseName" : String,
	"finishDate" : datetime
	}

#### Download Certificate
> Download Certificate
- **URL** : `/api/user/certificate`
- **Method** :  `POST`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : { `courseid : <String>` }

#### Success Response
	
- **Status code** : `200`
	
	**Response body** : {
	"firstname" : String,
	"lastname" : String,
	"coursename" : String,
	"finishdate" : datetime
	}
	
#### Change My Course
> Change user's course
- **URL** : `/api/user/postMycourse`
- **Method** :	`POST`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : { courseid : String }

#### Success Response
	
- **Status code** : `200`
	
	**Response body** : `NONE`
		
#### Check Wishkist
> Check Wishlist
- **URL** : `/api/user/checkWishlist`
- **Method** :	`POST`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : {`courseid : <String>}


#### Success Response
	
- **Status code** : `200`

	**Response body** : {
	"checkwishlist" : boolean
	}
	
#### Update Lastvisit Mycourse
> Update the last visiting time of my course 
- **URL** : `/api/user/updateLastvisitMyCourse`
- **Method** :	`PATCH`
- **Auth required** : `Yes`
- **Parameters** :  `NONE`
- **Body** : {`courseid : <String>}

#### Success Response
	
- **Status code** : `200`

	**Response body** : `NONE`
	
#### Update Finish Mycourse
>
- **URL** : `/api/user/updateFinishMyCourse`
- **Method** :	`PATCH`
- **Auth required** : `Yes`
- **Parameters** : `NONE`
- **Body** : {`courseid : <String>}

#### Success Response
	
- **Status code** : `200`

	**Response body** : `NONE`
