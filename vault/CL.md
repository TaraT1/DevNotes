---
id: f5bqwmgls2yfd6sv4fatw7g
title: CL
desc: ''
updated: 1675952139338
created: 1675866721762
---
## cURL 
- library & command line tool that completes IP transfers of data using URLs

### Syntax: 
```
curl URL
```
### Options: (case sensitive)
-X or --request  indicates providing method (GET, POST, etc.)  
- curl -X POST http://...
	- frequently used options:
		-X: --request COMMAND  
        -d: --data  
		-F: --form  
		-u: --user  
	    `curl --help`  
		-H or --header  
            Content-Type:  
                application/x-www-form-urlencoded  
                application/json

### Examples
```curl -X POST https://eg.com```

```curl -d "var1=val1&var2=val2" -X POST https://eg.com/```

#### specify header or content type:
```curl -d "var1=val1&var2=val2" -H "Content-Type: application/x-www-form-urlencoded" -X POST https://eg.com/```

``` curl -d {"var1": "val1", "var2": "val2" } -H "Content-Type: application/json -X POST https://eg.com ```


### References
* https://www.golinuxcloud.com/perform-a-post-request-using-curl/
* https://curl.se/docs/