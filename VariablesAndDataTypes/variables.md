## Variables

### Theory

Variables are named containers for a single piece of information. In Kotlin, there are two types of these containers - (i) where you put in the information once and keep it as it is and (ii) that allow you to change this information while your program runs. You indicate this when generating a new named variable. 

`val maja = "Hallo"` generates a new variable with the name `maja` which holds the text 'Hallo'. The `val` keyword tells Kotlin that you will never change the value of the variable `maja`. It is a so-called 'immutable' variable.

`var willi = "Welt"` generates a new variable with the name `willi`which holds the text 'Welt'. As you used the `var`keyword, you can change the value of this variable later in you code like this `willi = "World!"`. In Kotlin-speak, this variable is 'mutable'. Note that you use the `var` keyword only when first introducing the variable, not when working with it later in your code.

Read more about [var & val](https://stepik.org/lesson/103806/step/1?unit=78378)

Watch [this video](https://www.youtube.com/watch?v=HLvRzBjx7hk&list=PLQkwcJG4YTCRSQikwhtoApYs9ij_Hc5Z9&index=4) until 8:57. We will cover the content of the rest of the video in the next section, but of course you can watch it also here ;-)

### Action

Solve Exercises 1-5 of the Atomic Kotlin Course

In exercise 2 realise, that the value of b is not changing after you changed the value of a. This tells you that the statement `a = b` only assigns the current value of b to a. It does not "magically" link the variables.

---

[back](../)
