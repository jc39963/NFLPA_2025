# NFLPA Case Competition 2025 

### Jenny Chen and Rishika Randev

🏈 Predicting Injury & Re-Injury Risk in the NFL

This project analyzes how cumulative workload, recovery time, and player characteristics relate to injury and reinjury risk in the NFL. Using injury reports, snap count data, schedule information, and roster details across multiple seasons, we build explainable machine-learning models to better understand:

* Which factors most strongly predict injury risk

* How risk changes after returning from injury

* How patterns differ across positions and workloads

* What insights may inform NFLPA policy advocacy

Our work is motivated by the NFL Collective Bargaining Agreement (CBA), which shapes practice limits, roster structure, rest periods, and incentives — all of which influence player health. 

----

🧹 **Data & Feature Engineering**

We integrate multiple datasets using nflverse:

* Player Stats (weekly snap counts)

* Injury reports (status + type)

* Schedule & game dates

* Player metadata (age, position, team)

Key engineered features include:

*  `snap_count`

* `days_since_last_game`

* `weeks_since_return` - (if previously injured)

* `most_recent_injury` - (injury type)
* `position` 
* `game_surface`  

We also construct binary outcomes:
* Injury risk → injured the following week

* Re-injury risk → injured again after prior injury
----
🤖 Modeling

We used multiple approaches and techniques:

* XGBoost (baseline)

* GPBoost (tree boosting + random effects by player)

* Cross-season rolling validation

* SHAP explainability for model interpretation

We included mixed-effects modeling to account for:

* player-specific variability (random effects by player) allowing us to separate player tendencies from structural workload effects.

-----
🔍 Key Insights (High-Level)

* Higher snap counts correlate with lower observed injury risk — likely because healthier players are chosen to play more.

* Re-injury risk spikes immediately after return.

* Position group meaningfully influences risk.

* Increased rest days often reflect injuries themselves, not rest causing injuries.

* We pair findings with CBA policy implications around workload, return-to-play ramp-ups, roster flexibility, and incentive structures.

----
🏛 Policy & NFLPA Relevance

* Our insights are interpreted through:

* Practice/contact limits

* Bye-week rules

* Roster activation flexibilities

* Performance-based pay

* Return-to-play procedures

We highlight how current rules may unintentionally increase risk — and propose data-driven adjustments.

----
⚠️ Limitations

* “Re-injury” is defined broadly in our analysis (not necessarily same body part)

* Some injuries go unreported

* Not causal inference

* Missingness & team reporting variation

Future work: incorporate snap share, diff-in-diff, surface effects, and more granular injury taxonomy.