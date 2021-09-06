# js error solution
## Uncaught TypeError: Cannot set property 'checked' of undefined
```
    window.onload=function(){
                ... 
            };
```
## get cookies 
```
/**
 * 获取Cookie中的值,对document进行分解，使其变成一个数组，每个数字组里是对应的cookie的key、value
 *　在每个数组里的cookie中key、value根据=进行拆分，通过==比较获取想要的value值
 * @param objName
 * @returns
 */
function getCookie(objName){//获取指定名称的cookie的值 
    var arrStr = document.cookie.split("; "); 
    for (var i = 0; i < arrStr.length; i++) { 
        var temp = arrStr[i].split("="); 
        if (temp[0] == objName){ 
            return decodeURI(temp[1]); //decodeURI解密这个uri
        }
    } 
    return "";
}

```

## check unique charset
```
/**
 * 特效字符检查
 */
function validateXCode(sPostCode) {
    var regPostCode = /((?=[\x21-\x7e]+)[^A-Za-z0-9])/;
    if (!regPostCode.test(sPostCode)) {
        return "success";
    } else {
        return "failed";
    }
}
```

## hide context and space
style="display: none;"

## reload to special page
displayView.reloadPage('这里输入下一个页面的地址');

## set and get
 set or get value in textarea and select use .val()

## replaceall in js
```
/**
* 
* /-/ 正则表达式获取'-'，g 全局的参数（所有的）
*/
 address = address.replace(/-/g, "");
 ```
### 截取。 ； ， ： “ ”（ ） 、 ？ 《 》中文标点
```
sCIDAddr=sCIDAddr.replace(/[\u3002\uff1b\uff0c\uff1a\u201c\u201d\uff08\uff09\u3001\uff1f\u300a\u300b]/g, "");
```
即符号经过转码之后进行全局匹配

## contains in js
```
if(str.indexOf("3") != -1){
    alert("don't exist in string");
}else{
    alert("exist")
}
```

## text in span 
### set 
```
$('#span_id').html("text");
documeent.getElementById("span_id").innerText="text";
```
### get
```
documeent.getElementById("span_id").innerText;
$('#span_id').html();
```
## do next after click sure function
### alert part
```
wtApp.alert(alertInfo, function () {
    //todo
        });
```
### confirm part
```
wtApp.confirm(confirmInfo,, function() {
        //success
        },function(){
        //fail
    });
```