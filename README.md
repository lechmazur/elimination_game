# Elimination Game Benchmark: Social Reasoning, Strategy, and Deception in Multi-Agent LLM Dynamics

The **Elimination Game** is a multi-player tournament that tests LLMs in social reasoning, strategy, and deception. Players engage in public and private conversations, form alliances, and vote to eliminate each other round by round until only two remain. A jury of eliminated players then casts deciding votes to crown the winner. This benchmark goes beyond simple dialogues by creating a rich environment where models must navigate:

- **Public vs. Private Dynamics**: Balancing open discussions with secretive alliances where hidden agendas can shift outcomes.
- **Strategic Voting**: Each round, players anonymously vote to eliminate a peer, with tie-breaks adding tension and complexity.
- **Jury Persuasion**: Finalists must convince the jury, testing rhetorical skill under pressure.

By analyzing conversation logs, voting patterns, and final ranks, we uncover how language models manage **shared knowledge** versus **hidden intentions**, forging alliances or **backstabbing** at opportune moments.

---

## Animation

*(Placeholder: Insert video or GIF showing game progression—public chats, secret alliances, votes, and eliminations.)*

We provide a round-by-round replay visualizing:
- **Public Chat**: Each active seat’s statement in the single public subround.  
- **Private Chats**: Hidden from others, showing alliances forming or unraveling.  
- **Voting**: Who voted to eliminate whom, including tie-break subphases with short statements.  
- **Jury Decision**: The final two’s pleas and the jury’s decisive votes.

---

## Visualizations & Metrics

### **TrueSkill Leaderboard (\(\mu \pm \sigma\))**  
A horizontal bar chart for each model’s skill rating, sorted top to bottom by \(\mu\). Reflects overall consistency in outlasting or winning.

![scoreboard_trueskill](./scoreboard_trueskill.png)

### **Rank Distribution by Model**  
A grouped bar chart showing how often each model places 1st–8th. Identifies those who frequently **win** or get eliminated early.

![rank_distribution_by_model](./rank_distribution_by_model.png)

### **Buddy Betrayal Rate by Model (Betrayer Perspective)**
A bar chart showing how frequently each model betrays any private chat partner. Higher bars indicate a greater tendency to double-cross.
![Buddy Betrayal Rate (Betrayer) Placeholder]


### **Buddy Betrayal Rate by Victim (Betrayed Perspective)**
A bar chart from the receiving end: which models are most often betrayed after a private chat.
![Buddy Betrayal Rate (Victim) Placeholder]

### **Final 2 → Win Rate**  
A chart of how frequently each model wins after making it to the final 2. Showcases rhetorical prowess in swaying the **jury** (eliminated players) or surviving final tie-breaks.

![final2_aggregated](./final2_aggregated.png)

### **Model Wordiness**  
A horizontal bar chart ranking each model by average words per message—spotlighting loquacious or succinct communicators.

![conversation_stats_average_words_per_message](./conversation_stats_average_words_per_message.png)

---

## Method Summary

### **Players & Setup**  
- **8 LLMs** per game, each seat labeled `P1` … `P8`.  
- Models can see the game’s **public** history and their own private chat logs.

### **Round Structure**  
1. **Public Subround (up to 80 words)**: Everyone speaks openly once.  
2. **Preference Ranking**: Each seat ranks others for private pairing.  
3. **Three Private Subrounds (up to 70, 50, 30 words)**: Form pairs, exchange messages, possibly forging alliances.  
4. **Voting**: Each seat secretly votes to eliminate someone. Ties trigger tie-break statements and re-votes.
5. **Elimination**: The seat with the most votes is out.

This continues until **2 remain**.

### **Final Scenario**  
- The last two seats give final statements.  
- The **jury** (all eliminated) votes to eliminate one. The sole survivor is the **winner**.

### **Scoring & TrueSkill**  
- **TrueSkill** updates ratings based on ranks, aggregated over multiple random passes.

---

## Elimination Game Leaderboard

*(Placeholder for actual final scoreboard after ~1000 tournaments, multi-pass rating. Example:)*


---

## Sample Entertaining Emergent Text

Below are real lines from elimination logs showing alliances:


---

## About TrueSkill

We use Microsoft’s [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) to measure skill in **multi-player** scenarios. After each game, partial points by rank feed into the TrueSkill environment. Multiple random “passes” through all game logs help remove order bias, yielding final \(\mu \pm \sigma\). Defaults:

- `mu = 5.0`, `sigma = 8.3333`, `beta = 4.1667`, `tau = 0.0`, `draw_probability = 0.0`

---

## Updates

- *(Placeholder: Insert new updates or model additions here.)*  
- *Follow [@lechmazur](https://x.com/lechmazur) for news, or see related benchmarks (Multi-Agent Step Race, LLM Confabulations, etc.).*

---

