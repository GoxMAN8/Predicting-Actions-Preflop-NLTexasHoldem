# Predicting-Actions-Preflop-NLTexasHoldem

Project part of the module INM430, Principles of data science, City University, London

Motivation 

The motivation of this paper, comes from the authors’ personal opinion, that any solution to games with imperfect information could be further improved via human/machine interaction. Statistical software programs, like Poker Tracker 4, and Holdem Manager 2, provides players with huge number of real time statistics to dive in, while making a decision. This paper investigates some of the most important variables affecting decisions in poker, on two levels. First are variables, available at any single poker hand2 – ‘’hand environment’’. Second part, are sticky characteristics calculated as sum of actions, for the fixed time into the past. Latter is much more difficult to incorporate into the modern algorithms, as it increases computational needs substantially, acting as agents’ short-term memory.

Main goal of this paper is to distinguish and rank features according to the importance in predicting actions in the first stage of poker hand. Study is focused exclusively on actions taken in pre-flop stage because of tight limits on the scope and time available for project completion; availability of data – all hands start at this stage, therefore information loss is minimized; the importance of hole and community cards increases with every successive stage, players’ actions are analyzed in the absence of this information, therefore, stage where omitted variable is least important, is more appropriate.

Project workflow:

1. Data gathering and preparation. ( http://poker.cs.ualberta.ca/irc_poker_database.html; Python)
2. Data explored via correlation heatmaps, and frequency histograms.
3. Deceptiveness modeled,  callibrated and evaluated. (Random forrest, grid-search, feature contributions)
4. Aggresiveness/submissiveness/passiveness modelled, calibrated and evaluated. (Random forrest, grid-search, feature contributions)
5. Analysis of results report writing.

Conclusion

The one, who is skilled at deceiving, as well as the one who is sharp in detecting deception possess a significant advantage in poker. It looked like we managed to detect deception, with high accuracy using only proportional bankroll. However, full model spread the importance to 6 variables evenly. Three of them - lagged deceptiveness; lagged passiveness and relative position also showed high positive contributions. Players, who played deceptively recently, are more likely to do it again. Prolonged passiveness shows up as a sign of a deceptive player and requires careful evaluation. Later position (POS_to_N) is associated with deceptive action pre-flop, which is different from what correlation matrices suggested. Relative bankroll-size still shows importance, however aggregated contributions are small. It means that positive and negative contributions cancel each other out and relationship is complex non-monotonic.

Aggressive play is the one that earns you the money. Successfully predicting it without knowing the hand strength is bluff catching skill. Predicting it using only ‘’environment’’ variables seem of little use. However, full model gives some hope. Opponent actions, specifically passiveness and submissiveness score highest in importance measure. Opponents’ submissiveness is also one of the most contributed variables (positively). Player experience (HANDS_PLAYED) express strong monotonic relationship, even though does not appear in importance graph. Seems, like aggressiveness tends to increase with experience, and is mostly affected by actions of the most recent opponent.

Passiveness rather than submissiveness, is generally a sign of a weak poker player. Passive play gives more flexibility to your opponents, and ability to spot the high likelihood of passive play is of great use in poker. All four variables that showed high importance, also contributed the most. namely BANKROLL_prop; HANDS_PLAYED; HAND_ID and OUTCOME_lag10_sum. Fact that relative bankroll is strong positive predictor for deceptiveness as well as passiveness, points to interesting, and dangerous interaction. Therefore, features should always be considered in combinations. Greater experience, table familiarity and recent success adds more weight on the likelihood of a passive action.

Folding, or giving up a hand at the right time is one of the hardest skills to learn and can define long term winner from looser. If one could spot potential for submissive pre-flop action, one could profit steadily via pressuring. Expectation was to spot strong negative relationship, with opponent aggressiveness, surprisingly PRFLOP_agro_o appeared only in importance measure. Table familiarity (HAND_ID) as well as sum of recent winnings (OUTCOME_lag10_sum) shows most robust, positive effect. (positive) Similarity of variables and signs in predicting passiveness and submissiveness leads to challenges in deducing reliable distinctions between these actions.

