

# JS字符串操作常用函数

# JS对字符串去重

****

## JS字符串中去重操作

```js
// 字符型穿的去重操作
var str="aahhgggsssjjj";
function removeRepeat(msg){  
    var res=[];  
    var arr=msg.split("");  
    for(var i=0;i<arr.length;i++){  
        if(res.indexOf(arr[i])==-1){  
            res.push(arr[i]);  
        }  
    }  
    return res.join("");  
}  
removeRepeat(str);    //ahgsj
```

## JS计算字符串中的字符出现的重复次数

```js
// js计算字符串中的字符出现的重复次数
/*  
    1.先实现字符串去重  
    2.然后对去重后的数组用for循环操作，分别与原始数组中各个值进行比较，如果相等则count++,循环结束将count保存在sum数组中，然后将count重置为0  
    3.这样一来去重后的数组中的元素在原数组中出现的次数与sum数组中的元素是一一对应的  
*/  
var str="aacccbbeeeddd";  
var sum=[];  
var res=[];  
var count=0;  
var arr=str.split("");  
for(var i=0;i<arr.length;i++){  
    if(res.indexOf(arr[i])==-1){  
        res.push(arr[i]);  
    }  
}  
for(var i=0;i<res.length;i++){  
    for(var j=0;j<arr.length;j++){  
        if(arr[j]==res[i]){  
            count++;  
        }  
    }  
    sum.push(count);  
    count=0;  
}  
console.log(res);    //["a", "c", "b", "e", "d"]  
for(var i=0;i<res.length;i++){  
    var str=(sum[i]%2==0)?"偶数":"奇数";  
    console.log(res[i]+"出现了"+sum[i]+"次");  
    console.log(res[i]+"出现了"+str+"次");  
}
```

