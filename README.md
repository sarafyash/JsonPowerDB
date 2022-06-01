# ***JsonPowerDB***

## Introduction 
JsonPowerDB **(JPDB)** is a database server offering REST API services for developers. It's a Real-time database which provides high-performance and is light-weight, Ajax-enabled, serverless, and simple to use.
JsonPowerDB is equally Easy and Fast when used with Server Side programming like Java, .NET, Python or PHP etc.


## Features of JsonPowerDB 

* JPDB is nimble, simple to use, in memory and real time.
* JPDB is schema free and is quite easy to maintain.
* JPDB provides serverless support for fast development and cuts time to market.
* JPDB is built around the world's fastest indexing engine PowerIndex.
* Has a webservices API and has a  low development cost.
* JPDB has multiple security layers.
* A single instance - Million Indexes.
* Inbuilt support for querying multiple databases.
* Serverside Native NoSQL - best performance.
* Multi-mode database - One solution to a variety of data.
* Minimizes Total Cost of Ownership.
* Maximum Data processing performance.
* Fills gaps from Database to Big-data.
* Pluggable with new Algorithms.

## Use Cases of JsonPowerDB 

* Any software application that needs backend DB.
    * Dynamic web-apps/Mobile/Desktop Apps.
* All RDBMS Use cases.
* All key-value Use cases.
* All document Use cases.
* Use cases which needs Time series/geospatial analytics.
* Real time application for data analytics.
* Live working HTML templates.

![Alt text]("C:\Users\saraf\Desktop\Screenshot 2022-06-01 131157.png"?raw=true "Title")

## JsonPowerDB API Commands

>IML (JsonPowerDB Index Manipulation Language) for Inserting , Deleting/Removing and Updating a record in Json data.


* **Http method : POST**
* **Base url : http://api.login2explore.com:5577**
* **End-point url : /api/iml**

### 1. PUT Command
#### Syntax of PUT Command
```HTML
{
    "token": <"connection-token">,
    "cmd": "PUT",
    <<"dbName": <"database-name">,>>
    <<"rel": <"relation-name">,>>
    <<"colsAutoIndex": <boolean-value>,>>
    <<"templateStr": <json-template-data>,>>
    "jsonStr": <json-data>
}
```
### 2. UPDATE Command
#### Syntax of UPDATE Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "UPDATE",
    <<"dbName": "database-name",>>
    <<"rel": "relation-name",>>
    "jsonStr": {
        <"record-no">: {
            <"column-name">: <"new-value">
        }
        <"record-no">: {
            <"column-name">: <"new-value">
        }
    }
}
```

### 3. Remove Command
#### Syntax of Remove Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "REMOVE",
    <<"dbName": <"database-name">,>>
    <<"rel": <"relation-name">,>>
    "record": <record-number | [record-number1,...],>
    "jsonStr" : {}
}
```

>IRL (JsonPowerDB Index Retrieval Language) - For Retrieve Json data.


* **Http method : POST**
* **Base url : http://api.login2explore.com:5577**
* **End-point url : /api/iml**

### 4. GET Command
#### Syntax of GET Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "GET",
    "dbName": <"database-name">,
    "rel": <"relation-name">,
    "jsonStr": {
        <"column-name">:<"column-value">
    }
}
```

### For More Json API Commands please visit - ***https://login2explore.com/jpdb/docs.html***


## *Web Project in NetBeans*

### Creating a Student Details Form with JPDB

```HTML
<!DOCTYPE html>

<html lang="en">

<head>
    <title>Bootstrap Example</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
</head>

