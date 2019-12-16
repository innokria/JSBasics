
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




