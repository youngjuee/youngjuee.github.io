---
title: jquery number formatting
category: jquery
---

jquery 숫자 자리수 콤마 찍기


```
Number.prototype.nformat  = function () {
	if(this == 0) return 0;
	var reg =  /(^[+-]?\d+)(\d{3})/;
	var n = (this +'');
	
	while(reg.test(n)) n = n.replace(reg, '$1' + ',' + '$2');
	return n;
 }
 
 String.prototype.nformat = function () {
	var num = parseFloat(this)
	if(isNaN(num)) return "0";
	return num.nformat();
}
```