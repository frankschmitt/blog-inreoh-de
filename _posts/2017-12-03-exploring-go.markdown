# Synopsis
After having successfully solved the first two advent of code puzzles in Python and Rust, I decided to give Go a try. This post outlines my experiences with Go and its ecosystem.

# Testing
Bitter disappointment - apparently, Go's default testing package doesn't even provide ExpectEquals and similar. 
The reasoning seems to be "assertions are bad, therefore we don't use them". While I get why you wouldn't want to have an assert() *macro* in your language, an assert() *test assertion* surely will hurt no one?
Sure, I can easily roll my own, but that kind of defeats the purpose of a default package, doesn't it?

# Type Inference
Calling Go's approach "Type Inference" is an insult to all other programming languages. 

# Built-in Types
No tuples. 'nuff said. 

# Standard library
To use the standard math package, I have to convert everything to float64 and back. It would have been nice to be able to use Ceil() and get an int type instead of having to cast the float64 I get.

# Formatting
One of the few things I like about Go is that it brings its own formatting tool along and that there's zero room for configuring it. So no discussions about formatting, braces style etc. Although - why did they have to use tabs instead of spaces? 

# Final thoughts
Go seems useless. It would have been a great language if it had been invented in the the '80s, and it would have been ok in the '90s.

For comparison, in Rust, I was able to solve a simple assignment within 30 minutes (with no prior knowledge). In Go, I gave up after 3 hours of fighting the language and the ecosystem.

