**********************************************************Documentation jquery-ajax-plugin******************************************************
*Function name.
*Requirements functions.
*Parameters functions.
*Call function.
*************************************************************************************************************************************************
-------------------------------------------------------------------------------------------------------------------------------------------------
1.1 Function $.fn.sendloadPage(url, data).
	- Required is url-argument.
	- Required selector.
	- Not required data-argument.
- Call function:
	$("selector").sendloadPage(url, data);
Then sendloadPage() make AJAX request to server AND success function make:
 -> $(this->selector).html(data_from_server);

-------------------------------------------------------------------------------------------------------------------------------------------------

1.2 Function $.fn.sendFromDataloadPage(formName, url).
	- Required selector.
	- Required formName-argument.
	- If isset form->attribute(action), "url"-argument is not required.
-Call function:
	$(selector).sendFromDataloadPage(formName, (false or url));
Then sendFromDataloadPage() function, get value: inputs,select,textarea,checkbox,radiobutton..., if url-argument empty, get value form->action.
And then make AJAX request to server AND success function make load page to $(this->selector).

-------------------------------------------------------------------------------------------------------------------------------------------------

1.3 Function $.sendDataGetJSON(url, data).
	- Required url-argument.
	- Not required data-argument.
Call function:
	$.sendDataGetJSON(url, data);
Make AJAX request with data- or data- empty argument.

-------------------------------------------------------------------------------------------------------------------------------------------------

1.4 Function $.simpleSendData(url, data).
	-Required url-argument
	- Required data-argument
Call function:
	$.simpleSendData(url, data);

-------------------------------------------------------------------------------------------------------------------------------------------------

1.5 Function $.getFormData(formName).
Return value inputs from form.

-------------------------------------------------------------------------------------------------------------------------------------------------

1.6 Paging function $.fn.xhrPagination(paging_data, xhr_data).
	-Required Paging_data.sel(in this Selector creanted pages links)
	-Required Paging_data.totalCount(Counts data rows)
	-Required Paging_data.items(Rows in one Page)
	-Required xhr_data.url
	-Required xhr_data.dataLP{offset and items}

Call function:
Function Name allways loadPaging_content(bool OR 'next' OR 'preview').
function loadPaging_content(offset_data){
	var offset;//default value page button
	if(offset_data){
		offset = offset_data;
	}else{
		offset = 0;
	}
	var items = 10;
	$('your LoadPage selector(In this div load Page)').xhrPagination({
		sel: 'selector',//In this div created paging Links
		totalCount: 'selector OR Number', 
		items: items
		}, 
		{
			url:'//your URL', 
			dataLP:{offset: offset, items:items}
		}
	);
}