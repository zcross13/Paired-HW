# Paired-HW
Paired takehome challenge that challenges our skills in JavaScript. 

#Challenge 1

```js 
// created a function that take in a number 
// and return that number + 2

const addTwo = (num) => {
    return num + 2
}

console.log(addTwo(2))
```

#Challenge 2
```js 
// created a function that accept a parameter called word
// return word + the letter s 

const addS = (word) => {
   return word + 's'
}

console.log(addS('word'))
```

#Challenge 3
```js 

//create a function call mutiple by two that accepts a num 
// and return that num * 2 

const mutiplyByTwo = (num) => {
    return num * 2 
}

// created a function that accept a array and callback 
// created a variable call newArr as a empty array 
// loop through each item and the array 
// create a variable that assign the current index and it value 
// create a variable that is assign take the value of the current number array 
// and runs the callback function on that value 
// push the new variable into the empty array 
// return the new value 

function map(mapArr, callback){
    const newArr = []
    for(let i=0; i<mapArr.length; i++){
        const currentNumber = mapArr[i]
        const updatedNumber = callback(currentNumber, i)
        newArr.push(updatedNumber)
    }
    return newArr
}

console.log(map([1,2,3], mutiplyByTwo))
```


#Challenge 4
```js 
// Create the function 
// Use a for loop to iterate over each element in the array
//then call the callback function on each element in array

function forEach(arr, callback){
    for(let i=0; i<arr.length; i++){
        callback(arr[i])
    }
}


let alphabet = '';
const letters = ['a', 'b', 'c', 'd'];
forEach(letters, function(char) {
  alphabet += char;
});
console.log(alphabet);
```


#Challenge 5

```js 
const express = require('express');
const app = express();


const mockBlog = [
    {
        id: 1,
        title: 'First Blog Post',
        description: 'My first blog post!'
    },
    {
        id: 2,
        title: 'Second Blog Post',
        description: 'My Second blog post!'
    },
    {
        id: 3,
        title: 'Third Blog Post',
        description: 'My Third blog post!'
    }
];

module.exports = mockBlog

app.use((req, res, next) => {
    res.locals.data = {}
    next()
})

app.get('/blog', (req,res) => {
   res.json(mockBlog) 
} )

// create route is not completed 
app.post('/blog', (req, res) => {
   mockBlog.push(req.body)
   const createdBlog = mockBlog[mockBlog.length-1]
   res.locals.data.mockBlog = createdBlog
})


app.get('/blog/:id', (req, res) => {
    res.json(mockBlog[req.params.id]) 
})


app.listen(3008, () => {
    console.log('listening on port 3008')
})
```
