---
icon: lucide/brick-wall
date:
  created: 2026-06-22
  updated: 2026-11-22
categories:
  - Reflecting
---

# Is "Bytes, Boards, Boxes?" still applicable in 2026? 

A university lecture in 1982 provided both a technical framework, and wider life-lessons, but does the lesson stand today? 

<!-- more -->

The complete post continues here.

## Bytes, Boards, Boxes

![Detail of Himalayan Prayer Room](../../images/bbb.png){align=right}

In my final year at university studying computer science, there was one lecture that not only made an impression on me at the time, but in the intervening years has stood the test of time and with reflection has increasingly served as a metaphor for life in general. 

Delivered as a 50-minute lecture as part of a module on computer architecture, the content has been a major takeaway from my entire degree. I am not aware of wWhether or not this is still taught now as part of any computing related degree, but in my humble opinion it really ought to be as I believe the context holds as true today as it was in early 1982.

### A 1982 Approach to architecting computer-based solutions

!!! info inline end "1980s context"

    At the time of the lecture, there was a lot of 
    compute capability available, both in terms of
    processor power or memory capability. Our ability
    to interface computers to the real world was also limited.


The key problem being addressed by this lecture was _what is the best way to go about building a system, based around computing hardware, to meet a requirement?_ One example I saw after university was a hardware design for a firm-control computer for use by artillery. 

Given the paucity of developed compute solution as we know them today required a framework for architectural decisions making:

| Approach   | Description                                                          | Pros                            | Cons                             |
| :--------- | :------------------------------------------------------------------- | :------------------------------ | :------------------------------- |
| :lucide-grid-3x2:`Bytes` | Solution design from individual hardware components  | Can be made very specific to solving need | Difficult to debug / Difficult to customise or update to serve a similar requirement | 
| :lucide-between-horizontal-end: `Boards`   |  Design based upon a combinations of pre-built boards | Boards present pre-debugged chunks of functionality, debug only inter-connections / Potential to repurpose for similar requirements | Not as specific to a solution, may require trade-offs in requirements matching |
| :lucide-package: `Boxes`    |  Use a complete, working box for the solution  | Using a completely debugged solution saves development time  | Solution may need significant compromises to requirements, or software fixes |

The key decision point largely came down to how much time did you have to debug the hardware, Tracey Kidder covered this far better than I ever can in his book [The Sould of a New Machine](https://openlibrary.org/works/OL98218W/The_Soul_of_a_New_Machine) covering teh development of a new computer system, a _Box_ from the components, the _Bytes_.

!!! example "My Real-World Example"

    My first job after university was about addressing the problem of _how can we capture and store voice messages?_ The problem needed to solve some interesting dimensions:

    1. We had to link to a digital telephone line serving voice channels, but the silicon device we had planned for was severely delayed
    1. Storage devices had small capacity, and each voice channels was data intensive[^1]
    1. We needed a general compute server to run a real-time operating system and control everything
    
    The answer we came up with at the time turned out not be a clear cut case of one approach, but a hybrid... 

    - There was no box solution, so that was out immediately
    - There were some board solutions available: processor boards, memory boards, storage controllers so they presented a shot cut to the control portion
    - The boards were linked using {Intel Multibus](https://en.wikipedia.org/wiki/Multibus) as a standard interconnect
    - Our plan to use a simple chip for the telephony link had to change to building a board full of chips, and a lot of debugging
    - The research team came up with a compression solution using early [DSP ssystem on chip](https://en.wikipedia.org/wiki/System_on_a_chip#Digital_signal_processors) soluions which required their own board ... more hardware debugging 
    - All of the above required controlling software


[^1]: Well, 64kbps per channel was deemed very data intensive in the day

### Technically, has 'Bytes - Boards - Boxes' endured?

Many technology changes over the intervening forty years have changed the landscape. One irony is that not long after our work in teh example above, a customisable box solution came available which would have saved some of the time we spent simply getting a set of pre-developed boards working together, but we would still have had the other challenges.

My reflection of the changes amounts to:

- :lucide-grid-3x2: ___Bytes___: Silicon fabrication technology and techniques has created on-chip capabilities way beyond anything we could have anticipated back in 1982, for example a board full of components for a PC board a few years later is now routinely delivered on one silicon component. Our need to string together so many components has reduced.
  
    More recently the componentization of [chiplets](https://en.wikipedia.org/wiki/Chiplet) and the ability to combine chiplets on a single silicon die has moved the whole _Bytes_ architecture decisions towards the large manufacturers and chip fabricators, as well as raising the economic factors in these decisions.
    
- :lucide-between-horizontal-end: ___Boards___: The original approach of a standard interconnect bus with boards plugged in has been largey left behind by the increasing capabilities available on a singly silicon component. This in turn has created an architecture for Single Board Computers SBC) cards such as the Raspberry Pi. 

  However, these SBC products have been developed with defined connectivity, such as the General Purpose I/O (GPIO) standard which supports additional plug-in modules, and some development boards for customised hardware solutions. 

- :lucide-package: ___Boxes___: The _"siliconisation"_ of components, such as storage devices has merged the distinction between boards and boxes, witness the Raspberry PI as delivering what would previously be a box solution as a standalone single board|

The decision frameworx still endures, but the decision points have moved. 

### Bytes - Baords - Boxes as a Metaphor

The main reason that the lecture has stuck with me reflects my experiences in my roles, and life in general. Whenever solving a problem I tend to think of possible solutions, and the impacts in terms of:

| | |
|:--------------- | :-------------------------- |
| ___"Bytes"___ | What happens if we put together a lot of different parts to solve our problem. What are the _integration_ challenges (for example, what do i need X to tell Y) An example could be putting my own holiday plans together from teh individual parts|
| ___"Boards"___ | Are there some integrated parts I can hook into. Using my holiday example, what if I use one company for all my travel needs, flights, car hire etc, and then one hotel chain for different parts of the itinerary?|
| ___"Boxes"___ | Can I get a single solution with everything pre-integrated? A package holiday? A new build house? |


### Final Thoughts - Systems Engineering

In my practice as an Enterprise Architect, this approach based on Bytes - Boards - Boxes as a metaphor is always part of my toolkit, especially when developing options for stakeholders. In working through teh life-cycle of a project, I can map Bytes - Boards - Boxes metaphor over the [Systems ENgineering V Model](https://en.wikipedia.org/wiki/V-model) starting with "Boxes" at teh top level working all teh way down to "Bytes" at the point of the V.

What started as a simple hardware lecture all those years ago has turned into one of the most used tools in the toolbox of my working practice.



