# IPL 2008–2020 Analysis Dashboard (Tableau)

An interactive Tableau dashboard that analyses 13 seasons of the Indian Premier League (IPL) using match-level and ball-by-ball data. It covers season winners, Orange Cap and Purple Cap holders, boundary counts, and how the toss decision relates to winning.

**Tools:** Excel / CSV (data sources) · Tableau Public / Desktop (data model, calculated fields, worksheets, dashboard)

---

## 1. Project Objective

Turn raw cricket data into an easy-to-explore dashboard that answers:

1. Who won each IPL season, and which teams win the most matches?
2. Who are the Orange Cap (top run-scorer) and Purple Cap (top wicket-taker) holders?
3. How many fours and sixes were hit across the tournament?
4. Does winning the toss, and the decision taken (bat or field), improve the chances of winning the match?

---

## 2. Datasets

| File | Content | Size |
|---|---|---|
| `IPL_Matches_2008-2020.xlsx` | One row per match: city, date, venue, teams, toss winner and decision, winner, result and margin, player of the match, umpires | 816 matches × 17 columns |
| `IPL_Ball-by-Ball_2008-2020.xlsx` | One row per delivery: batsman, bowler, runs, extras, wicket, dismissal type, batting and bowling team | 193,468 deliveries × 18 columns |

The two files are linked by the match **id**.

**Data notes:** City is blank for a few matches; winner and player of the match are blank for 4 matches (no result). Dismissal, fielder and extras columns are blank unless the event happened. Date values are stored in mixed formats, so check the date field's type before doing season-level work.

---

## 3. Project Steps

### Step 1 – Collect and understand the data
Reviewed both datasets and their columns, and noted that the match id connects them.

### Step 2 – Connect the data in Tableau
Loaded both files into Tableau (the workbook references `IPL Matches 2008-2020.csv` and `IPL Ball-by-Ball 2008-2020.csv`) and joined them on match id so that match details (season, toss, winner) can be used with delivery-level data (runs, wickets).

### Step 3 – Prepare fields
Checked data types, handled blanks, and created calculated fields such as **Max Date** to support the season selector.

### Step 4 – Build the worksheets
| Worksheet | Purpose |
|---|---|
| Select Season | Season filter that drives the dashboard |
| Title Winner | Winner of the selected season |
| Team Image | Winning team's logo |
| Orange Cap | Top run-scorer(s) |
| Orange Cap Image | Orange Cap holder's image |
| Purple Cap | Top wicket-taker(s) |
| Purple Cap Image | Purple Cap holder's image |
| Tournament 4's | Total fours hit |
| Tournament 6's | Total sixes hit |
| Match Win Based on Toss Decision | Matches won when batting first vs fielding first |
| Toss Decision Based Winning % | Win percentage by toss decision |

### Step 5 – Design the dashboard
Combined the worksheets into **Dashboard 1**: season selector and title winner at the top, cap holders with images beside them, tournament totals of fours and sixes, and the toss-decision analysis below.

### Step 6 – Interpret and share
Drew the insights below and saved the workbook as `IPL_Match_data.twbx` so it opens with its data.

---

## 4. Key Insights

*(Computed from the two datasets across 2008–2020.)*

- **Most successful team:** Mumbai Indians have the most match wins (120), followed by Chennai Super Kings (106), Kolkata Knight Riders (99), Royal Challengers Bangalore (91) and Kings XI Punjab (88).
- **Top run-scorers (all seasons):** Virat Kohli (5,878), Suresh Raina (5,368), David Warner (5,254), Rohit Sharma (5,230) and Shikhar Dhawan (5,197).
- **Top wicket-takers (all seasons, excluding run-outs):** Lasith Malinga (170), Amit Mishra (160), Piyush Chawla (156), Dwayne Bravo (153) and Harbhajan Singh (150).
- **Boundaries:** about 21,900 fours and 8,900 sixes were hit across the tournament.
- **Toss:** winning the toss gives only a slight edge: toss winners won about 51.5% of matches.
- **Toss decision:** captains chose to field first about 61% of the time, and those who did won about 55% of their matches, compared with about 45% for those who chose to bat first.
- **Player of the Match:** AB de Villiers (23 awards) and Chris Gayle (22) lead.

---

## 5. Takeaways

1. Chasing has been the more successful strategy in IPL history, which is why most captains choose to field first.
2. The toss alone is not decisive; team strength matters more.
3. A season selector makes the same dashboard reusable for any season or the entire tournament.

---

## 6. How to Open

1. Download `IPL_Match_data.twbx` and open it in Tableau Public or Tableau Desktop.
2. Open **Dashboard 1**, choose a season in the selector, and the title winner, caps and charts update.

## 7. Repository Structure

```
├── IPL_Match_data.twbx                # Tableau workbook + dashboard
├── IPL_Matches_2008-2020.xlsx         # Match-level data
├── IPL_Ball-by-Ball_2008-2020.xlsx    # Delivery-level data
└── README.md
```

## 8. Skills Demonstrated

Tableau data joins · Calculated fields · Interactive filters · Dashboard design · Sports analytics · Data storytelling

---

**Author:** Astha Kumari Jha
**GitHub:** [github.com/Asthajha4275](https://github.com/Asthajha4275)
