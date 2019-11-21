# learn-fp
A repository with links and learning resources and my own personal understandings of FP. You can correct me anytime I am wrong by filing an Issue or a PR. You can also connect with me on twitter : https://twitter.com/haquezameer.

Example code in JS


# Currying / Partial Application .. blah blah

Currying is a way to apply inputs(i.e) data required by a function partially(step-by-step). In the most basic sense, it is a higher order function(HOF) that returns another function or another HOF and this might go on until a final function that returns the expected value.

For example:-

```js
const multiplyBy2 = num => num * 2;
```

A long time from now you need another func multiplyBy3, what would I do?

I would simply add another multiplyBy3 function

```js
const multiplyBy3 = num => num * 3;
```

or perhaps I might do something like

```js
const multiplyBy = (num,by) => num * by;
```

mehh....

now everytime I have to do `multiplyBy2` or `multiplyBy3` or `multiplyBy4`, I would write 

const res = multiplyBy(2,3) or multiplyBy(2,4) ... and so on...

But what if I could have a multiplyBy2 function which could take an input `num` and return the `result` of `num * 2` and I don't have to provide it each time that I want to multiply by `2` and also that I would not have to go ahead and make other such functions if I want to multiply a different number.

Well here is where currying will help, basically `we'll take all the ingredients and put it one by one(partially applying) in the function(our pot) to get our result(the curry)`.

```js
const multiplyBy = (by) => (num) => num * by;
```

or 

```js
function multiplyBy(by) {
  return function(num) {
    return num * by;
  }
}
```

you see now you could have multiplyBy2 func like

```js
const multiplyBy2 = multiplyBy(2)
```

want to multiply something by 2??

just call 

```js
multiplyBy2(3) // result: 6
```

similarly other such functions can be created and can be used to compute the multiplication result yet not having to pass in the other other input each time.
