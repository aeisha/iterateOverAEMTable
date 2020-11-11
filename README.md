# iterateOverAEMTable
Use caes: this shows how we can iterate over table rows and append to the cells a dynamic dropdown list 

function createDropdown() {

	var rowCount = window.guideBridge.resolveNode("guide[0].guide1[0].guideRootPanel[0].panel18[0].testpanel[0].table1603899047163[0].Row1[0]").instanceManager.instances.length;

  var temp = new Date().getFullYear();
  var year = parseInt(temp,10);
	var array = [];

  var i = 0;
//create dynamic dropdown items
   	for (i=0;i<10;i++){

        var value = year - 1;
        var value2 = year;
        var value3 = (value + "/" + value2);
        array.push(value3)
		year++;

    }   
    
//iterate over the existing rows and append the drop down with the dynamic array 
    for (j=0;j<rowCount;j++){

        var input1 = window.guideBridge.resolveNode("guide[0].guide1[0].guideRootPanel[0].panel18[0].testpanel[0].table1603899047163[0].Row1["+j+"].tableItem12[0]");
    	  input1.items=[array[0],array[1],array[2],array[3],array[4],array[5],array[6],array[7],array[8],array[9]];

    }
}  


