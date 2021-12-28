<h1 align="center"> <b>Postman - Integration Test</b> </h1>

> 🔗  https://www.getpostman.com/collections/668115399cc0b1e28a0f

 ## ![postman](https://user-images.githubusercontent.com/35347777/147509734-b58b6d8d-1780-4d9b-8c4f-ffcb545d3a1d.png) Postman

 #### 👨🏻‍💻 (cityName=ankara)
*** 


<details>
  <summary>(<i>Testi görüntülemek için tıklayın</i>)</summary>

```javascript
var jsonData = pm.response.json();
var size = Object.keys(jsonData).length;  
var responsLimit = 1000;
var responseTime = pm.response.responseTime; 


tests["Size control"] = size == 6;     
tests["pageItemsCount type control"] = typeof(jsonData.paginationResponse.pageItemsCount) === "number"; 
tests["totalItemsCount type control"] = typeof(jsonData.paginationResponse.totalItemsCount) === "number"; 
tests["totalPageCount type control"] = typeof(jsonData.paginationResponse.totalPageCount) === "number"; 
tests["totalCount type control"] = typeof(jsonData.totalCount) === "number"; 
tests["averageRate type control"] = typeof(jsonData.averageRate) === "number"; 
tests["averageAllReviewsRate type control"] = typeof(jsonData.averageAllReviewsRate) === "number"; 


pm.test("StarDtos types control",() => { 
    jsonData.starDtos.map((starDtos)=> { 
        pm.expect(starDtos.point).to.be.a("number")
        pm.expect(starDtos.percent).to.be.a("number") 
        pm.expect(starDtos.count).to.be.a("number") 
    })
});  

pm.test("ReviewDtos types control",() => { 
    jsonData.reviewDtos.map((reviewDtos)=> { 
        pm.expect(reviewDtos.name).to.be.a("string")
        pm.expect(reviewDtos.comment).to.be.a("string") 
        pm.expect(reviewDtos.rating).to.be.a("number")
        pm.expect(reviewDtos.createOn).to.be.a("string")
        pm.expect(reviewDtos.regionName).to.be.a("string")
        pm.expect(reviewDtos.cityName).to.be.a("string")
    })
});  

pm.test("Check all cityName 'ANKARA'",() => { 
    jsonData.reviewDtos.map((reviewDtos)=> {  
        pm.expect(reviewDtos.cityName).to.be.eql("ANKARA")
    })
});  
    
pm.test("Status code is 200", function () {
  pm.response.to.have.status(200);
}); 

pm.test("Status code name has string", () => {
  pm.response.to.have.status("OK");
});

pm.test("Check response time", () => {  
  if (responseTime > responsLimit) {       
    console.log("Response time was longer than " + responsLimit + " ms " + "(" + responseTime + " ms)" + " / Response Date: " + pm.response.headers.get("Date"));
  }
  pm.expect(responseTime).to.be.below(responsLimit); 
});

pm.test("Response should not be error", function () { 
    pm.response.to.not.be.error; 
});

pm.test("Response must be valid", function(){
    pm.response.to.be.ok;
});
```

</details>

