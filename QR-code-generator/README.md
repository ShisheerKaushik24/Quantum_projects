QR code Generator

The QR code system was invented in 1994 by Masahiro Hara from the Japanese company Denso Wave.[3] The initial design was influenced by the black and white pieces on a Go board.[4] Its purpose was to track vehicles during manufacturing; it was designed to allow high-speed component scanning, known as CP 1919. The signal was significant for many reasons, including being thought to be an extraterrestrial beacon. But for me, the significance of the CP 1919 is its eventual use in the album artwork for Joy Division's Unknown Pleasures. It is one of the most beautiful and recognizable visual adaptations of scientific data.

To honor that legacy, you can create a similar image by typing in the box below, but instead of using pulsar data, it uses data from a quantum computer.

<image src="./Captur.jpg">

Project Summary 

The above demo creates an image with a quantum computer. Even better, the image is a word written by a quantum computer. Each line shows the amplitude of the binary representation of a letter of as an output of the Bernstein-Vazirani algorithm. 

Didn't understand that sentence? That's okay. Let's break it down and get into some details.

First, let's talk about how quantum computers work a little bit. I'm going to skip some of the fundamentals, as its been said many times by people much more knowledgeable than myself, like this video.

For our purposes here, the important part is that unlike regular (or classical) computers, quantum computers use the effects of interference, a behavior only found in quantum physics, to get to a right answer in less steps. These computers are manipulating really delicate states which have lots of errors and may not get the right answer all the time, so we run an algorithm over and over to amplify the right answer. For example, a typical result from a quantum computer looks something like this.

<image src="./histogram1.png">
  
Whatever the quantum computer was trying to compute, we can see that the right answer is that tall column in the middle. All those other little bars in our histogram are a result noise. Today's quantum computers aren't perfect, so there will be noise in our results, but in this case, our correct answer is still fairly clear. For the sake of creating a visualization, I think the noise is beautiful and adds to the final effect. Once quantum computers are fully fault tolerant, this visualization will be a lot more boring. For once, the noise is a good thing.

So what is it calculating, and what is the answer? Let's add some more data to our histogram.

<image src="./histogram2.png">
  
As you can see, each bar is labeled with a series of 0s and 1s. These are 7 bit binary strings, and our amplified answer is "1010001", which is binary for the letter "Q". This means that our quantum computer is amplifying the letter Q, the first letter of Qiskit, which is exactly what we want! (For those really paying attention, text to binary is often written as 8 bits, starting with a 0 or 0b, but more on that later in the FAQs).

