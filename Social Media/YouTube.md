## **Template for extracting targeted text from source code**

javascript.
var html = document.documentElement.innerHTML;
var subhtml = html.split('$leftlimittext’)[1];
var output = subhtml.split('$rightlimittext’)[0];
alert(output)


## **Template for running multiple URL-structured queries**

javascript:
var input = prompt("Prompt user for Input");

var variable1 = "$URLSTRUCTUREONE" + input;
var variable2 =  "$URLSTRUCTURETWO" + input;
var variable3 =  "$URLSTRUCTURETHREE" + input;

SiteOneFunction(); 
SiteTwoFunction(); 
SiteThreeFunction(); 

function SiteOneFunction() {   setTimeout(function(){ window.open(variable1, "_blank"); }, 1000); }
function SiteTwoFunction() {   setTimeout(function(){ window.open(variable2, "_blank"); }, 1000); }
function SiteThreeFunction() {   setTimeout(function(){ window.open(variable3, "_blank"); }, 1000); }
