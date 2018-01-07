# Synopsis
I've recently played a little bit with Go (solved one of the Advent of Code puzzles in it - another Blog post with details regarding that will follow soon), and overall, I don't like it. I don't like its attitude, and I don't like the lack of convenience features I expect from newly designed languages nowadays.

# Detailed Rant

## Naming
Choosing Go as the name of a new programming language was incredibly stupid (since Go the board game has been around for thousands of years). Searching for "Go tutorial" can therefore never be unambiguous - either you want an explanation of the board game, or you want one for the programming language. But apparently, Google's arrogance let them assume that they don't have to respect anybody else.

## Testing 
Taken from https://golang.org/doc/code.html#Testing (official Go documentation):

```
    got := Reverse(c.in)
    if got != c.want {
      t.Errorf("Reverse(%q) == %q, want %q", c.in, got, c.want)
    }
```

Seriously? You recommend I *manually compose my assertion and error message* when I want to write a trivial unit test?

What was so wrong about

```
  AssertEquals(Reverse(c.in), c.want, "Reverse does not work as expected")

This is simply brain-dead.

## Attitude of the Go core team
At first, I thought "Ok, Go is still young, and they made some mistakes that they will certainly fix in future releases". But then, I read this: 

"There are many things in the Go language and libraries that differ from modern practices, simply because we feel it's sometimes worth trying a different approach. https://golang.org/doc/faq#assertions
"

Translation: "We do it differently because we are Google and therefore know better than everybody else on the planet. We ignore important research and knowledge obtained by others because we massively suffer from the NIH syndrome."

## Attitude of Go users
The final straw was the attitude that several Go users showed on StackOverflow, e.g. 

 "It's not the Go way" https://stackoverflow.com/a/18638071/610979  

It might not be the Go way, but it's the *sensible, industry proven* way. 

# Conclusion
Goodbye, Go.

 

 
