# Mystery Function

What does the `mystery()` function in the following piece of code do? Add your
answer to this markdown file.

```javascript
function mystery(a) {
    if(a.length == 1) return a[0];
    var foo = mystery(a.slice(1, a.length))
    if(foo > a[0]) return foo;
    else return a[0];
}
```

The mystery function in question takes an array as a parameter and returns the largest element in the array  

It does this by making an array of every element but the first and recursively calling itself on these increasingly smaller and smaller arrays, with a base case of an array of only one element. It then checks to see if the largest element found in the array minus the first element by the recursive call is larger than first element. If it is that value is returned, if it isn't the first element is returned as the larger of the two. By slicing off one element at each call until there is only one element left and making one comparison for every call, you make a comparison for every element in the array, with the greater value in the comparison being returned. This results in the function returning the largest value in the array  

Line by line breakdown:  

The mystery function takes an array (a) as a parameter  
It first checks if the length of the input array is 1, or it is an array with only one element  
    If it does only have one element, it returns that one element aka the first element aka the element at index 0  
    Since this is the only element, it must be the highest  
If the array has a length that is not 1, it will pass the if statement  
Initialize a global variable foo to be a recursive call that passes the array made by slicing the array of the current call from its second element to its final element as an argument back to our mystery function  
This is essentially passing on an array that contains every element except the first element, the element at index 0  
If the value obtained by the recursive call of foo is larger than the value currently stored at the index 0, return foo  
If all other conditions fail, return the value at index 0  
