COMP3330 - HiPhi Report - AI In Games
=====================================

* Beau Gibson - C3146845
* Tyler Haigh - C3182929
* Simon Hartcher - C3185790
* Rob Logan - C3165020

# Introduction #

Video Games form a rapidly growing industry moving towards an artistic form that both programmers and players can appreciate ([Wexler, 2002](http://www.cs.rochester.edu/~brown/242/assts/termprojs/games.pdf)). The term "Game AI" encompasses programming and design practices, including path-finding algorithms, neural-networks, models of interaction, state machines, and decision trees, all with the common goal of providing some intelligent behaviour ([Mateas, 2003](http://lmc.gatech.edu/~mateas/publications/MateasDIGRA2003.pdf)). Game AI aims to establish the belief in a living entity within the computer that can act independently of the player.

## The Founding Fathers ##

Game AI shares its foundations with the rise of digital processing. Claude Shannon and Alan Turing started developing chess programs as early as 1950. Board games were the popular choice for experimenting with Artificial Intelligence due to their nature of perfect information - the entire state of the game can be captured by the computer. They are typically non-trivial search problems with no well-defined path to a given solution as the involvement of an opponent introduces a degree of uncertainty ([Middleton, 2002](http://web.stanford.edu/group/htgg/sts145papers/zmiddleton_2002_1.pdf)).

## The Early Years ##

During the early years of video games, AI was not a feature due to the simplicity of the games produced, and human centred design.

In 1949, Claude Shannon published the paper *Programming a Computer for Playing Chess* in which he describes how a machine can decide how to move such that it can minimise the possible loss in the worst case scenario ([Shannon, 1949](http://www.pi.infn.it/~carosi/chess/shannon.txt)). His reasons for using chess as the basis for his paper include:

* The legal move-set and the end goal is well defined
* It is neither a trivial problem, nor too difficult to calculate a viable solution
* There is a element of skilful thinking involved
* The discrete structure of chess fits well into the design of computers

A computerised version of Nim was published in 1952, and was able to consistently win games against players 95% of the time ([The New Yorker, 1952](http://www.newyorker.com/magazine/1952/08/02/it))

`TODO: Expand this`

# The Golden Age #

The Golden Age of Video Games revolutionised how we develop and play games today.

## Game of Life ##

Game of Life is a deterministic, zero-player based, cellular automaton  game developed by Brittish Mathematician John Conway. Conways rules for genetic change are designed to make behaviour of the population unpredictable ([Gardner, 1970](http://web.archive.org/web/20090603015231/http://ddi.cs.uni-potsdam.de/HyFISCH/Produzieren/lis_projekt/proj_gamelife/ConwayScientificAmerican.htm))

* Every counter with two or three neighbouring counters survives for the next generation
* Every counter with four or more neighbours dies from overpopulation
* Every counter with one neighbour or none dies from isolation
* An empty cell adjacent to exactly three neighbours is a birth cell
* All births and deaths occur simultaneously consituting a single generation

## Discrete Logic ##

Atari released the infamous Pong in 1972, a table tennis simulator that can be played between two people, but more importantly with a computer controlled opponent. The core intelligence of these games was established using disrete logic (i.e. hardcoded logic gates). ([Monfort, Bogost, 2009](http://books.google.co.uk/books?id=DqePfdz_x6gC&lpg=PP1&dq=racing+the+beam&pg=PA40&hl=en#v=onepage&f=false)).

PacMan, released in 1980, introduced AI patterns in maze environments, with individual pesonalities (or strategies) assigned to each enemy ghost. Ghosts were given specific "goal tiles" depending on their personality which could be exploited by players who knew the underlying discrete logic.

This discrete logic only gives the illusion of intelligence. This illusion provides little or no actual game logic or decision making and was mainly used due to memory constraints at the time.

## Randomness ##

Random number generators are intelgral to Game AI. It makes the games feel more immersive and "real". Random numbers drive many decisions and events for in-game objects such as graphical effects (rain or transitions), frequency and choice of sound effects, and enemy behaviour.

([Doom, 1997](https://github.com/id-Software/DOOM)) is a primary example of using randomness to esstablish interesting features in a game. It uses an array of 256 integers that are sorted randomly, and stored in a static lookup table. The game references these "seeming random" values throughout the game to make the game more dynamic.

Jonathan Dowland examined the behaviour of Doom when all values in the "random value" lookup table were set to all 0 (0x00 in Hexadecimal) or 255 (0xFF) ([Downland, 2015](http://jmtd.net/log/deterministic_doom/)). The following are some of his findings:

* Monster make the same sound effect
* Hitscan weapons (shotgun, chaingun) have no spread
* Lights will strobe, or never flicker
* Damage values don't vary
* Monsters will never make an idle sound with 0x00, but with 0xFF, they constantly play, drowning everything out

# The 90's Explosion #

As the arcade and video game industry began to wane in the late 80's, gamers began to crave a better quality of gameplay. The goal of the industry then was to create a more challenging and lifelike opponent, which would react to the player like a human.

## Real Time Strategy ##

## Colin McRae - Use of Neural Networks ##

# Current Research Topics #
The primary goal of Game AI is to entertain. As such, developers tend to avoid using true "academic" AI, opting for short-cuts and efficiency, whilst maintaining some level of intelligence in the system.

Instead, researchers have redefined the role of artificial intelligence in video games by replacing all human interaction with intelligent agents. This concept of General Game Playing requires agents to be able to play numerous types of games without reliace on dedicated algorithms, designed specifically for a particular game. In this case, IBM's Deep Blue, the first intelligent computer to defeat the world chess champion, would not be sufficient as it was designed to play chess, and hence would not perform as well when playing checkers. ([Genesereth, Love, Pell, 2005](http://www.aaai.org/ojs/index.php/aimagazine/article/download/1813/1711))

## Google AI - DeepMind Technologies ##

Founded in 2011 by Dennis Hassabis, and acquired by Google in 2014, Google DeepMind aims to combine "the best techniques from machine learning and systems neuroscince to build powerful general-purpose learning algorithms" ([DeepMind, 2015](http://deepmind.com/)).

In 2013, DeepMind published a report detailing the success in using Reinforcement Learning environments, and sensory data, to train a neural network to play Atari 2600 games ([NIPS, 2013](http://arxiv.org/pdf/1312.5602v1.pdf)). Using a modified Q-Learning (a model free) reinforcement learning algorithm, and stochastic gradient descent to update the network weights, their paper proposed a new deep learning model for reinforcement learning and demonstrated its effectiveness at mastering seven Atari 2600 games using only the raw pixels and game score as input.

In an interview with Dennis Hassabis, their network starts off with no prioir knowledge of the game ([The Verge, 2015](http://www.theverge.com/2015/2/25/8108399/google-ai-deepmind-video-games)). Early training interations involve the network randomly pressing mapped buttons in order to determine the basic controls and inputs. As expected with Reinforcement Learning, the network adapts to the new game by playing. An interesting observation made was that the network was unable to plan long term actions and hence, struggled with learning maze-based games, such as PacMan.

## The "Mario Lives!" Project ##

The Association for the Advancement of Artificial Intelligece (AAAI) holds an annual video competition to showcase the advances in artificial intelligence in a fun and exciting means.

Computer scientists from the Cognitive Modelling Group at the University of Tubingen, Germany, submitted the *Mario Lives* project as part of this competition in 2015. Their aim was to develop an artifical agent that can become alive in its own world.

In the demonstration, Mario is shown to learn from his own experiences. After jumping on Goomba, he is asked "What do you know about Goomba?". The speech recognition and context grammar that underpins the agent allows Mario to respond with "If I jump on Goomba, then it maybe dies". Mario is als shown to learn from what it is told. Mario is told "Goomba dies, when you jump on Goomba". He is able to store this information and refer to it as he responds "If I jump on Goomba, then it certainly dies". ([Ehrenfeld, et. al., 2015](https://www.youtube.com/watch?v=K0nlO87evhY))

"Mario developes a schema based knowledge base, and maintains internal emotive states". These emotive states are used to drive behavioural actions. When he is hungry, Mario will collect coins.

# References #

1. James Wexler, *Artificial Intelligence in Games*, http://www.cs.rochester.edu/~brown/242/assts/termprojs/games.pdf, University of Rochester, 2002
2. Grant, Lardner, *IT*, http://www.newyorker.com/magazine/1952/08/02/it, The New Yorker, 1952
3. Michael Mateas, *Expressive AI: Games and Artifical Intelligence*, http://lmc.gatech.edu/~mateas/publications/MateasDIGRA2003.pdf, The Georgia Institute of Technology, 2003
4. Zak Middleton, *Case History: The Evolution of Artificial Intelligence in Computer Games* http://web.stanford.edu/group/htgg/sts145papers/zmiddleton_2002_1.pdf, Stanford, 2002
5. Nick Motfort, *Racing the Beam: The Arati Video Computer System (PLatform Studies)*, http://books.google.co.uk/books?id=DqePfdz_x6gC&lpg=PP1&dq=racing+the+beam&pg=PA40&hl=en#v=onepage&f=false, ISBN: 9780262261524
6. Botea, Herbrich, Graepel, *Video Games and Artificial Intelligence*, http://research.microsoft.com/en-us/projects/ijcaiigames/, Microsoft Research, 2015
7. *Interview with Jeff Hannan*, http://www.ai-junkie.com/misc/hannan/hannan.html, AI-Junkie, 2001
8. Siyuan Xu, *History of AI Design in video games and its development in RTS games*, https://sites.google.com/site/myangelcafe/articles/history_ai, Xu, n.d.
9. Claude Shannon, *Programming a Computer for Playing Chess*, http://www.pi.infn.it/~carosi/chess/shannon.txt Shannon, Published in Pilosophical Magazine, 1950
10. *DeepMind Technologies*, http://deepmind.com/ DeepMind Technologies, 2015
11. Mnih, et. al. *PLaying Atari with Deep Reinforcement Learning*, http://arxiv.org/pdf/1312.5602v1.pdf, DeepMind Technologies, Published by NIPS, 2013
12. The Verge, *Google's AI can learn to play video games*, http://www.theverge.com/2015/2/25/8108399/google-ai-deepmind-video-games, 2015
13. Genesereth, Love, Pell, *General Game Playing: verview of the AAAI Competition*, http://www.aaai.org/ojs/index.php/aimagazine/article/download/1813/1711, AI Magazine, 2005
14. Ehrenfeld, et. al., 2015, *Mario Lives! An Adaptive Learning AI Approach for Generating a Living and Conversing Mario Agent* https://www.youtube.com/watch?v=AplG6KnOr2Q, AAAI, 2015
15. Martin Garnder, *Mathematical Games. The fascinating combinations of John Conway's new solitare game "life"*, http://web.archive.org/web/20090603015231/http://ddi.cs.uni-potsdam.de/HyFISCH/Produzieren/lis_projekt/proj_gamelife/ConwayScientificAmerican.htm, Scientific American, 1970
16. Jonathan Dowland, Deterministic Doom, http://jmtd.net/log/deterministic_doom/, JMTD, 2015