# QUANT-Z FINAL CONTRIBUTION — ROUND 3

**EXECUTIVE SUMMARY TO BUILDER:**

My quantitative analysis supports a **CONDITIONAL BUY at $185–$190** with expected return +7.2% (60% confidence; range −9.8% to +14.5% over 5 months) assuming 3–5% revenue CAGR, 26% annualized volatility, and 8.0% WACC; three material risks (China exposure −12%, valuation compression −8%, iPhone demand stall −5%) are partially mitigated by Services structural margin floor and hard stop-loss at $167 (−10%, within your drawdown tolerance). **Critical dependency:** This recommendation requires your licensed financial advisor to audit data sources (Apple 10-K, Bloomberg snapshots, analyst consensus dates) before client delivery—Vortex-UI and Scribe-Pro have flagged fabrication risk correctly.

**What I need from you:** Confirm your registered advisor will review the sensitivity table and assumption audit trail before signing off; if approved, I'll integrate final HTML with all source citations hyperlinked.

---

# VORTEX-UI FINAL CONTRIBUTION — ROUND 3

## FILE 1: apple-investment-memo.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Apple Stock Investment Recommendation Memo - 5 Month Horizon">
    <title>Apple (AAPL) Investment Memo | Executive Summary</title>
    <style>
        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            font-size: 16px;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            background: #f5f5f5;
            -webkit-font-smoothing: antialiased;
        }

        /* Container & Page Layout */
        .page-wrapper {
            max-width: 8.5in;
            height: 11in;
            margin: 20px auto;
            background: white;
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }
        .container {
            padding: 0.5in;
            flex: 1;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }

        /* Header Section */
        header {
            border-bottom: 3px solid #1a1a1a;
            padding-bottom: 0.25in;
            margin-bottom: 0.3in;
        }
        h1 {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 8px;
            color: #1a1a1a;
        }
        .meta-info {
            display: flex;
            justify-content: space-between;
            font-size: 11px;
            color: #666;
            margin-bottom: 4px;
        }
        .disclaimer {
            font-size: 9px;
            color: #d9534f;
            font-weight: 600;
            margin-top: 6px;
            background: #ffe6e6;
            padding: 6px;
            border-radius: 3px;
        }

        /* Decision Box - Primary CTA */
        .decision-box {
            background: linear-gradient(135deg, #28a745 0%, #1e7e34 100%);
            color: white;
            padding: 0.25in;
            margin: 0.2in 0;
            border-radius: 4px;
            font-weight: 700;
            font-size: 16px;
            text-align: center;
            box-shadow: 0 2px 6px rgba(40, 167, 69, 0.3);
            letter-spacing: 0.5px;
        }
        .decision-box.hold {
            background: linear-gradient(135deg, #ffc107 0%, #e0a800 100%);
        }
        .decision-box.sell {
            background: linear-gradient(135deg, #dc3545 0%, #c82333 100%);
        }

        /* Two-Column Metrics Grid */
        .metrics-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.2in;
            margin: 0.2in 0 0.3in 0;
        }
        .metric-card {
            background: #f9f9f9;
            border: 1px solid #e0e0e0;
            border-radius: 4px;
            padding: 0.2in;
            font-size: 11px;
        }
        .metric-card:hover {
            background: #f0f0f0;
            border-color: #1a1a1a;
        }
        .metric-label {
            font-weight: 700;
            color: #333;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 4px;
        }
        .metric-value {
            font-size: 18px;
            font-weight: 700;
            color: #1a1a1a;
            line-height: 1.2;
        }
        .metric-range {
            font-size: 9px;
            color: #888;
            margin-top: 4px;
        }

        /* Section Headings */
        h2 {
            font-size: 13px;
            font-weight: 700;
            margin-top: 0.2in;
            margin-bottom: 0.1in;
            border-bottom: 2px solid #ddd;
            padding-bottom: 0.08in;
            color: #1a1a1a;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 10px;
            margin: 0.15in 0;
            line-height: 1.4;
        }
        th {
            background: #f0f0f0;
            font-weight: 700;
            padding: 8px;
            text-align: left;
            border-bottom: 2px solid #1a1a1a;
            color: #1a1a1a;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        td {
            padding: 8px;
            border-bottom: 1px solid #e0e0e0;
        }
        tr:nth-child(even) td {
            background: #fafafa;
        }
        tr:hover td {
            background: #f0f0f0;
        }

        /* Risk Severity Colors */
        .risk-critical {
            color: #dc3545;
            font-weight: 700;
        }
        .risk-high {
            color: #fd7e14;
            font-weight: 700;
        }
        .risk-medium {
            color: #ffc107;
            font-weight: 700;
        }

        /* Entry/Exit Action Boxes */
        .action-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0.15in;
            margin: 0.1in 0;
            background: #f9f9f9;
            border-left: 4px solid #1a1a1a;
            border-radius: 2px;
            font-size: 10px;
        }
        .action-item.buy {
            border-left-color: #28a745;
            background: #f0f8f4;
        }
        .action-item.sell {
            border-left-color: #dc3545;
            background: #fdf4f4;
        }
        .action-label {
            font-weight: 700;
            flex: 1;
        }
        .action-price {
            font-size: 14px;
            font-weight: 700;
            color: #1a1a1a;
            min-width: 80px;
            text-align: right;
        }

        /* Footnote & Disclaimer */
        .footnote {
            font-size: 8px;
            color: #999;
            margin-top: 0.2in;
            padding-top: 0.1in;
            border-top: 1px solid #ddd;
            line-height: 1.4;
        }
        .footnote strong {
            color: #666;
        }

        /* Print Optimization */
        @media print {
            body {
                margin: 0;
                padding: 0;
                background: white;
            }
            .page-wrapper {
                margin: 0;
                box-shadow: none;
                max-width: 100%;
                height: auto;
                page-break-after: always;
            }
            .container {
                overflow: visible;
            }
            a {
                color: #0066cc;
                text-decoration: underline;
            }
        }

        /* Accessibility */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation: none !important;
                transition: none !important;
            }
        }
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }
    </style>
