# ems
it's an Email Managment System. from where you can register and use thair Api's to send emails through your own pannel. Completely in Core php and Sql based with 100% Oop based Code. 
> note
 ```
 make sure you have `Email Catcher in serve mode`.
```
---
# Email Service EndPoint

toc_footers:
  - <a href='http://localhost:8888/web/view.php?route=login'>Sign Up for a Secret Key</a>

includes:
  - errors

search: true
---
#Email Service End Point
## Introduction

The Email Service End point is helps you to send multiples Emails from your website anywhere any time. Fully Secured and Manageable Service by Email Service. 

## HTTPs Requests And Method `Email Send End point`

 Method:
  `POST`

 End point:
  `http://localhost:8888/web/apis.php?route=SendEmail`  

> Use Ajax to Send Data:

```javascript

    $.ajax({
    type: "POST",
    url: "['End Point URL']",
    data: ['Json Object'],
    success: function(){},
    dataType: "json",
    contentType : "application/json"
});

```

## Request Data Format `Email Send End Point`

#### Request Data Must be in Json Formate

#### Headers Required for End Point

> The Data Must be in This Formate:

```json

[
  {
    "request_reference": "xxxxxxxxxx",
    "webhook_url": "example@example.com",
    "data": {
        "from": "example.from@example.com",
        "to": "example.to@example.com",
        "cc": "example.cc@example.com",
        "bcc": "example.bcc@example.com",
        "subject": "Your Email Subject",
        "body": "Your Email Body"
      }
  }
]

```
> Autherized Header Required (For Security)

```js

  Header Name |                   Vaues                           |
  ----------- | ------------------------------------------------- |
   Username   | [Your Api Key (Create in your Account)]           |
   Password   | [Your Account Secret Key ( Find in Your Profile)] |
  
```
This EndPoint Retrive Data Response.

#### Query Parameters

Parameter | Description |
--------- | ----------- |
request_reference | Must be Unique for each request to identify the request. |
webhook_url | To receive notifications for your Email Request EndPoint. |
data['from'] | Email Address from where you want to send email (Must be Registered on EmailService.com) |
data['to'] | Email Adderss Where you want to send your email. |
data['cc'] | Email Address to send a Carban Copy to there. |
data['bcc'] | Email Address to Wher You want to send Blind carbon copy |
data['subject'] | Email Subject, About Your Email |
data['body'] |  Your Email Body Could be in HTML |

<aside class="warning">Remember: Use Unique Request Reference for each Request.</aside>

<aside class="success">
Remember — Oath Basic is Implemented!
</aside>

## Respose `Email Send End Point`

> The Data Will Send Response In This Formate:

```json

  {
    "status": "Error",
    "error": {
        "key": "409",
        "message": "Duplicate Request Reference"
    },
    "description": "Request Reference Must Be Unique. Use a Different Request Reference",
    "signature": "ea2ff59255a1f6f71610860f233c5de9287b4b125c3f41d5d1c25b1b08dbfd1d"
}

```

 Key | Value |
 --- | ----- |
 status | Request Status Invalid, Error or Received |
 error | array of response Code + response Message |
 description | A Breaf Info About Your Error |
 signature | A combination of your Request + Secret Key `to validate your Request Secretly`

<aside class="notice">
    Secret Key is Created by shah256 with [Your Request Data] cancate [Your Secret Key] for Validate Your Request.
</aside>



## How it Works `Email Send End Point`

###Step 1
  Register to <siteURl> `http://localhost:8888/web`
###Step 2
  Verify Your `Email`, `Number` and `Identity` to Access Dashboard.
<small>You will receive Email Notification on your Email and Code on Your Phone Number</small>
###Step 3
  Buy a Monthly Plan for Email Service. In Plans.

  IN Sidebar > Plans

<small>Expire After 30 Days Automatically</small>
###Step 4 
  --> Create a Temporary Secret Key to Use the Api.

<small>Visit Profile (Dropdown) > Create Api Key. (You can send this In Header with you Secret Key)</small>

`You will find your Secret Key in Profile Section`




-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------




# Check Status End Point

## Introduction

This EndPoint Will Show You Response For Each Request.

