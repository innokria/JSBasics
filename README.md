

# unique object in an array
```
const unique = [...new Map(arr.map(item => [item[key], item])).values()]
```

# How does it work
```
First the array is remapped in a way that it can be used as an input for a Map.

arr.map(item => [item[key], item]);

which means each item of the array will be transformed in another array with 2 elements; the selected key as first element and the entire initial item as second element, this is called an entry (ex. array entries, map entries). And here is the official doc with an example showing how to add array entries in Map constructor.

Example when key is place:

[["here", {place: "here",  name: "x", other: "other stuff1" }], ...]
Secondly, we pass this modified array to the Map constructor and here is the magic happening. Map will eliminate the duplicate keys values, keeping only last inserted value of the same key. Note: Map keeps the order of insertion. (check difference between Map and object)

new Map(entry array just mapped above)

Third we use the map values to retrieve the original items, but this time without duplicates.

new Map(mappedArr).values()

And last one is to add those values into a fresh new array so that it can look as the initial structure and return that:

return [...new Map(mappedArr).values()]

https://stackoverflow.com/questions/2218999/remove-duplicates-from-an-array-of-objects-in-javascript
```
# array are pass by ref

primitive type variables like strings and numbers are always passed by value.
Arrays and Objects are passed by reference or by value based on these conditions:

let a =['a' ,'b']

let b = [];
b.push(a)

b[0].push('1')
console.log(a)
console.log(b)

both will get updated -> a , b ,1 


# convert  const a=[1,2]   to ["a","b]
-const a =[12345];
-console.log(Array.from(a.toString())) ->["a","b]
#sql

sub query


select *
from (select item_id, count(*)
from file
group by item_id
 ) i2
where i2.count>400;


#sublime
control+a
conteol+shift+l to select whole and then replace

# JSBasics
Javascript and typescript basics
```


#parse
{ key: '2020-05-2*',
  from: 1590364800000,
  from_as_string: '2020-05-25T00:00:00.000Z',
  doc_count: 0 }
  
  ---solution 
  const oe = ((((agg || {}).recent || {}).buckets || [])[0] || {}).from_as_string || {};

  
  
  
  
  # parse ends



unqiure item in array
 
 ss=[
   {  key :'1',
     value:'abc'

   },
      {  key :'12',
     value:'ab2c'

   },
      {  key :'12',
     value:'adef'

   },
      {  key :'1',
     value:'a54353'

   },
 ]
 
 const uniqueBuckets = ss.filter(
        (obj, index, self) => index === self.findIndex((t) => t.key === obj.key),
      );

      console.log(JSON.stringify(uniqueBuckets,null,2))
      
      






CSS to refer
https://caniuse.com/#search=flex

--------------------------------------
Merge/flatten an array of arrays
[['1'],['2]]  => [1,2]
var merged = [].concat.apply([], arrays);

console.log(merged);

-------------------------------------


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



const array = ["one", "two", "three"]
array.forEach((item, index,arr)=> {
  console.log(item, index,arr);
});


array.forEach((key,item)=>{
  
  console.log(typeof key);
  
})

var a = ["a", "b", "c"];
a.forEach(function(entry) {
    console.log(entry);
});


let arrWithObjects = [{
    name: 'Jon',
    age: 32
  },
  {
    name: 'Elise',
    age: 33
  }
];
// NOTE: Destructuring objects while using shorthand functions 
// are required to be surrounded by parenthesis
arrWithObjects.forEach( ({ name, age: aliasForAge }) => {
  console.log(name, aliasForAge)
});









# find duplicates
let strArray = [ "q", "w", "w", "e", "i", "u", "r"];

let findDuplicates = (arr) => arr.filter((item, index) => arr.indexOf(item) != index)

console.log(findDuplicates(strArray)) // w


#########################################################################################
#kotlin
https://chercher.tech/kotlin/duplicate-string-character-count

A Set is a collection that contains no duplicate events, so converting an array to a Set will get rid of all the duplicates.

/**
 * You can edit, run, and share this code. 
 * play.kotlinlang.org 
 */
import java.util.Arrays;
fun removeArrayDuplicates(duplicates: Array<String>): Array<String> {
    return Arrays.asList(*duplicates).toSet().toTypedArray()
}

fun main(args: Array<String>) {
    val duplicates = arrayOf("a", "b", "c", "a", "c")
    println(Arrays.toString(removeArrayDuplicates(duplicates)))
    // [a, b, c]
}

# merge 2 aray  into 1
where s is array ["1","2"]
let result = [].concat.apply([], s);


##################### kotlin ends








https://github.com/sudheerj/javascript-interview-questions
https://github.com/topics/javascript-interview-questions


#BIG O

 O(1) - Constant time   - same time for any inout  ) even or odd no 
3. O(n) - Linear time   --  one loop ( takes all element) ( find find the maximum value from an unsorted array.
4. O(n^2) - Quadratic time       -- double loop ( find duplicates in array)
5. O(n^c) - Polynomial time
6. O(log n) - Logarithmic time --- binary swarch  ( find an keyword in dictionrty - divide item into half n scan ) 
https://adrianmejia.com/most-popular-algorithms-time-complexity-every-programmer-should-know-free-online-tutorial-course/


GIT TDD 
https://gist.github.com/up1/ae097e63c9cc09aed89b64333b2e98b6










# remove all nulls and undefined from array
// where doc is an array 
 let x = Object.keys(doc).reduce(
        (acc, key) =>
          doc[key] == null || (doc[key].length == 0 && delete doc[key]) ? acc : { ...acc, [key]: doc[key] },
        {},
      );

# delete obj from array
const obj = {
  prop1: 'foo',
  prop2: 'bar',
  prop3: 'baz'
}

;[ 'prop1', 'prop2' ].forEach(prop => {
  delete obj[prop]
})

console.log(obj.prop1, obj.prop2, obj.prop3)



# remove null and empty and get unqiue data from array
 let aa = [
        ...new Set(
          []
            .concat(...Object.values(doc))
            .filter((v) => {
              return v && typeof v !== 'object';
            })
            .map((v) => String(v)),
        ),
      ];




#linked list
function linkedList(arr){
  return arr.reduceRight((next, value) => ({value, next}), null);
}

l = [3, 1, 2, 3, 4, 5];

console.log(linkedList(l));

{
  "value": 3,
  "next": {
    "value": 1,
    "next": {
      "value": 2,
      "next": {
        "value": 3,
        "next": {
          "value": 4,
          "next": {
            "value": 5,
            "next": null
          }
        }
      }
    }
  }
}


# recursive method 

 getItemsByParentIds(items: string[]) {
    let ids = [];

   
    const pId = items.map((a) => a.id);
    if (pId[0] !== null) {
      ids.push(...pId);
      ids = ids.concat(this.getItemsByParentIds(pId));
    }

    return ids;
  }
```




