---
layout: post
title:  "Elegance in Ruby (pt. 1)"
date:   2017-09-08 22:06:27 +0000
---


As I've been working through the **Procedural Ruby** course, I find myself getting the most confused with iteration and loops. It is just a difficult concept for me to wrap my head around (no pun intended). However, with each lab that I complete, I feel like it makes more and more sense. And rather than getting completely stuck with no clue on how to solve the problem, I find myself thinking like a programmer by asking myself questions based on previous solutions to other problems.

<img src="https://media.giphy.com/media/QMJhOD0obsiPe/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive">

Something that I keep noticing is how much I tend to over-complicate solutions inside my head. I'll read the lab instructions, jump right in, try a bajillion things, and end up with a huge blob of code that *kinda* works. But once I get to the "kinda works" stage, I get really excited that something is happening, that I am getting something to *do something*, and that fuels me to try more things and finish the lab.

<img src="https://media.giphy.com/media/DFqYLyMGpZ42c/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive">

More often than not, the solution to the problem is A LOT simpler than I think it is, and I spend many hours getting to the point of coming to that conclusion. But once I realize the simplicity, I have that "Ah ha!" moment and everything seems to just fall into place.

For example, today I was working on the [**Reverse Each Word**](https://learn.co/lessons/reverse-each-word) lab and I had finally come up with a solution that worked:

```
def reverse_each_word(sentence)
  split_sentence = sentence.split
  split_sentence.collect do |word|
    word.reverse
	end
  .join(" ")
end
```

Sure, it worked, but I realized it was redundant and long. I didn't need to make a variable for my `sentence` argument that I was using `.split` on to convert it to an array. Instead, I could just operate the `.split` and the `.collect` on the `sentence` argument, use the braces instead of the `.each / do` and `.join` it at the end of the last brace. Look at how much more elegant this solution is compared to the one above:

```
def reverse_each_word(sentence)
  sentence.split.collect { |word| word.reverse }.join(" ")
end
```

After I cleaned up my code, everything just felt better. Kinda like cleaning your room, or donating a bunch of things you don't need anymore. Ahh, that breath of fresh minimalism. Not to mention feeling like a complete badass.

<img src="https://media.giphy.com/media/BdKgExSCWg9TG/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive">
