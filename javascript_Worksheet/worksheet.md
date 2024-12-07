Problem 1

Error debugging question
function fetchUser(callback){
    setTimeout(() => {
        const user = {name: "Rahul"};
        if (user) {
            callback(user.name);
        
        }else{
            callback("User not found");
        }
    },1000);
}

fetchUser((name) => {
    console.log(name);
})


Output Based question

function fetchAPI(url,delay){
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve({data:`${url} response`});

        },delay);
    });
}

async function fetchData(){
    try {
        const fstapiResult = await fetchAPI('first file',1000);
        const sndapiResult = await fetchAPI('Second file',2000);

        const Result = {...fstapiResult, ...sndapiResult};
        console.log("Combined API",Result);
    }catch (error){
        console.log("Error fetching data",error);
    }
}
fetchData();


Related topic questions:

async/await:
 async marks the function as asynchronous and it always return a promise.

 await pauses execution of the function until the promise is resolved or rejected.

 async/await is syntactic sugar on top of Promises that makes asynchronous code look and behave like synchronous code.

 async/await allows you to write cleaner, more readable code without chaining like .then() and .catch()

Example:
 function fetchAPI(url,delay){
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve({data:`${url}`});

        },delay);
    });
}

async function fetchData(){
    try {
        const fstapiResult = await fetchAPI('first file',1000);
        const sndapiResult = await fetchAPI('Second file',2000);

        console.log("Combined API",fstapiResult);
        console.log("Combined API",sndapiResult);
    }catch (error){
        console.error("Error fetching data",error);
    }
}
fetchData();




Problem 2

Error debugging question

const nums = [10,20,30]
const result = nums
.map((n) => n  / 2)
.filter((n) => n > 0);

console.log(result.reduce((total,num) => total + num,0))



OutputBased question

const nums = [1,2,3,4,5]
const result = nums
.filter((n) => n % 2 == 0)
.map((n) => n * 2)
.filter((n) => n > 0)
.reduce((sum,nums) => sum + nums, 0)
console.log(result)


relative topic question:

Both reduce and forEach used to iterate over arrays, but they behave differently when it comes to their return values.

reduce:

It is used to reduce an array to single value like number,string,object etc. by applying a function on each element in the array.

It returns the final accumulated value after processing all the elements in the array.

when you use callback function with reduce(), which is applied to each element of the array.

The callback takes two arguments an accumulator  and the current element.

The final value returned by reduce() is the accumulated result after all iterations.

Example:

const nums = [2,3,4,5,1];

const sum = nums.reduce((accumulator,n) => accumulator + n,0);

console.log(sum)


forEach:
It is used to loop through each element in array and perform an action with no intention of returning a value.

It returns undefined, It does not produce a value.

It mainly used for side effects, like logging or modifying external variables,rather than returning a new value.

It applies the provided function to each element in array but does not accumulate or return any value or result.

It is useful when you perform actions like logging or updating something outside of the array, but you dont need to return value.

Example:

const nums = [2,1,3,4,5];
nums.forEach((n) => {
    console.log(n);
});
console.log(nums.forEach((n) => n * 3));



Problem 4

Error Based question

const nums = [1,10,2];
nums.sort((a,b) => a - b);
console.log(nums)

output Based question

const users = [
    {name:"Alice", age:25},
    {name:"Bob",age:30}
];

users.sort((a,b) => b.age - a.age);
console.log(users)


Related topic question

LocalCompare:

It is method used to compare two strings according to the local language/country of the users environment.

It can be perticularly useful for sorting strings in a language specific manner,taking into account local variations like alphabet order,case sensitivity and speacial characters.

It returns negative value if the  one string  is less that other string.

It returns zero if the strings are equal.

It returns positive value if the first string is greater than other string.

Example:

const fruits = ['apple','banana','mango']
fruits.sort((a,b) => a.localeCompare(b));
console.log(fruits);

const fruits = ['apple','banana','mango']
fruits.sort((a,b) => a.localeCompare(b,undefined,{sensitivity:'base'}));
console.log(fruits);


Problem 5:

Error based debugging


const obj = {
    name:"Alice",
    greet(){
        console.log(`Hello,${this.name}`)
    }
};
obj.greet();


outputbased question

function Person(name){
    this.name = name;
    this.greet = function(){
        console.log(`My name is ${this.name}`)
    }
}

const person  = new Person("Alice");
person.greet();


Related topic question

bind,call and apply are methods that allow you to explicitly set the value of this within a function.

bind:
bind() method returns a new function where this is permanently set to the provided object.The new function can be called later.

call:
call method allows you to invoke a function immediately and explicitly set this to a specific object.you can pass arguments directly to the function.


apply:
apply method works similarly to call but instead of passing arguments individually,you can provide them as an array.


 