# t20-world-cup-sql-analysis
SQL-based analysis of T20 World Cup data to uncover match trends, team performance, toss impact, venue influence, and qualification insights.
##  Project Overview
This project analyzes T20 World Cup 2026 data using SQL and Power BI to uncover match trends, tournament strategies, team consistency, venue impact, and qualification patterns.

The project focuses on transforming raw cricket match data into meaningful insights through SQL queries, aggregations, joins, and analytical reporting.

---

#  Objectives
- Analyze team performances throughout the tournament
- Study the impact of toss decisions on match outcomes
- Evaluate batting-first vs chasing success rates
- Identify venue-wise performance trends
- Examine knockout-stage performance under pressure
- Analyze qualification patterns using points and Net Run Rate (NRR)

---

#  Tools & Technologies
- SQL (MySQL)
- Power BI
- Kaggle Dataset
- GitHub

---

# Dataset Information

The dataset contains:
- Match details
- Venue information
- Tournament points table

### Main Tables
| Table Name | Description |
|---|---|
| `matches` | Match-level tournament data |
| `venues` | Stadium and venue details |
| `points_table` | Team standings and qualification data |

---

#  Data Cleaning Performed
- Imported CSV datasets into SQL tables
- Cleaned and structured tournament data
- Converted Net Run Rate values for numerical analysis
- Organized relationships between tables using JOIN operations

---

#  Key Analysis Performed

##  Team Performance Analysis
- Evaluated total wins and tournament consistency
- Compared match wins with overall points table standings

## Toss Impact Analysis
- Analyzed whether toss-winning teams gained strategic advantage
- Compared batting-first and chasing success rates

##  Team Consistency Analysis
- Studied win-loss ratios and qualification trends
- Identified teams with the most stable tournament performance

##  Knockout Match Analysis
- Evaluated performance in Semi-finals and Finals
- Measured pressure-handling capability of teams

##  Venue Performance Analysis
- Studied venue-wise winning trends
- Analyzed how stadium conditions influenced match outcomes

##  Qualification Analysis
- Examined qualification thresholds
- Investigated the role of Net Run Rate (NRR) in tournament progression

---

#  Key Insights

- Teams batting first showed higher winning percentages in multiple matches.
- Consistent performance across matches contributed more to qualification than isolated victories.
- Venue conditions influenced team strategies and overall outcomes.
- Knockout-stage performance highlighted the importance of pressure handling.
- Net Run Rate played a critical role when teams had equal points.

---

#  Example SQL Queries

## Toss Impact Analysis
```sql
SELECT 
    toss_decision,
    COUNT(*) AS total_matches,
    SUM(CASE 
        WHEN toss_winner = winner THEN 1
        ELSE 0
    END) AS successful_decisions
FROM matches
GROUP BY toss_decision;
```

---

## Team Consistency Analysis
```sql
SELECT 
    team,
    won,
    lost,
    no_result,
    points
FROM points_table
ORDER BY won DESC, lost ASC;
```

---

## Knockout Match Performance
```sql
SELECT 
    stage,
    winner,
    COUNT(*) AS wins
FROM matches
GROUP BY stage, winner
ORDER BY stage, wins DESC;
```

---

#  Dashboard Features
- Toss Analysis Dashboard
- Team Performance Dashboard
- Venue Analysis Dashboard
- Qualification Analysis Dashboard
- Knockout Stage Performance Dashboard
---

#  Skills Demonstrated
- SQL Joins
- Aggregations
- GROUP BY & HAVING
- CASE Statements
- Data Cleaning
- Tournament Data Analysis
- Dashboard Development
- Analytical Thinking

---

# Future Improvements
- Add player-level performance analysis
- Include ball-by-ball match analysis
- Build predictive models using Python
- Create interactive filtering dashboards

---

#  Learning Outcomes
This project improved understanding of:
- Real-world SQL analysis workflows
- Sports analytics techniques
- Data-driven decision making
- SQL-based reporting and dashboard creation

---

#  Conclusion
This project demonstrates how SQL and data analytics can be used to transform raw cricket tournament data into strategic insights regarding team performance, match outcomes, consistency, and qualification patterns.
