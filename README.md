# 🚀 Breakout + Trendlyne Combined Analysis System

This system combines **ChartInk breakout signals** with **Trendlyne fundamental analysis** to provide comprehensive stock analysis that considers both technical breakouts and fundamental strength.

## 📊 What It Does

### Combines Two Powerful Analysis Systems:
1. **ChartInk Breakout Scanner** - Technical analysis with 6 conditions
2. **Trendlyne Analysis** - Fundamental + Technical scoring (65% Technical + 35% Fundamental)

### Creates a Unified View:
- Shows only stocks that have **both** breakout signals AND Trendlyne analysis data
- Sorts by composite score to prioritize the best opportunities
- Provides interactive HTML report with comprehensive data

## 🔄 How It Works

```
Breakout Scanner → CSV Results → Combined Analyzer ← Trendlyne HTML
                                      ↓
                              Combined HTML Report
                          (Breakout + Financial Data)
```

## 📋 Prerequisites

1. **Breakout Scanner Results**
   - Run `breakout_scanner.py` first to generate `breakout_signals_*.csv`

2. **Trendlyne Analysis Data**
   - Run Trendlyne analysis to generate `complete_enhanced_report_all_stocks.html`

## 🚀 How to Run

### Step 1: Generate Breakout Signals
```bash
cd zerodha
python breakout_scanner.py
```
This creates: `breakout_signals_YYYYMMDD_HHMMSS.csv`

### Step 2: Run Combined Analysis
```bash
python BreakoutTrendlyne/breakout_trendlyne_analyzer.py
```

### Step 3: View Results
Open the generated HTML report:
```
zerodha/BreakoutTrendlyne/combined_breakout_trendlyne_report.html
```

## 📊 Report Features

### 🎯 Summary Dashboard
- Total companies with breakout signals
- Average composite, QSS, and fundamental scores
- Signal distribution (BUY/HOLD/SELL)

### 📈 Interactive Table
- **Sortable columns** - Click headers to sort
- **Search functionality** - Search by company name, NSE code, industry
- **Filtering** - Filter by minimum composite score
- **Pagination** - Choose items per page or show all
- **Export** - Download results as CSV

### 📋 Data Columns
- **Company Name & NSE Code**
- **Composite Score** - Overall Trendlyne rating
- **QSS Score** - Technical analysis score
- **Fundamental Score** - Financial strength rating
- **Trade Signal** - BUY/HOLD/SELL recommendation
- **Current Price**
- **Market Cap**
- **PE Ratio**
- **Revenue Growth**
- **Promoter Holding**
- **Breakout Badge** - Indicates ChartInk breakout signal

## 🎨 Visual Features

### Color-Coded Scores
- 🟢 **Green (80-100)** - Excellent
- 🟡 **Yellow-Green (60-79)** - Good
- 🟠 **Orange (40-59)** - Average
- 🔴 **Red (20-39)** - Poor
- ⚫ **Dark Red (0-19)** - Bad

### Signal Badges
- 🟢 **BUY** - Strong buy signal
- 🟡 **HOLD** - Hold recommendation
- 🔴 **SELL** - Sell recommendation

## 📁 File Structure

```
zerodha/BreakoutTrendlyne/
├── breakout_trendlyne_analyzer.py    # Main analyzer script
├── README.md                         # This file
└── combined_breakout_trendlyne_report.html  # Generated report
```

## 🔍 What the System Looks For

### Required Files (Auto-detected):
1. **Breakout Results**: `breakout_signals_*.csv` (latest file)
2. **Trendlyne Data**: `zerodha/Trendlyne/complete_enhanced_report_all_stocks.html`

### Data Matching:
- Matches companies by NSE code/symbol
- Only includes companies present in **both** datasets
- Ensures you get stocks with **both** technical breakouts **and** fundamental analysis

## 📊 Sample Output

```
🏆 TOP 10 COMPANIES WITH BREAKOUT SIGNALS:
----------------------------------------------------------------------------------------------------
#   Company                  NSE        Comp   QSS    Fund   Signal     Price   
----------------------------------------------------------------------------------------------------
1   RELIANCE                 RELIANCE   85.2   78.5   95.1   BUY        ₹2847.50
2   HDFCBANK                 HDFCBANK   82.1   75.3   92.4   BUY        ₹1654.20
3   JINDALSTEL               JINDALSTEL 79.8   82.1   75.2   BUY        ₹945.80
```

## 🎯 Benefits

### Why Combine Both Systems?
1. **Technical + Fundamental** - Get the complete picture
2. **Quality Filter** - Only stocks with breakout potential AND strong fundamentals
3. **Risk Mitigation** - Avoid breakouts in fundamentally weak companies
4. **Opportunity Identification** - Find the best of both worlds

### Perfect For:
- **Swing Trading** - Medium-term positions (weeks to months)
- **Investment Planning** - Long-term wealth building
- **Risk Management** - Avoid weak fundamental stocks
- **Portfolio Screening** - Pre-filter quality opportunities

## 🚨 Important Notes

1. **Dependencies**: Requires both breakout scanner and Trendlyne analysis to be run first
2. **Data Freshness**: Results are only as current as your input data
3. **Market Conditions**: Always consider overall market conditions
4. **Risk Management**: Use proper position sizing and stop-losses

## 🔧 Troubleshooting

### Common Issues:

**"No breakout signals CSV file found"**
- Run `breakout_scanner.py` first
- Check that CSV was generated successfully

**"Trendlyne HTML file not found"**
- Ensure `zerodha/Trendlyne/complete_enhanced_report_all_stocks.html` exists
- Run Trendlyne analysis first

**"No merged data"**
- Check that symbol names match between datasets
- Ensure both datasets contain overlapping companies

## 🎉 Success Indicators

When working correctly, you should see:
```
✅ Loaded X breakout signals from breakout_signals_*.csv
✅ Extracted Y companies from Trendlyne analysis
✅ Successfully merged Z companies with both breakout signals and Trendlyne data
✅ Combined HTML report generated: combined_breakout_trendlyne_report.html
```

---

**Happy Trading! 🚀📈** 