SyncFor Node Module
=====================

synchronous for loop (node.js)

How to use
==============
 
include syncFor module using require
====================================================================================
var syncFor=require('./syncFor'); //path to syncFor.js 

 
var arr =   [1,2,3,4,5];

syncFor(0,arr.length,"start",function(i,status,call){

 if(status === "done")

    console.log("array iteration is done")

 else

    makeHttpCall(arr[i],function(){

     call('next') // this acts as increment (i++)

   })

})

function makeHttpCall(pageNo,callback){

 request("www.exaple.com?page="+pageNo,function(err,res){

    callback(); // call the callback when u get answer

  });

}

Known Issues
=============
Failing if length of array is more than 200
 


