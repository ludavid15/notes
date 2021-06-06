---
layout: post
title: Twelve Tone Equal Temperatment
permalink: /twelveTone/
mathjax: true
except_separator: <!--more-->
categories: music
---

If you've taken any kind of music lesson before, chances are you were introduced to the western classical system of notation, otherwise known as twelve-tone equal temperament. In this system, each octave is subdivided into 12 notes, labeled A through G. 
 
So much of music theory is based on this system that it's easy to forget what it is - a constructed language that approximates something physical. 

That physical thing in question being acoustic waves traveling through the air. These waves (like all waves) carry a frequency, amplitude, and waveform. What we call pitch is the first of these - the frequency. 

<!--more-->

To build a bridge between music theory and physics, let us begin with intervals. If we define the note **A** at 1 hz and then double the frequency to 2 hz, the resulting note is defined in our musical langauge as being 1 octave higher. 

> In western music, two notes that are an octave apart are considered the same "note". For this reason, they recieve the same label, although a number is sometimes used to indicate how high the note is. However, not all musical languages may recognize the concept of an octave, and after all, why should they? Even though we say two notes an octave apart are the same, they clearly are not - one is much higher in pitch than the other. Be careful to remember that the language we have shapes our perspective of the world. 

We could continue to double each frequency (1, 2, 4, ...) and find a series of notes spaced 1 octave apart, but this musical scale is pretty limiting. So how do we define other intervals? Well, let's take other ratios along the set of positive integers. 

$$1, 2, 3, 4, 5, 6, 7, 8, 9, 10, ... $$

| 2/1   | 3/2   | 4/3    | 5/4          | 6/5           | 7/6 | 8/7 | 9/8        |
|octave | fifth | fourth | major third  | minor third   | ??  | ??  | whole step |

Notice that each subsequent ratio gets closer and closer to 1. In this way we achieve smaller and smaller intervals. There's also nothing wrong with 7/6 or 8/7, those particular intervals just aren't defined in our musical theory language. 

But are these intervals any good? Like many things, the answer is: it depends. They certainly *sound* nice, but these all lack an important feature: they don't return to the same point. 

Let's take a whole step: 9/8. If we start on a note and travel up 7 whole steps, we get to:

$$(9/8)^6 = 2.0272$$

Which is NOT an octave. Almost, but not quite. Whole steps are also unable to build any to any of the other intervals. 

$$(9/8)^3 = 1.42$$

Which is neither equal to 3/2 or 4/3. In fact, this basic problem extends for any interval defined with the ratio of positive integers. This is where 12-tone equal temperament comes in. The frequency ratio for a half step is set to be the twelfth root of two.

$$^{12} \sqrt{2}$$

This way, any pair of notes 12 half steps apart form a perfect octave. This allows us to freely move about the piano and play in any key, at the cost of perfect intervals ratios. The approximations of each perfect ratio in this system become:

| Exact ratio       | 2/1   | 3/2   | 4/3   | 5/4    | 6/5  | 9/8   |
| As decimal        | 2.0   | 1.5   | 1.333 | 1.25   | 1.2  | 1.125 | 
| 12-tone approx.   | 2.0   | 1.498 | 1.335 | 1.26   | 1.19 | 1.123 |

As you can see, except for an octave which remains perfect, each 12-tone interval is very slightly off from the corresponding "just intonation" interval. In most cases, the variation is small enough that it very nearly sounds the same. 

















