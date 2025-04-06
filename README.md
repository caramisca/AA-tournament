# AA-tournament
# Rocky Algorithm Description

The "Rocky" algorithm is a strategy designed for the Iterated Prisoner's Dilemma (IPD) game. It adapts its behavior based on the history of the opponent's moves, aiming to maximize long-term cooperation while minimizing exploitation.

## Key Features

1. **Initial Cooperation**:
   - The algorithm starts by cooperating in the first round, which sets a cooperative tone from the start.

2. **Cooperation Rate Analysis**:
   - Rocky tracks the opponent's cooperation rate over time. If the opponent cooperates more than 80% of the time, Rocky will continue to cooperate as well. This encourages a cooperative environment.
   - If the opponent defects too frequently (less than 20% cooperation), Rocky will defect to protect itself from being exploited.

3. **Recent Behavior Analysis**:
   - The algorithm considers recent moves (the last 5) from the opponent. If the opponent has recently cooperated, Rocky will continue cooperating. If the opponent's behavior is unpredictable or defection is detected, it will adjust its response accordingly.

4. **Mimic Strategy**:
   - If the opponent has consistently mirrored Rocky's moves, the algorithm will mimic the opponent’s behavior. This allows Rocky to "build trust" if the opponent behaves in a cooperative way.

5. **Defection Patterns**:
   - If the opponent exhibits specific patterns of defections, such as alternating between cooperating and defecting (e.g., `[1, 0, 1, 0]`), Rocky will choose to defect in response. This pattern recognition helps Rocky to avoid being exploited by cyclical defectors.

6. **Threshold for Cooperation**:
   - If the cooperation rate is very high (greater than 80%), Rocky will cooperate. Conversely, if the cooperation rate is very low (less than 20%), Rocky will defect.
   - When the cooperation rate is moderate (between 40% and 60%), the strategy becomes more reactive: if Rocky defected on the previous round, it will cooperate, and if it cooperated previously, it will defect.

7. **Long-Term Adjustment**:
   - After 10 rounds, if the opponent has consistently defected (i.e., the sum of their history is zero), Rocky will defect.
   - If the opponent has cooperated every time (i.e., the sum of their history equals the total number of rounds), Rocky will cooperate to reward consistent cooperation.

## Algorithm Behavior

- The algorithm reacts to the opponent’s behavior by analyzing their recent moves and calculating the cooperation rate over time.
- It will cooperate or defect based on the following conditions:
  - **High cooperation rate**: The algorithm cooperates.
  - **High defection rate**: The algorithm defects.
  - **Patterns of behavior**: It identifies patterns such as alternating defecting and cooperating and adjusts accordingly.
  - **Mimicking**: The algorithm will mimic the opponent's previous move if they have been cooperating with it.

## Conclusion

The Rocky algorithm is a balanced approach that promotes cooperation when possible but adjusts its strategy based on the opponent's behavior. It uses a mix of cooperation rate analysis, recent behavior patterns, and mimicry to determine the best course of action. Its adaptability helps it thrive in diverse competitive environments.
