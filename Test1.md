# API Documentation: SoundDate Profile Audio

**Base URL:** `https://api.sounddate.com

## Table of Contents
* [1. Uploading a Sound File](#1-uploading-a-sound-file)
* [2. Retrieving a List of Sound Files](#2-retrieving-a-list-of-sound-files)
* [3. Status Codes and Errors](#3-status-codes-and-errors)

## 1. Uploading a Sound File
Uploads a sound file to the User Profile.

* **Method:** `POST`
* **URL:** `https://api.sounddate.com/profile/sound`

### Query Parameters

| Parameter | Description | Type | Required | Notes |
| :--- | :--- | :--- | :--- | :--- |
| N/A | | | | |

### Headers

| Header Name | Required | Value | Description |
| :--- | :--- | :--- | :--- |
| `Authorization` | Yes | See Authorization section | The access token for the user session. |
| `Content-Type` | Optional| `audio/mpeg or audio/x-wav. Default is audio/mpeg.` | The format of the sound file to upload. |
| `Accept` | Optional| `application/json` | The format of the returned data. |

### POST Body
The sound file.
> **Note:** The sound file must be **5 minutes or shorter**.

### Sample Request
```http
POST https://api.sounddate.com/profile/sound
Authorization: Bearer {access token}
Content-Type: audio/mpeg
Accept: application/json
{sound file}
```
### Response Elements
The following table lists the response elements:

| Element | Description | Type | Notes |
| :--- | :--- | :--- | :--- |
| **id** | The ID of the new sound file | integer | |
| **length** | The length of the sound file | float | Length is in seconds. |

### Sample Response
**JSON Response**

```json
{
  "id": 3543,
  "length": 19.8
}
```
## 2. Retrieving a List of Sound Files

**Description:** Retrieves a list of profile sound file URLs and their lengths for the specified user.

### Resource Information
**Method:** `GET`  
**URL:** `https://api.sounddate.com/user/{user id}/profile/sound`  
**Note:** `{user id}` is the ID of the user whose profile contains the sound files.  

### Query Parameters
The following table lists the query parameters:

| Parameter | Description | Type | Required | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **sortOrder** | The order to return the sound file information. | String | Optional | Valid values: `mostRecent`, `earliest`, `shortest`, `longest`. <br> Default is `mostRecent`. |

**Notes on Sort Order:**
* `mostRecent`: returns the most recent sound files to the earliest.  
* `earliest`: returns the earliest sound files to the most recent. 
* `shortest`: returns the shortest sound files to longest. 
* `longest`: returns the longest sound files to the shortest. 

### Headers
The following table lists the required headers:

| Header Name | Description | Required | Values |
| :--- | :--- | :--- | :--- |
| **Authorization** | Access token | Required | See Authorization section |
| **Accept** | The format of the returned data | Optional | `application/xml` or `application/json`. <br> Default is `application/json`. |

### Sample Request
```http
GET https://api.sounddate.com/user/345354/profile/sound?sortOrder=shortest
Authorization: Bearer {access token}
Accept: application/json
```

### Response Elements
The following table lists the response elements:

| Element | Description | Type | Notes |
| :--- | :--- | :--- | :--- |
| **soundFiles** | List of sound file information | Array | |
| **id** | The ID of the sound file | integer | |
| **url** | The URL of the sound file | string | |
| **length** | The length of the sound file | float | The length in seconds. |

### Sample Response
**JSON Response**

```json
{
  "soundFiles": [
    {
      "id": 23456,
      "url": "https://api.sounddate.com/profile/sound/23456.mp3",
      "length": 11.2
    },
    {
      "id": 24559,
      "url": "https://api.sounddate.com/profile/sound/24559.mp3",
      "length": 19.8
    }
  ]
}
```
## 3. Status Codes and Errors
The following table lists the returned HTTP status codes.

| Code | Description | Notes |
| :--- | :--- | :--- |
| **200** | Ok | Request processed successfully (File uploaded or List retrieved). |
| **401** | Unauthorized | Authentication failed or token missing. |
| **404** | Not Found | The specified User ID was not found (for GET requests). | 
| **413** | Request Entity Too Large | Uploaded sound file is longer than 5 minutes.. |
