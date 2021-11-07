# Pommerman

## Monte Carlo Tree Search with Progressive Bias and Decaying Reward

### Setup

* Open the project using a suitable IDE, such as [IntelliJ](https://www.jetbrains.com/idea/).
* Clone the following repository: `git clone https://github.com/GAIGResearch/java-pommerman`
* Naviagte to the `players` directory:
```
java-pommerman
│   README.md  
│   
└───...
│   
└───src
│   │   
│   └───core 
│   │   
│   └───...
│   │                   
│   └───players
│   │   │    
│   │   └───mcts
│   │   │   
│   │   └───...
│   │   │    
│       └───rhea
```

* Clone this repository to the `players` package of `java-pommerman`: ``  
```
java-pommerman
│   README.md  
│   
└───...
│   
└───src
│   │   
│   └───core 
│   │   
│   └───...
│   │                   
│   └───players
│   │   │    
│   │   └───mcts
│   │   │   
│   │   └───...
│   │   │    
│       └───rhea
```

* \[arg index = 1\] Number of level generation seeds \[S\]. "-1" to execute with the ones from the paper (20). <br>
* \[arg index = 2\] Repetitions per seed \[N\]. "1" for one game only with visuals. <br>
* \[arg index = 3\] Vision Range \[VR\]. (0, 1, 2 for PO; -1 for Full Observability)<br>
* \[arg index = 4-7\] Agents. When in TEAM, agents are mates as indices 4-6, 5-7: <br>
	* 0 DoNothing <br>
	* 1 Random <br>
	* 2 OSLA <br>
	* 3 SimplePlayer <br>
	* 4 RHEA 200 itereations, shift buffer On, pop size 1, random init, length: 12 <br>
	* 5 MCTS 200 iterations, length: 12 <br>
	* 6 Human Player (controls: cursor keys + space bar)  <br>


Examples: 
 * A single game with full observability, FFA. This is also the default mode when no arguments are passed:
 	* *java -jar run.jar 0 1 1 -1 2 3 4 5*
 * A single game with partial observability, FFA, where you're in control of one player:
 	* *java -jar run.jar 0 1 1 2 0 1 2 6*
 * Executes several games, headless, FFA. Two different random seeds for the level generation, repeated 5 times each (for a total of 5x2 games). 
 	* *java -jar run.jar 0 2 5 4 2 3 4 1* 
 * Executes several games, headless, TEAM, repeated 10 times each. Same configuration as the one used in the paper, including the 20 seeds.
 	* *java -jar run.jar 1 -1 10 4 5 3 5 3* 


Notes:
 * If you provide N=1, the program will run a single game, with graphics on, using the agents specified in parameters 4-7.
 * If you provide S=-1, the program will run N games with the *specific _20_ seeds* used in the AIIDE 2019 paper (graphics off, results reported at the end).
 * If you provide any other S>1, the program will run N games with *_S_ random seeds* (total games, NxS), graphics off, using the agents specified in parameters 4-7 and results being reported at the end.
 * The Human Player (option 6) is only available when N=1.

You can modify the code to execute different games as well (i.e. different agents or their parameters). For extra Java-pommerman wiki/documentation, visit this: https://github.com/GAIGResearch/java-pommerman/wiki

All games you play are logged in res/gamelogs/



