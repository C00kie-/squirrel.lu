# PineTime and Infinitime OS

  A few months ago I came with a need for having a smart watch that record heart rate speed and count daily steps. I had a few conditions:
  - I didn't want to send my data to China.
  - I didn't want to pay 400+$ for it.
  
I also wanted to have a hand on data and why not, [code something](https://www.mit.edu/~amidi/teaching/data-science-tools/study-guide/data-visualization-with-r/) to understand patterns of my activity to help physical preparation for climbing. 

  I also was very curious about all these programs that we use daily to keep track of our health work, and how everything is packaged into small devices that we wear (it seems like hardware design constrains to me)

           _
          |E]
        .-|=====-.
        | | mail |
     ___|________|
            ||
            ||
            ||   www
     ,;,    ||   )_(,;;;,
     <_>  \ ||   \|/ \_/
     \|/  \\||  \\|   |//

~~~
 *dring dring!
- "you got a delivery" //no it's not amazon
- "ho nice!"
~~~
 And so I received the watches. :-p


# An Open-source smartwatch

**[PineTime](https://www.pine64.org/pinetime/) is an open source smart watch. It's all programmable.**

The watch comes in two setups:
- one with a sealed watch, for "normal" usage only.
- a developper one, where the watch isn't sealed, in which you can access everything. Here the hardware seems to be pretty accessible and things easy to get going.

## A sealed device

As I just received both, I wanted to start to use the device and see then what is inside (application), what is lacking and how I can contribute to development*.

The more I dig into the doc and the more I saw that there is a lot of possibilities of development, and learning.

As from hardware level to software level, everything is open, it's a nice project to understand how parts (hardware and software) work together.

*Development is to be on the not sealed watch, in the developer kit.

## PineTime quickstart

This blogpost takes a lot of information directly from the documentation of the project, what I invite you to read extensively ;) I invite you to put an issue on the repo's project if something isn't clear there.

But so far, it's one of best documentation I've seen an IoT project, it's really human readable and smart.

So, the goal of this post is just to give you "quick start" advices and references if you want to dig into it :)


Once you get the watch out and turns it on, you'll have to do a few configuration to be able to use it "out of the box":

- update the firmware to use the last stable version that fixes initial bugs (not sure if they are still in production but as the initial firmware version was 0.7.0 I guess it is)
- set the watch on time

### You'll need:
- **documentation** : 
[on github](https://github.com/JF002/Pinetime/blob/develop/doc/gettingStarted/gettingStarted.md)

- **the releases page** : 
[on github](https://github.com/JF002/Pinetime/releases)

### (!) Careful about firmware update: check the last stable version for sealed watch only.

### (!) for updating the firmware and time I chose the most secure way to do it* : OverTheAir update using nRF Connect**, and direct download of the DFU file you'll push to the device.

*(in the way that the less use of alternative softwares that question at each step the chain of trust is good to take ;) )

** [Nordic Semi conductor website](https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Connect-for-mobile)


