# Using GPT to create webpages 

This guide will show you how I request help from chatGPT to create an HTML and .js script that handles the gameplay elements of games I’m building. In this example, we’re trying to make a piano. The puzzle requires figuring out the right series of keys to press, in which instance the solution is provided. This could be a link to the next room/portal, or a clue/key, etc.

## Getting Started

To get started, ask GPT how to install `node.js` and `http-server` on your machine to run and test this locally. Then ask GPT how to host HTML pages on github using github.io

There you can host all your webpages you intend to use in your game. My full transcripts with GPT are available here, if you’re interested in how the back in forth takes place. I do a lot of showing the code we’ve got so far, and asking very basic questions. One step at a time leads to better results!

[Transcript 1](https://chat.openai.com/share/3ad0b66c-fcf7-4c88-8bf7-0df72477f5cc)

[Transcript 2](https://chat.openai.com/share/ea817d7d-1da8-40aa-953d-39ce9e3e479f)

### First prompts first

This is how I typically begin, `using HTML and javascript, help me create a webpage that ___`

```
using html and javascript, help me create a webpage that looks like 2 octaves of a piano. when the user clicks a key, on MBD a sound will trigger. i will add the sounds later, i just want help making the keys.
```

as you can see, there’s been some misunderstanding on the layout of the piano…

![1](https://cdn.discordapp.com/attachments/1051281685234327613/1145385590687272960/1.png)
```
please make the keys closer together, like on a real piano, the white keys should all be touching, and the black keys should overlap the white keys, centered over the line where the white keys meet. please animate the keys to depress when clicked 
```
### Refine your prompts

Keep trying! Describe your end goal as best you can.
![2](https://cdn.discordapp.com/attachments/1051281685234327613/1145385590943137802/2.png)

![3](https://cdn.discordapp.com/attachments/1051281685234327613/1145385591610023997/4.png)

```
pretty good! thanks a ton for your help. can you center the keyboard vertically in the screen so it's in the middle of the webpage rather than the bottom? please allow the black keys to overlap the white keys, the spacing of the black keys is perfect. you just need to remove the gaps between the white keys
```

You can talk to GPT like a real person, and get pretty good results just by being like, “dude, please help me out here…”

```
the white keys are all different widths, and the black keys have no gap, this should look like a real piano
```
![4](https://cdn.discordapp.com/attachments/1051281685234327613/1145385591895240835/5.png)

After some fiddling around with the css styling, i got this, which I’m really happy with. 

### Bells and Whistles

After settling on the key dynamics, I got to work on a background. I used midjourney to create an image I wanted, and here’s my revised code with this background:

![5](https://cdn.discordapp.com/attachments/1051281685234327613/1145385592209805463/6.png)

Then i had to get to work exporting individual wav files for the sounds, wasn’t too hard. Then I hosted these on glitch to call in my project.

### Make it go BRRR

Then i asked GPT to add a sequence to password gate a pop-up modal

```
this piano is a password gate, a clue will be provided to the game player to indicate the note sequence to reveal a secret password. the note sequence to display the popup modal is:

[PASSWORD REDACTED]

please modify this code so a popup modal appears when the sequence is entered correctly. the popup should be black with grey text
```
I added the functionality for the keyboard so you could play the piano without the mouse, but the depress animation doesn’t take place. I’ll fix that another day! Works great

Take a look at the attached code for examples on how to call audio in your webpages, css styling, .js functionality, and more. These techniques will be similar among all your webpages.

If you have any questions specifically, find me. I'm always happy to help.

Happy building!

