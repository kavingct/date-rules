Date Rules
==========
*Rule based dates for jquery ui datepicker.*

Date rules is a jQuery plugin with which you can control the dates shown in jQuery UI datepicker using a set of pre-defined rules or custom ones.

##### Installation
###### Using Bower
Install the `date-rules` package using bower.
```
	bower install date-rules
```
Once completed you can use it by linking to it in your HTML.
```html
<script src="/bower_components/date-rules/date-rules.js"></script>
```
###### Without Bower
Just download the `date-rules.js` files in this git and link it in your HTML files using script tags.

##### Usage
Before using this package on an element, `jquery ui datepicker` should be initialized already on that element.
```javascript
	$('#element').datepicker({
		//Your options goes here.
	});
```
Once you have done it, you can use date-rules plugin on it. For example let's try to display all dates with even numbers.
The syntax to do it will look like this.
```javascript
	$('#element').dateRules({
		rule: 'evenDays'
	});
```
That's it. The datepicker will only show dates with even numbers now.
Date rules also supports specifying multiple rules at once. Let's extend the previous example to display even dates with no weekend (Saturday and Sunday).
```javascript
	$('#element').dateRules({
		rule: [
			'evenDays',
			'noWeekEnd'
		]
	});
```

###### Custom rule
If you wish to specify your own custom rule implementation you can do it like this.
```javascript
	$('#element').dateRules({
		rule: [
			'evenDays',
			'noWeekEnd'
		],
		custom: function(date) {
			/**
			* Now every date will be passed to this function before showing.
			* Return true to show it and false to hide it.
			*/
		}
	});
```

##### Supported methods
`selected`
This method displays only a provided array of dates in datepicker. For this method, in addition to rule tag, you should also specify a `selections` tag with an array of dates in option.
```javascript
	var dates = [];
	var date = new Date();
	date.setHours(0,0,0,0);
	dates.push(date);
	$('#element').dateRules({
		rule: 'selected',
		selections: dates
	});
```
Note that the `setHours(0,0,0,0)` will remove time values from date object before adding to array, as datepicker check will need dates without time.

`noWeekEnd`
This method hides weekend days (Saturday and Sunday) in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'noWeekEnd'
	});
```

`onlyWeekEnd`
This method shows only weekend days (Saturday and Sunday) in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'onlyWeekEnd'
	});
```

`evenDays`
This method shows only days with even number in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'evenDays'
	});
```

`oddDays`
This method shows only days with odd number in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'oddDays'
	});
```

`evenMonths`
This method shows only dates in months with even number in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'evenMonths'
	});
```

`oddMonths`
This method shows only dates in months with odd number in datepicker.
```javascript
	$('#element').dateRules({
		rule: 'oddMonths'
	});
```

Note
====
* If you find any bug or need any new feature, please open an issue in Github. I will try my best to reply back as soon as possible.
* If you wish to contribute to the code, fork the repo, commit any changes and send pull request.

License
=======
The MIT License (MIT)

Copyright (c) 2013 Genzis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.