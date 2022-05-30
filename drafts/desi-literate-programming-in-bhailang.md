---
title: Desi Literate Programming in Bhailang
date: 2022-03-16
draft: true
---
# Desi Literate Programming in Bhailang

## What is Bhailang[^bhailang]?
According to its landing page, "A toy programming language written in Typescript".
Its a programming language based on Indian slangs, which makes it fun & accessible for anyone who knows Hindi.

## What is Literate Programming[^literate-programming]?
According to Donald Knuth, the creator of Literate programming, "Literate programming is a programming methodology that combines a programming language with a documentation language, making programs more robust, more portable, and more easily maintained than programs written only in a high-level language."

Simply put, its "Code inside Documentation" instead of "Documentation inside Code".

## Why Bhailang?
It doesn't adhere to literate programming's definition, but I guess you could call it poor man's literate programming language.

I do believe that code is meant to be read first and executed second. The fact that Bhailang makes reads like natural language makes it a good language for literate programming. 

Also according to the documentation, "`hi bhai` is the entrypoint for the program and all program must end with `bye bhai`. Anything outside of it will be ignored". Which means you can write things like documentation, problem statement and things related to the program anywhere outside the program body. 

## Sample programs 
I wont explain the syntax, its trivial. They are just syntactic sugars for programming constructs but accessible.

Lets go with classics.

### Fizzbuzz
```bhailang:fizzbuzz.bl
hi bhai

bhai ye hai counter = 1;
bhai ye hai upperbound = 100;

jab tak bhai (counter <= upperbound){

  agar bhai (counter % 15 == 0){
    bol bhai counter, "FizzBuzz";
  } nahi to bhai (counter % 3 == 0){
    bol bhai counter, "Fizz";
  } nahi to bhai (counter % 5 == 0){
    bol bhai counter, "Buzz";
  } warna bhai {
    bol bhai counter;
  }

  counter = counter + 1;
}

bye bhai
```

Now for number 2, let's go with something math isn't quite ready for.

### Collatz function
```bhailang:collatz.bl
hi bhai

bhai ye hai input = 10;
bhai ye hai counter = 0;

  jab tak bhai(input != 1){
    agar bhai(input % 2 == 0){
      input = input / 2;
    } warna bhai {
      input = 3 * input + 1;
    }

    counter = counter + 1;
  }

  bol bhai counter;

bye bhai
```


[^bhailang]: https://bhailang.js.org
[^literate-programming]: http://www.literateprogramming.com
