# Javascript Interview Question Answer


##  Exciting ES6 JavaScript Features!

- Arrow functions
- Multi-line Strings
- Destructuring Assignment
- Enhanced Object Literals
- Promises
- Let and Const Keywords

##  var vs let vs const

### var:

- Scope: Global 
- Shadowing: Possible 
- Declaration: Can declare without initialization 
- Re-init/Update: Can be updated 

### let:

- Scope: Functional/Block 
- Shadowing: Possible outside scope, illegal inside 
- Declaration: Can declare without initialization
- Re-init/Update: Can be updated 

### const:

- Scope: Functional/Block 
- Shadowing: Impossible in any case 
- Declaration: Must declare with initialization 
- Re-init/Update: Cannot be updated 


##  Hoisting and temporal deadzone
Hoisting for var,const,let
https://www.freecodecamp.org/news/what-is-hoisting-in-javascript-3/


##  map vs filter vs reduce

- Map is used to create new array from existing one by applying callback function on each of its element.
Syntax : Array.map((currentValue, index, OriginalArray)=>{
    logic
})
  - Map Polyfill
    - 
    ``` 
    Array.prototype.myMap =function (cb){
    let temp =[];
    for (let i =0; i<this.length ; i++>){
        temp.push(cb(this[i], i, this));
    }
    return temp;
 } 
    ```
- Filter is used to take array elems and based on given condition it will decide whether it need to push it to new array or remove it.
Syntax : Array.filter ((currentValue, index, OriginalArray)=>{
    condition
})
  - Filter polyfill
    - 
    ``` 
    Array.prototype.myFilter = function (cb){
    let temp = [];
    for (let i = 0; i < this.length; i++) {
        if(cb(this[i],i,this)){
            temp.push(this[i]);
        }
        
    };
    return temp;
}; 
    ```


- reduce used to reduce the array to a single value and executes a provided function for each value of the array (from left to right) and the return value of the function is stored in an accumulator. 
Syntax : Array.reduce ((accum, index, currentValue, OriginalArray)=>{
    return Logic;
}, initialValue)

Polyfill

- map vs forEach difference

- - - map returns new array with transformed elements, foreach returns undefined , it doesnt create new array

- - map() is chainable. This means that you can attach reduce(), sort(), filter() methods, That's something you can't do with forEach() because, as you might guess, it returns undefined.

- - map is immutable, it doesnt modify original array, while forEach is mutable, it can modify original array

- - As always, the choice between map() and forEach() will depend on your use case. If you plan to change, alternate, or use the data, you should pick map(), because it returns a new array with the transformed data.
But, if you won't need the returned array, don't use map() - instead use forEach() or even a for loop.