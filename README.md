Simple AJAX
=====================
The easiest way to use a simple_ajax  and running in seconds.
All you need is some valid markup, jQuery and some extra CSS, 
and jquery-simple_ajax can do the rest.
---
Get to Start.
-----------------------------------
To get to start, You need download jquery and then jquery-simple_ajax.
* Add to your Project jquery.js
* Add to your Project jquery-simple_ajax.js  
* Add to your Project jquery-simple_ajax.css
---

Using functions from Plugin.
-----------------------------------
###1. Paging function $.fn.xhrPagination(paging_data, xhr_data).
* Required Paging_data.sel(in this Selector created pages links)
* Required Paging_data.totalCount(Counts data rows)
* Required Paging_data.items(Rows in one Page)
* Required xhr_data.url
* Required xhr_data.dataLP{offset and items}
---
Call function:
```html
function yorFunctionName(offset_data){
	var items = 10;
	$('your LoadPage selector(In this div load Content)').xhrPagination({
		sel: 'selector',//In this div created paging Links
		totalCount: 'selector OR Number', 
		items: items,
        funcName: "yorFunctionName"
		}, 
		{
			url:'//your URL', 
			dataLP:{offset: offset_data, items:items}
		}
	);
}
```
---
###2. Function $.getFormData(formName)
Return value inputs from form.
* Required formName.
---
Use function:
```html
var formData = $.getFormData(formName);
```
---
###3. Function $.simpleSendData(url, data).
* Required url-argument
* Required data-argument
---
Call function:
```html
var url = "your url";
var data = {your data};
	$.simpleSendData(url, data);
```
---
###4. Function $.sendDataGetJSON(url, data).
* Required url-argument.
* Not required data-argument.
---
Call function:
```html
var url = "your url";
var data = {your data};
	$.sendDataGetJSON(url, data);
```
---
###5.Function $.fn.sendFromDataloadPage(formName, url).
* Required selector.
* Required formName-argument.
If isset form->attribute(action), "url"-argument is not required.
---
Call function:
if isset form attribute action, then var url = 0;
```html
	$(selector).sendFromDataloadPage(formName, (false or url));
```
Then sendFromDataloadPage() function, get value: inputs,select,textarea,checkbox,radiobutton...,
And then make AJAX request to server AND success function make load page to $(this->selector).
---
###6. Function $.fn.sendloadPage(url, data).
* Required is url-argument.
* Required selector.
* Not required data-argument.
---
Call function:
```html
var url = "your url";
var data = {your data};
	$("selector").sendloadPage(url, data);
```
Make AJAX request to server AND success function make:
 -> $(this->selector).html(data_from_server);
