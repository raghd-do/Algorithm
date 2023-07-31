# ATM
Given the following currency denominations 1, 5, 10, 50, 100. Write a function that divides any given amount of money (integer) input into the smallest number of bank notes. Return a dictionary of currency denominations as keys and their frequency in the answer as values. For example, Given input of 265 you should return { 1:0, 5:1, 10:1, 50:1, 100:2 }

### Solution
```js
function ATM (withdraw){
  const take = {1:0, 5:0, 10:0, 50:0, 100:0}
  
  const currencyDenominations = [100, 50, 10, 5, 1]
  
  for (var i = 0; i < currencyDenominations.length; i++){
    var result = Math.floor(withdraw/currencyDenominations[i])
    
    take[currencyDenominations[i]] = result
    
    if (result > 0 ) {
      withdraw -= (currencyDenominations[i]*take[currencyDenominations[i]])
    }
  }
    return take
}
```
### Test
```js
console.log(ATM(0))
console.log(ATM(1))
console.log(ATM(265))
console.log(ATM(300))
```
