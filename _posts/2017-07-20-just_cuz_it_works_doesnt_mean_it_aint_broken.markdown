---
layout: post
title:  "Just Cuz it Works, Doesn't Mean it Ain't Broken"
date:   2017-07-20 05:02:30 +0000
---


I had a fun learning experience and big AH-HA! moment today. I was working on a lab where I had to build a playable Tic Tac Toe game in Ruby using helper classes which I had written in several previous labs. I approached this project with a really positive attitude because it felt like something I could totally do. I've always been a great copy-paster.

All was going well at first. I followed the instructions, brought everybody over to the party from the other labs, ran the first RSpec and everyone was playing nicely together and passing.

Building the `#play` method to run the turns for the game was challenging but I figured it out, writing the CLI was cake, and before I knew it I was playing a working game of Tic Tac Toe that ***I built in Ruby***.

<img src="https://media.giphy.com/media/nXxOjZrbnbRxS/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive" />

I could hardly contain my excitement. I had done it. I did it! And it worked. I was playing Tic Tac Toe and getting wins or draws just like the instructions said to do. Everything seemed as it should be.

Then I ran the `learn` command to try and pass my local tests before I committed my code to GitHub and BOOM!, there it was, the grey text of doom telling me the following:
```
Errno::ENOENT: No such file or directory
```
The error was something I hadn't seen before and it was complaining about my `gets.strip` in the `#turn` method (which the `#play` method runs in a loop). I Googled and read Stack Overflow forums and tried a few things to no avail.

I analyzed my code up and down and read over the instructions a few times. Everything looked good. Ran the bin and played the game successfully several times, but I was still getting the error on my `gets`

<img src="https://media.giphy.com/media/ffJiLLtCk5Am4/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive" />

I reached out to the Learn community for help and the guy said it sounded very odd and wanted to do a screenshare. But the timing was bad for me, dinner had just finished in the crockpot, and I was hangry and coded out for the day.

So I dismissed asking for help for the day and figured I'd sleep on it and try again the next day (today).

Today, I started fresh and decided to intricately comb through it all again. I looked over a few student-submitted solutions and over the master solution on GitHub. Everything still looked good to me and I was scratching my head for hours.

I kept getting either the `Errno::ENOENT` error on the `gets` when running the `learn` command on the master, or a `NoMethodError` on `strip` in each of the RSpecs.

Then I read through the instructions one more time and something jumped out at me:

`A tic tac toe game must allow players to take turns, checking if the game is over after every turn, and at the conclusion of the game, whether because it was won or because it was a draw, reporting to the user the outcome of the game.`

The game I was playing (which was "working") was not ending after a draw, it would allow you to continue playing until you had a win. After reading these instructions, I realized the game needed to end after a draw. So it was something wrong with the `#play` method and not actually the `gets` inside of the `#turn` method.

And then I finally saw it.

<img src="https://media.giphy.com/media/3NtY188QaxDdC/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive" />

I had mistakenly called on `play(board)` at the end of my `#play` method instead of just at the end my CLI (which is where it was supposed to be since the bin initializes the game).

Derptastic, and total User-Error! I felt a little silly, and a little dumb, but moreso, I felt kinda lowkey badass for finding that all on my own and that was rewarding to me.

<img src="https://media.giphy.com/media/11caUX0P0nYZ32/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive" />

It was an exciting moment and another way to learn; by finding what's broken when things are working. Which is just as important as every other way I've been "learning to learn" on my coding journey through Ruby.

***Next up***: **Object Orientated Programming.** I'm a little scared. Wish me luck!

<img src="https://media.giphy.com/media/xTka03MJaW81LHt0sg/giphy.gif" style="min-width: 300px; max-width: 300px;" alt="image" class="img-responsive" />
