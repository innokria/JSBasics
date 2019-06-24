# JSBasics
Javascript and typescript basics
```
var number = ["d","e","h"];

let s:any=["a","b"];

let obj={
  id:1,
  roll:3
}





console.log(Object.assign(obj, number));//0: "d" , 1: "e" ,2: "h" ,id: 1 ,roll: 3



console.log(Object.entries(obj));
console.log(...number);// array of index and value
const ss = s.includes("a");//bool

console.log(ss)//true
console.log(number.includes("e"))//true

const k= Object.keys(number).find(x=>number[x]==='d');// value

let a = Object.keys(number).filter(x=>number[x]==='d'); // array of index



console.log(k);//'0'
console.log(a);//['0']
```