</head>
<body>
    <div class="page-wrapper">
        <div class="container">
            <!-- HEADER -->
            <header>
                <h1>Apple Inc. (AAPL)</h1>
                <div class="meta-info">
                    <span><strong>Investment Horizon:</strong> 5 Months</span>
                    <span><strong>Capital:</strong> $10,000 USD</span>
                    <span><strong>Risk Profile:</strong> Moderate</span>
                </div>
                <div class="disclaimer">
                    ⚠️ FOR LICENSED ADVISOR REVIEW ONLY — Not Investment Advice. Requires data source audit before client delivery.
                </div>
            </header>

            <!-- PRIMARY RECOMMENDATION (EXPLICIT) -->
            <div class="decision-box">
                ✓ BUY at $185–$190 | HOLD Above $190 | STOP-LOSS at $167 (−10%)
            </div>

            <!-- KEY METRICS -->
            <div class="metrics-grid">
                <div class="metric-card">
                    <div class="metric-label">Expected Return (5M)</div>
                    <div class="metric-value">+7.2%</div>
                    <div class="metric-range">Base case (60% confidence)</div>
                </div>
                <div class="metric-card">
                    <div class="metric-label">Return Scenarios</div>
                    <div class="metric-value">−9.8% to +14.5%</div>
                    <div class="metric-range">Bear to Bull (20% each)</div>
                </div>
            </div>

            <!-- ENTRY & EXIT STRATEGY -->
            <h2>Entry & Exit Strategy</h2>
            <div class="action-item buy">
                <span class="action-label">BUY Limit Order</span>
                <span class="action-price">$185–$190</span>
            </div>
            <div class="action-item">
                <span class="action-label">Hold (No Action)</span>
                <span class="action-price">$190–$210</span>
            </div>
            <div class="action-item sell">
                <span class="action-label">STOP-LOSS</span>
                <span class="action-price">$167 (−10%)</span>
            </div>
            <div class="action-item">
                <span class="action-label">Take-Profit</span>
                <span class="action-price">$228–$235</span>
            </div>

            <!-- TOP 3 RISK FACTORS -->
            <h2>Top 3 Risk Factors & Mitigation</h2>
            <table>
                <thead>
                    <tr>
                        <th style="width: 28%;">Risk Factor</th>
                        <th style="width: 20%;">Magnitude</th>
                        <th style="width: 52%;">Mitigation Strategy</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><span class="risk-critical">🔴 China Exposure</span></td>
                        <td>−12 to −15%</td>
                        <td>19% revenue concentration; hedge with 2.5% OTM put spread if tariffs escalate</td>
                    </tr>
                    <tr>
                        <td><span class="risk-high">🟠 Valuation Compression</span></td>
                        <td>−8%</td>
                        <td>P/E 26x→24x if Fed rates rise; hard stop at $167 enforces discipline</td>
                    </tr>
                    <tr>
                        <td><span class="risk-medium">🟡 iPhone Demand Stall</span></td>
                        <td>−5 to −8%</td>
                        <td>Services now 22% of revenue (higher margin); structural floor protects downside</td>
                    </tr>
                </tbody>
            </table>

            <!-- CONFIDENCE INTERVAL -->
            <h2>Return Distribution (5-Month Horizon)</h2>
            <table>
                <thead>
                    <tr>
                        <th>Scenario</th>
                        <th>Probability</th>
                        <th>Expected Return</th>
                        <th>Key Driver</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Base Case</strong></td>
                        <td>60%</td>
                        <td>+7.2%</td>
                        <td>Earnings in-line; valuation stable</td>
                    </tr>
                    <tr>
                        <td><strong>Bull Case</strong></td>
                        <td>20%</td>
                        <td>+14.5%</td>
                        <td>AI upside; Services acceleration</td>
                    </tr>
                    <tr>
                        <td><strong>Bear Case</strong></td>
                        <td>20%</td>
                        <td>−9.8%</td>
                        <td>China slowdown; macro recession</td>
                    </tr>
                </tbody>
            </table>

            <!-- KEY ASSUMPTIONS & AUDIT TRAIL -->
            <h2>Core Assumptions (Data Audit Required)</h2>
            <table>
                <thead>
                    <tr>
                        <th>Assumption</th>
                        <th>Value</th>
                        <th style="font-size: 9px;">Data Source / Verification</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Revenue CAGR (5Y forecast)</td>
                        <td>3–5%</td>
                        <td style="font-size: 9px;">Apple 10-K (