<body>
    <div class="container">
        <h2> Student Details Form </h2>
        <form id="Student_Form" method="post">
            <div class="form-group">
                <span><label for="Student_ID">Student ID:</label> <label id="StudentIDMsg">
            </label></span>
                <input type="text" class="form-control" name="Student_ID" id="Student_ID" placeholder="Enter Student's ID" required>
            </div>

            <div class="form-group">
                <label for="Student_Name">Student Name:</label>
                <input type="text" class="form-control" id="Student_Name" placeholder="Enter Student's Name" name="Student_Name">
            </div>

            <div class="form-group">
                <label for="Student_Email">Email:</label>
                <input type="email" class="form-control" id="Student_Email" placeholder="Enter Student's Email" name="Student_Email">
            </div>

            <div class="form-group">
                <label for="Student_MobileNo">Student Mobile Number:</label>
                <input type="text" class="form-control" id="Student_MobileNo" placeholder="Enter Student's Mobile Number" name="Student_MobileNo">
            </div>

            <div class="form-group">
                <label for="Student_Address">Student Address:</label>
                <input type="text" class="form-control" id="Student_Address" placeholder="Enter Student's Address" name="Student_Address">
            </div>



            <input type="button" class="btn btn-primary" id="Student_Save" value="Submit" onclick="saveStudent();">
        </form>
    </div>

    <script>
        $("#Student_ID").focus();

        function validateAndGetFormData() {
            var Student_IDVar = $("#Student_ID").val();
            if (Student_IDVar === "") {
                alert("Student's ID Required Value");
                $("#Student_ID").focus();
                return "";
            }
            var Student_NameVar = $("#Student_Name").val();
            if (Student_NameVar === "") {
                alert("Student's Name is Required Value");
                $("#Student_Name").focus();
                return "";
            }
            var Student_EmailVar = $("#Student_Email").val();
            if (Student_EmailVar === "") {
                alert("Student's Email is Required Value");
                $("#Student_Email").focus();
                return "";
            }
            var Student_MobileNoVar = $("#Student_MobileNo").val();
            if (Student_MobileNoVar === "") {
                alert("Student's Mobile Number is Required Value");
                $("#Student_MobileNo").focus();
                return "";
            }
            var Student_AddressVar = $("#Student_Address").val();
            if (Student_AddressVar === "") {
                alert("Student's Address is Required Value");
                $("#Student_Address").focus();
                return "";
            }

            var jsonStrObj = {
                Student_ID: Student_IDVar,
                Student_Name: Student_NameVar,
                Student_Email: Student_EmailVar,
                Student_MobileNo: Student_MobileNoVar,
                Student_Address: Student_AddressVar,

            };
            return JSON.stringify(jsonStrObj);
        }

        function createPUTRequest(connToken, jsonObj, dbName, relName) {
            var putRequest = "{\n" +
                "\"token\" : \"" +
                connToken +
                "\"," +
                "\"dbName\": \"" +
                dbName +
                "\",\n" + "\"cmd\" : \"PUT\",\n" +
                "\"rel\" : \"" +
                relName + "\"," +
                "\"jsonStr\": \n" +
                jsonObj +
                "\n" +
                "}";
            return putRequest;
        }

        function executeCommand(reqString, dbBaseUrl, apiEndPointUrl) {
            var url = dbBaseUrl + apiEndPointUrl;
            var jsonObj;
            $.post(url, reqString, function(result) {
                jsonObj = JSON.parse(result);
            }).fail(function(result) {
                var dataJsonObj = result.responseText;
                jsonObj = JSON.parse(dataJsonObj);
            });
            return jsonObj;
        }

        function resetForm() {
            $("#Student_ID").val("")
            $("#Student_Name").val("");
            $("#Student_Email").val("");
            $("#Student_MobileNo").val("");
            $("#Student_Address").val("");
            $("#Student_ID").focus();
        }

        function saveStudent() {
            var jsonStr = validateAndGetFormData();
            if (jsonStr === "") {
                return;
            }
            var putReqStr = createPUTRequest("90938999|-31949289505418442|90940827", jsonStr, "New_Student_Record", "Student_Relation");
            alert(putReqStr);
            jQuery.ajaxSetup({
                async: false
            });
            var resultObj = executeCommand(putReqStr, "http://api.login2explore.com:5577", "/api/iml");
            alert(JSON.stringify(resultObj));
            jQuery.ajaxSetup({
                async: true
            });
            resetForm();
        }
    </script>
</body>

</html>
```

## References 

   * https://learn.login2explore.com/course/view.php?id=7
   * https://login2explore.com/jpdb/
   * https://github.com/BeAgarwal/JsonPowerDB
   * https://github.com/dbader/readme-template
   * https://github.com/prateek-mehra/JsonPowerDB