## HTTPs Requests And Method `Request Status End Point`

 Method:
  `POST`

 End point:
  `http://localhost:8888/web/apis.php?route=EmailStatus`  

> Use Ajax to Send Data:

```js
   
    $.ajax({
    type: "POST",
    url: "['End Point URL']",
    data: ['Json Object'],
    success: function(){},
    dataType: "json",
    contentType : "application/json"
});

```

## Request Data Format `Request Status End Point`

#### Request Data Must be in Json Formate

> The Data Must be in This Formate:

```json

  {
    "request_reference": "999765432345"
  }

```

#### Headers Required for End Point


> Autherized Header Required (For Security)

```js

  Header Name |                   Vaues                           |
  ----------- | ------------------------------------------------- |
   Username   | [Your Api Key (Create in your Account)]           |
   Password   | [Your Account Secret Key ( Find in Your Profile)] |
  
```
This EndPoint Retrive Data Response.

#### Query Parameters

Parameter | Description |
--------- | ----------- |
request_reference | Must Be Your Request Reffrence. |

<aside class="warning">Remember: Use Unique Request Reference for each Request.</aside>

<aside class="success">
Remember — Oath Basic is Implemented!
</aside>

## Respose `Request Status End Point`

> The Data Will Send Response In This Formate:

```json

  {
    "status": "Success",
    "success": {
        "key": 200,
        "message": "Request Reference Found"
    },
    "Request_Status": "processed"
  }

```

 Key | Value |
 --- | ----- |
 status | Request Status Invalid, Error or Received |
 error | array of response Code + response Message |
 description | A Breaf Info About Your Error |
 Request Status | Response About Your Email |



## How it Works `Request Status End Point`

You Must Have A Plan to use the First Api.
You Must Have Atleast one Api Request.
After Using Email Send End Point You Will Find Your Email Status By This End point or Webhook Url.
You Must have a Valid Request Refference For Your Status.
 
<aside class="notice">Visit Profile (Dropdown) > Create Api Key. (You can send this In Header with you Secret Key). `You will find your Secret Key in Profile Section`</aside>

-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------

#Daily Report End Point

## Introduction

This EndPoint Will Show You Report According To Your Date Submitted Day.

## HTTPs Requests And Method `Daily Report End Point`

 Method:
  `POST`

 End point:
  `http://localhost:8888/web/apis.php?route=Report`  

> Use Ajax to Send Data:

```js
   
    $.ajax({
    type: "POST",
    url: "['End Point URL']",
    data: ['Json Object'],
    success: function(){},
    dataType: "json",
    contentType : "application/json"
});

```

## Request Data Format `Daily Report End Point`

#### Request Data Must be in Json Formate

> The Data Must be in This Formate:

```json

  {
    "date": "2019-12-13"
  }

``` 

<aside class="notice">
    Please Use Y-m-d Formate For Your Date.
</aside>

#### Headers Required for End Point


> Autherized Header Required (For Security)

```js

  Header Name |                   Vaues                           |
  ----------- | ------------------------------------------------- |
   Username   | [Your Api Key (Create in your Account)]           |
   Password   | [Your Account Secret Key ( Find in Your Profile)] |
  
```
This EndPoint Retrive Data Response.

#### Query Parameters

Parameter | Description |
--------- | ----------- |
date | A Date After Your Registration. |

<aside class="success">
Remember — Oath Basic is Implemented!
</aside>

## Respose `Daily Report End Point`

> The Data Will Send Response In This Formate:

```json

  {
    "status": "Success",
    "used_emails": "12",
    "date": "2019-12-13"
  }

```

 Key | Value |
 --- | ----- |
 status | Request Status Invalid, Error or Success |
 Used Emails | No of Used Emails of Relivent Date |
 Date | The Input Date in Back Response |



## How it Works `Daily Report End Point`

You Must Have A Plan to use the First Api.
You Must have a Valid Request Refference For Your Status.
 
<aside class="notice">Visit Profile (Dropdown) > Create Api Key. (You can send this In Header with you Secret Key). `You will find your Secret Key in Profile Section`</aside>


<aside class="success">
    You Can Also find the all 3 Endpoint Links Under Your Profile Details to access them.
</aside>


