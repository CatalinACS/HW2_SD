# Tree-Based Game Implementation

## Project Overview
This assignment involved implementing a tree-based game system with three distinct problems, completed over 2 weeks and 4 days. The project demonstrates advanced tree data structures, game state management, and minimax algorithm implementation.

## Development Timeline

### Week 1: Foundation and Problem 1
**Duration**: 7 days  
**Focus**: Core infrastructure and first problem solution

#### Achievements
- **Data Structures**: Created all necessary tree structures and processing functions
- **File I/O**: Implemented input processing using `while(fgets(..))`
- **Problem 1**: Successfully solved the first assignment problem
- **Algorithm Development**: Created a position counting/tracking algorithm using counters

#### Challenges
- **Memory Management**: Extensive Valgrind errors within the `add` function
- **Algorithm Design**: 3-4 days spent developing the position tracking algorithm
- **Debugging**: Initial memory leak issues requiring careful pointer management

---

### Week 2: Problem 2 and Major Debugging
**Duration**: 7 days  
**Focus**: Tree processing and complex memory management

#### Implementation Details
- **Core Function**: Developed `Prelucrare_Arbore_TF` function
- **Code Reuse**: Utilized portions of the `add` function from Week 1
- **Data Storage**: Implemented stack-based node storage system

#### Major Challenges
- **Segmentation Faults**: Extensive SIGSEGV errors requiring GDB debugging
- **Memory Management**: Required triple pointer usage for proper memory deallocation
- **Debugging Phase**: 2-3 days dedicated to error resolution

#### Debugging Tools
- **Valgrind**: Primary tool for memory error detection
- **GDB**: Essential for segmentation fault debugging
- **Memory Architecture**: Triple pointer implementation for complex memory cleanup

#### Technical Innovation
- **Stack Implementation**: Used for saving tree nodes
- **Node Information**: Stack stores `GenericTree*` data field information
- **Memory Strategy**: Complex but necessary approach for proper cleanup

---

### Final 4 Days: Problem 3 and Completion
**Duration**: 4 days  
**Focus**: Minimax algorithm and final integration

#### Problem 3 Implementation
- **Algorithm Research**: Studied the minimax algorithm from Lab 06 Algorithms Programming
- **Implementation**: Straightforward max/min value calculation at each function call
- **Integration**: Main solution logic implemented in `main` function

#### Technical Components
- **String Processing**: Used `strtok` for parsing sequences like `'(num1) (num2) [num3]..'`
- **Tree Construction**: `Tree_Build` variable for dynamic tree building
- **Edge Formation**: `Tree_Aux` variable handles:
  - Edge creation for round parentheses
  - Numeric value storage for square brackets

#### Final Challenges
- **Memory Issues**: Continued Valgrind problems requiring 3-4 days resolution
- **Output Formatting**: Implemented indentation using `\t` characters
- **Resource Cleanup**: Extensive variable management for memory deallocation

## Game Architecture

### Game State Representation
The system models game progression through a tree structure:

```
We start with O in the input file -> X moves.
             X O X
             O X X
             O X O
            ^
           /
      X O X
      O X X
      O X -
      ^
     /
- O X
O X X
O X -
     \
      v
       - O X
       O X X
       O X X
```

### Tree Structure
```
                        Initial_State
                        /             \
                       v               v
                Stare1_Level1          Stare2_Level1
                                                    \
                                                     v
                                                     Stare1_Level2
```

## Data Structure Design

### Node Structure Fields
- **`character`**: Character to be placed ('X'/'O' or 'T'/'F')
- **`edge`**: Number of outgoing edges from the node
- **`val`**: Numeric value stored in the node
- **`Next_Node`**: Array of pointers to child nodes
- **`gametable`**: Game board stored as `char**`

### Navigation Examples
- `Initial_State->Next_Node[1]` → `Stare2_Level1`
- `Stare2_Level1->Next_Node[1]->gametable` → Access to game board
- `Stare1_Level2->Next_Node[1]` → `NULL` (leaf node)

## Problem Solutions

### Problem 1: Position Tracking
- **Algorithm**: Counter-based position detection
- **Implementation**: Custom tracking system for game positions
- **Challenges**: Memory management in the add function

### Problem 2: Tree Processing
- **Core Function**: `Prelucrare_Arbore_TF`
- **Architecture**: Stack-based node management
- **Innovation**: Triple pointer memory management
- **Integration**: Reused components from Problem 1

### Problem 3: Minimax Implementation
- **Algorithm**: Standard minimax with max/min value calculation
- **Parsing**: `strtok`-based sequence processing
- **Tree Building**: Dynamic construction using `Tree_Build`
- **Output**: Properly indented tree representation

## Technical Implementation

### Memory Management Strategy
- **Variables Used**: 
  - String variables: `sir1`, `sir2`, `sir3`
  - Integer counters: `14`, `17`, `2`, etc.
  - Cleanup variables: `Tree_Aux_Free1`, `Tree_Aux_Free2`
- **Approach**: Systematic deallocation of all dynamic memory
- **Challenge**: Complex pointer relationships requiring careful cleanup

### Parsing System
- **Input Format**: Mixed parentheses notation `'(num1) (num2) [num3]..'`
- **Strategy**: `strtok`-based tokenization
- **Logic**: 
  - Round parentheses → Edge formation
  - Square brackets → Value storage

### Output Formatting
- **Indentation**: Tab character (`\t`) for proper tree visualization
- **Structure**: Hierarchical representation of game states
- **Readability**: Clear formatting for debugging and analysis

## Development Insights

### Debugging Experience
1. **Week 1**: Initial memory management challenges
2. **Week 2**: Complex segmentation fault resolution
3. **Final Days**: Valgrind compliance and memory cleanup

### Tool Effectiveness
- **Valgrind**: Essential for memory error detection
- **GDB**: Critical for runtime debugging
- **Systematic Approach**: Week-by-week problem solving

### Lessons Learned
- **Memory Management**: Triple pointers are necessary for complex structures
- **Algorithm Research**: External resources valuable for implementation
- **Incremental Development**: Problem-by-problem approach managed complexity

## Project Complexity Assessment

### Challenge Rating: Non-Trivial
- **Data Structure Complexity**: Multi-level tree with game state storage
- **Memory Management**: Advanced pointer manipulation required
- **Algorithm Integration**: Multiple algorithmic approaches combined
- **Debugging Intensity**: Significant time investment in error resolution

### Success Factors
1. **Systematic Approach**: Problem-by-problem implementation
2. **Thorough Debugging**: Extensive use of debugging tools
3. **Research Integration**: External algorithm study
4. **Memory Discipline**: Careful resource management

## Final Architecture

### Core Components
1. **Game State Tree**: Hierarchical game progression representation
2. **Memory Management**: Advanced pointer-based cleanup system
3. **Minimax Engine**: Optimal move calculation
4. **I/O Processing**: File-based input parsing
5. **Output System**: Formatted tree visualization

### Supported Features
- Dynamic tree construction
- Game state tracking
- Optimal move calculation
- Memory-safe operations
- Formatted output generation

## Conclusion
This implementation demonstrates sophisticated tree data structure usage, advanced memory management techniques, and algorithmic problem-solving. The multi-week development process provided extensive experience in debugging complex pointer-based systems and integrating multiple algorithmic approaches into a cohesive solution.
