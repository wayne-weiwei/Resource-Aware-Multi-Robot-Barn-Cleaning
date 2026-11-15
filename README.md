# Multi-Robot Manure Cleaning in Dairy Barns: Full-Day Simulation Videos

Supplementary videos for the paper **Resource-Aware Multi-Robot Coverage Path Planning for Continual Manure Cleaning**
(Wei Wei, Congcong Sun, and Jianglin Lan; submitted to Computers and Electronics in Agriculture).

Each video replays one full day (24 h) of simulated barn cleaning, compressed into about 30 s. Cows move between cubicles, feeders, drinkers and milking areas and block and reopen the alleys, while manure is deposited throughout the day. The cleaning robots return to their stations for water, manure disposal and charging. Our planner, RA-CRH, is shown side by side with five baseline planners under exactly the same barn, cows and robot settings.

## Video Layout and Labels

Each video has six panels, one per planner: **RA-CRH (ours)**, **Greedy**, **Ponce (2026)\***, **Yazici et al. (2014)\***, **Cai et al. (2025)\*** and **Boustrophedon**. The asterisk marks our implementations of published methods.

Each panel contains:

- **Map:** Dark grey cells are fixed obstacles such as cubicles and feed bunks; the remaining cells form the floor to be cleaned.
- **Floor shading:** How often each cell has been cleaned so far (darker blue means more often; white means not yet cleaned).
- **Cows and manure:** Orange blocks are cow bodies; brown dots are manure that has not yet been removed.
- **Robots:** Coloured lines show the recent path of each robot. A red circle marks a robot and a cow in the same grid cell.
- **Panel title:** The share of the floor cleaned at least once so far and the number of uncollected manure deposits, followed by two full-day results:
  - **c_min**, the minimum window coverage: the lowest fraction of the floor cleaned within any 4-h cleaning window (higher is better);
  - **a95**, the 95th percentile of the time since a cell was last cleaned (lower is better).

## How the Clips Were Selected

The clips were not chosen to show the best case. For each barn, the condition shown is the one with the median difference in c_min between RA-CRH and Greedy across all conditions of that barn in the paper, the same rule used for the path figure in the paper. Every replay was rerun and checked against the results reported in the paper before rendering.

## Clip Descriptions

### 1. Ponce Barn B: Most Restricted Access


https://github.com/user-attachments/assets/c2edfb1e-26b6-4e45-8049-6fc5d83e8d42


Two robots clean a barn with 175 cows in which cows frequently cut off large parts of the floor. RA-CRH is the only planner that cleans every cell at least once during the day; the baselines leave 12–21% of the floor uncleaned. RA-CRH also achieves the highest c_min (0.545 versus 0.321 for Greedy) and the lowest a95 (428.3 versus 990.4 min for Greedy).

### 2. Ponce Barn A


https://github.com/user-attachments/assets/a89bea0a-17bf-4b93-a138-6aa4d32ed214


Three robots clean a barn with 175 cows. Five of the six planners clean the whole floor at least once, so the difference lies in how regularly the floor is cleaned. RA-CRH achieves c_min = 0.875 and a95 = 208.4 min, compared with 0.682 and 304.7 min for Greedy, and completes four whole-floor cleaning rounds against three for Greedy.

### 3. Six-Row Barn


https://github.com/user-attachments/assets/062eaa10-c689-4c0e-9f67-5adadd39b236


Six robots clean a barn with 216 cows. RA-CRH cleans nearly the whole floor in every 4-h window (c_min = 0.995, compared with 0.901 for Greedy) and lowers a95 from 194.2 to 109.7 min. It completes seven whole-floor cleaning rounds against five for Greedy, at the cost of more driving (60.4 versus 45.6 robot-hours).
