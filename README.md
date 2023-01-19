# Paired-HW
Paired takehome challenge that challenges our skills in JavaScript. 

#Challenge 1

```js 
const addTwo = (num) => {
    return num + 2
}

console.log(addTwo(2))
```

#Challenge 2
```js 
const addS = (word) => {
   return word + 's'
}

console.log(addS('word'))
```

#Challenge 3
```js 
const mutiplyByTwo = (num) => {
    return num * 2 
}

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