![cityName_Ankara](https://user-images.githubusercontent.com/35347777/147562838-de596310-806c-448b-916d-d57cdaed450f.PNG)

 #### 👨🏻‍💻 (cityName=istanbul)
***


<details>
  <summary>(<i>Testi görüntülemek için tıklayın</i>)</summary>

```javascript
var jsonData = pm.response.json();
var size = Object.keys(jsonData).length;  
var responsLimit = 1000;
var responseTime = pm.response.responseTime; 


tests["Size control"] = size == 6;     
tests["pageItemsCount type control"] = typeof(jsonData.paginationResponse.pageItemsCount) === "number"; 
tests["totalItemsCount type control"] = typeof(jsonData.paginationResponse.totalItemsCount) === "number"; 
tests["totalPageCount type control"] = typeof(jsonData.paginationResponse.totalPageCount) === "number"; 
tests["totalCount type control"] = typeof(jsonData.totalCount) === "number"; 
tests["averageRate type control"] = typeof(jsonData.averageRate) === "number"; 
tests["averageAllReviewsRate type control"] = typeof(jsonData.averageAllReviewsRate) === "number"; 


pm.test("StarDtos types control",() => { 
    jsonData.starDtos.map((starDtos)=> { 
        pm.expect(starDtos.point).to.be.a("number")
        pm.expect(starDtos.percent).to.be.a("number") 
        pm.expect(starDtos.count).to.be.a("number") 
    })
});  

pm.test("ReviewDtos types control",() => { 
    jsonData.reviewDtos.map((reviewDtos)=> { 
        pm.expect(reviewDtos.name).to.be.a("string")
        pm.expect(reviewDtos.comment).to.be.a("string") 
        pm.expect(reviewDtos.rating).to.be.a("number")
        pm.expect(reviewDtos.createOn).to.be.a("string")
        pm.expect(reviewDtos.regionName).to.be.a("string")
        pm.expect(reviewDtos.cityName).to.be.a("string")
    })
});  

pm.test("Check all cityName 'ISTANBUL'",() => { 
    jsonData.reviewDtos.map((reviewDtos)=> {  
        pm.expect(reviewDtos.cityName).to.be.eql("ISTANBUL")
    })
});  
    
pm.test("Status code is 200", function () {
  pm.response.to.have.status(200);
}); 

pm.test("Status code name has string", () => {
  pm.response.to.have.status("OK");
});

pm.test("Check response time", () => {  
  if (responseTime > responsLimit) {       
    console.log("Response time was longer than " + responsLimit + " ms " + "(" + responseTime + " ms)" + " / Response Date: " + pm.response.headers.get("Date"));
  }
  pm.expect(responseTime).to.be.below(responsLimit); 
});

pm.test("Response should not be error", function () { 
    pm.response.to.not.be.error; 
});

pm.test("Response must be valid", function(){
    pm.response.to.be.ok;
});
```

</details>

![cityName_Istanbul](https://user-images.githubusercontent.com/35347777/147562923-ac690357-ad9f-41d9-8881-44f332052b04.PNG)

 #### 👨🏻‍💻 (cityName=van)
***
 

<details>
  <summary>(<i>Testi görüntülemek için tıklayın</i>)</summary>

```javascript
var jsonData = JSON.parse(responseBody);  
var size = Object.keys(pm.response.json()).length;  
var responsLimit = 1000;
var responseTime = pm.response.responseTime;


tests["Size control"] = size == 1;   
tests["Message type control"] = typeof(jsonData.message) === "string"; 
 

pm.test("Check response", function () {
    pm.expect(jsonData.message).is.eql("Not Found"); 
});

pm.test("Status code is 404", function () {
  pm.response.to.have.status(404);
}); 

pm.test("Status code name has string", () => {
  pm.response.to.have.status("Not Found");
});

pm.test("Check response time", () => {  
  if (responseTime > responsLimit) {       
    console.log("Response time was longer than " + responsLimit + " ms " + "(" + responseTime + " ms)" + " / Response Date: " + pm.response.headers.get("Date"));
  }
  pm.expect(responseTime).to.be.below(responsLimit); 
});

pm.test("API response contains the expected fields", () => { 
  pm.expect(jsonData).to.have.property("message", "Not Found");
});

pm.test("Response should be error", function () { 
    pm.response.to.be.error; 
});

pm.test("Response must be invalid", function(){
    pm.response.to.not.be.ok;
});
```

</details>

![cityName_Van](https://user-images.githubusercontent.com/35347777/147562968-ddab6706-1552-4cfb-83e8-4a335cc517e8.PNG)


 #### 👨🏻‍💻 (cityName is null)
***


<details>
  <summary>(<i>Testi görüntülemek için tıklayın</i>)</summary>

```javascript
var jsonData = JSON.parse(responseBody);  
var size = Object.keys(pm.response.json()).length;  
var responsLimit = 1000;
var responseTime = pm.response.responseTime;


tests["Size control"] = size == 1;   
tests["CityName type control"] = typeof(jsonData.cityName[0]) === "string"; 
 

pm.test("Check response", function () {
    pm.expect(jsonData.cityName[0]).is.eql("'cityName' can not be null."); 
});

pm.test("Status code is 400", function () {
  pm.response.to.have.status(400);
}); 

pm.test("Status code name has string", () => {
  pm.response.to.have.status("Bad Request");
});

pm.test("Check response time", () => {  
  if (responseTime > responsLimit) {       
    console.log("Response time was longer than " + responsLimit + " ms " + "(" + responseTime + " ms)" + " / Response Date: " + pm.response.headers.get("Date"));
  }
  pm.expect(responseTime).to.be.below(responsLimit); 
});

pm.test("Response should be error", function () { 
    pm.response.to.be.error; 
});

pm.test("Response must be invalid", function(){
    pm.response.to.not.be.ok;
});
```

</details>
 
![cityName_null](https://user-images.githubusercontent.com/35347777/147562986-f6d456e7-3de1-4d3d-b127-2118dda03719.PNG)


##  ![postman monitoring](https://user-images.githubusercontent.com/35347777/147594384-6d3a8248-fb31-450f-8f8c-e7a786057fcb.png) Postman Monitör

<details>
  <summary> (<i>Monitörü görüntülemek için tıklayın (8 saatlik veri)</i>)</summary>
 
![postman Monitör](https://user-images.githubusercontent.com/35347777/147594476-cd6de8b0-8069-4ccb-be51-ba08a37c5bf9.png)

</details>

  
##  ![newman](https://user-images.githubusercontent.com/35347777/147482415-33220019-78d5-4a50-8855-a2f8fe3b8070.png) Newman Raporu

Daha detaylı incelemek için [**buraya**](https://onurerdemiroglu.com.tr/html-reports/) tıklayınız.

<details>
  <summary> (<i>Raporu görüntülemek için tıklayın</i>)</summary>

![newman-html](https://user-images.githubusercontent.com/35347777/147485417-2e693dd6-3c73-42d5-af8a-52809219f02a.png)

</details>
 
##  ![1200px-Jenkins_logo svg](https://user-images.githubusercontent.com/35347777/147480987-e53e1e34-a6b5-4491-982f-d95c081112c5.png) Jenkins - Newman Konsol Çıktısı
 
<details>
  <summary> (<i>Raporu görüntülemek için tıklayın</i>)</summary>

![Jenkins-Newman](https://user-images.githubusercontent.com/35347777/147479410-95d8cf0e-93e4-4b8f-9785-b267de8ceaf5.png)

</details>