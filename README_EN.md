# jsstp  

Use js to communicate with ukagaka in a web page to exchange information.
See [ukagaka](https://en.wikipedia.org/wiki/Ukagaka)&[SSTP](http://ssp.shillest.net/ukadoc/manual/spec_sstp.html) for details.

## Usage

### 1. loading js

```html
<script src="https://cdn.jsdelivr.net/gh/ukatech/jsttp-lib@master/jsttp.min.js"></script>
<!-- or --->
<script src="https://cdn.jsdelivr.net/gh/ukatech/jsttp-lib@master/jsttp.js"></script>
```

### 2. Use

```javascript
jsttp.SEND(
	{//Event information
		"Event": "OnTest",
		"Script": "\\0Hello, World!\\e"
	},
	function (data) {//callback function, can be omitted
		console.log("return_code: "+data.return_code());
		console.log(data);
		console.log(data["Script"]);
	}
);
//You can also use promise
jsttp.SEND(
	{
		"Event": "OnTest",
		"Script": "\\0Hello, World!\\e"
	}
).then(function (data) {
	console.log("return_code: "+data.return_code());
	console.log(data);
	console.log(data["Script"]);
});
```
Please read the source code for detailed definitions and functionality.
