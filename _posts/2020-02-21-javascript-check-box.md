---
categories: javascript
title: javascript check box 제어
---

### 코드

```
function check(_this){
        var chk_name = _this.className;
        console.log(chk_name);
        var chk_box = document.getElementsByClassName(chk_name);
        var chk_length = document.getElementsByClassName(chk_name).length;
        var chkNum = 0;
        for(var i =0; i < chk_length ; i++){
          if(chk_box[i].checked) { chkNum++ }
          if(chk_length == chkNum){
            document.getElementById(chk_name+"All").checked = true;
          }else{
            document.getElementById(chk_name+"All").checked = false;
          }
        }
      }
      function checkAll(_this, className){
        var checkBox = document.getElementsByClassName(className);
        if(_this.checked){
          for(var i =0; i < checkBox.length; i++){
            checkBox[i].checked = true;
          }
        }else{
          for(var i =0; i < checkBox.length; i++){
            checkBox[i].checked = false;
          }
        }
      }
```
