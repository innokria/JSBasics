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



// Generics Sample 
// if you want to add formTitle to existing interface


interface IMyContent {}

interface IProfile extends IMyContent {
    name: string;
    email: string;
}

interface IForm<T extends IMyContent> {
    formTitle: string;
    content: T;
}

var x : IForm<IProfile> = {
    formTitle: "",
    content: {name: "", email: ""}
}

// another way to do the above using intersection
interface IProfile {
    name: string;
    email: string;
}
interface IForm {
    formTitle: string;
}
type IProfileForm = IForm & IProfile;

function formDisplay(resource: IProfileForm) { }



# Object.assign it is possible to mutate an existing object
# using a spread you are always creating a new object:
#Shallow copies duplicate as little as possible. A shallow copy of a collection is a copy of the collection structure, not the elements. With a shallow copy, two collections now share the individual elements.

Deep copies duplicate everything. A deep copy of a collection is two collections with all of the elements in the original collection duplicated.


#In a shallow copy, object B points to object A's location in memory. In deep copy, all things in object A's memory location get copied to object B's memory location.

var module = {
  x: 42,
  getX: function() {
    return this.x;
  }
}

var unboundGetX = module.getX;
console.log(unboundGetX()); // The function gets invoked at the global scope
// expected output: undefined

var boundGetX = unboundGetX.bind(module);
console.log(boundGetX());
// expected output: 42
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind

Remember that objects, including arrays are passed by reference while strings, booleans and numbers are passed by value.

var strA = "hi there";
var strB = strA;
strB="bye there!";
console.log (strA) // hi there
var objA = {prop1: 42};
var objB = objA; 
objB.prop1 = 90;
console.log(objA) // 90
```
