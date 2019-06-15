# Project-1 Reading-JSON-data-into-R
The vignette is about reading JSON data into R with an example that includes basic exploratory data analysis (summaries and graphs - more details on this later).


##What is JSON data
JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate. It is based on a subset of the JavaScript Programming Language, Standard ECMA-262 3rd Edition - December 1999. JSON is a text format that is completely language independent but uses conventions that are familiar to programmers of the C-family of languages, including C, C++, C#, Java, JavaScript, Perl, Python, and many others. These properties make JSON an ideal data-interchange language. [[Ref1](https://www.json.org/)]

JSON is built on two parts:keys and values. Together they make a key/value pair.   
   
Key: A key is always a string enclosed in quotation marks.  
Value: A value can be a string, number, boolean expression, array, or object.  
Key/Value Pair: A key value pair follows a specific syntax, with the key followed by a colon followed by the value. Key/value pairs are comma separated.[[Ref2](https://developers.squarespace.com/what-is-json)]    
    
In JSON, values must be one of the following data types:      

a string
a number
an object (JSON object)
an array
a boolean
null

JSON values cannot be one of the following data types:    
   
a function   
a date  
undefined      [[Ref3](https://www.w3schools.com/js/js_json_datatypes.asp)]    
    
    
##Reading JSON file into R   
###R Packages for JSON file
There are three popular packages that can be used to read JSON data: rjson, RJSONIO and jsonlite.  
    
rjson was first implemented for R in 2007 by Alex Couture-Beil. It allows R users to convert JSON objects into R object and vice-verse. There are three functions available under rjson package: fromJSON, toJSON and newJSONParser.   
    
RJSONIO started with a GitHub project by Duncan Temple Lang in 2010. It also provides facilities for reading and writing data in JSON. This allows R objects to be inserted into JavaScript/ECMAScript/ActionScript code and allows R programmers to read and convert JSON content to R objects. It could be used as an alternative to rjson package however it doesn’t use S4/S3 methods. Given this, RJSONIO is extensible, allowing others to define S4 methods for different R classes/types, as well as allowing the caller to specify a different callback handler. Unlike rjson package, RJSONIO package uses a C++ library - libjson, rather than implementing yet another JSON parser so that parsing would be faster than pure interpreted R code. There are three primary functions available in this package: fromJSON, toJSON and asJSVars.    
    
jsonlite is commonly known to R community starting from a ‘fork’ of RJSONIO package, starting from 2013 but has been completely rewritten in recent versions. Like RJSONIO, it also provides functions, such as fromJSON() and toJSON() to convert between JSON data and R objects. It could also interact with web APIs, building pipelines and streaming data between R and JSON. In addition, jsonlite provides more options in fromJSON/toJSON function to make conversion explicitly, depending on the input class of R object. jsonlite package also implements these two functions to process data over a http(s) connection, a pipe, even from a NoSQL database. [This paper](https://rstudio-pubs-static.s3.amazonaws.com/31702_9c22e3d1a0c44968a4a1f9656f1800ab.html) gives readers a brief comparison between three packages which is also worthy reading it. [[Ref](http://anotherpeak.org/blog/tech/2016/03/10/understand_json_3.html)]   

In the example above, jsonlite converts a JSON array into a R vector but after using arugments “simplifyVector = F”, the JSON array is converted into a R string. However, if it is a JSON object, the conversion will return a R object automatically.  
Based on the above introduction, we will use jsonlite in this project. 


   
###Example
When we work on projects using Github as the source code repository, we manage all the issues (bugs), tasks or enhancement features, etc, as ‘issues’ at Github. And of course I want to do some analysis on that data. I mean, it is pretty basic stuff like, “how many issues do we have for each release or milestone ?”, “how many issues are assigned to who ?”, “What is the trend of the incoming and outgoing issues ?”. Luckily, Github lets us extract these data, but the data comes in JSON format.[Ref](https://blog.exploratory.io/working-with-json-data-in-very-simple-way-ad7ebcc0bb89)       

```{r, echo = TRUE}
install.packages(c("rjson", "RJSONIO", "jsonlite", "tidyjson"), dependencies = TRUE)   
library(tidyderse)   
library(knity)   
library(DT)     
library(c("jsonlite","tidyjson")    



     


```







