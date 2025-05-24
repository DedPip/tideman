# Tideman Voting System (Ranked Pairs)

This program implements the **Tideman voting system**, also known as the **Ranked Pairs** method, in C. It allows voters to rank candidates in order of preference and determines the winner using a directed graph approach, while ensuring no cycles are formed.

---

## Features

- Accepts up to **9 candidates**
- Allows voters to **rank all candidates**
- Records all **pairwise preferences**
- Sorts pairs by **strength of victory**
- Builds a directed graph without cycles
- Determines the winner as the **source of the graph**

---

## How It Works

1. **Collect Input**  
   Users provide candidate names as command-line arguments and then enter the number of voters and their ranked votes.

2. **Record Preferences**  
   Builds a 2D matrix of how many voters prefer candidate A over candidate B.

3. **Add Pairs**  
   Records all pairs of candidates where one is preferred over the other.

4. **Sort Pairs**  
   Sorts the pairs by the margin of victory in descending order.

5. **Lock Pairs**  
   Constructs a directed graph of locked-in pairs, making sure no cycles are created (i.e., no candidate beats itself indirectly).

6. **Print Winner**  
   The candidate with **no incoming edges** in the final graph is declared the winner.

---

## Usage

```bash
$ ./tideman Alice Bob Charlie
Number of voters: 3
Rank 1: Alice
Rank 2: Bob
Rank 3: Charlie

Rank 1: Bob
Rank 2: Charlie
Rank 3: Alice

Rank 1: Charlie
Rank 2: Alice
Rank 3: Bob

Alice