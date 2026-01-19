# Guide d'Utilisation API - Agents UX Programmatiques

**Version** : 1.0
**Dernière mise à jour** : 2026-01-18

---

## 📋 Table des Matières

1. [Introduction](#introduction)
2. [Setup Claude API](#setup-claude-api)
3. [Agent Invocation](#agent-invocation)
4. [Automation Scripts](#automation-scripts)
5. [Best Practices](#best-practices)

---

## Introduction

### Pourquoi Utiliser les Agents via API ?

**Use cases automation :**
- ✅ **Audits périodiques automatisés** (weekly Nielsen scans)
- ✅ **Batch processing** (audit 50 screenshots en une fois)
- ✅ **CI/CD integration** (accessibility check avant deploy)
- ✅ **Monitoring continu** (analytics interpretation daily)
- ✅ **Workflows orchestrés** (multi-agents sans intervention manuelle)

**Avantages :**
- Scalabilité (traiter volumes importants)
- Consistency (mêmes critères appliqués)
- Rapidité (pas de copier-coller manuel)
- Integration (pipelines existants)

---

## Setup Claude API

### 1. Obtenir API Key

```bash
# S'inscrire sur console.anthropic.com
# Créer API key dans Settings > API Keys
# Stocker de manière sécurisée (environment variables)

export ANTHROPIC_API_KEY="sk-ant-api03-..."
```

### 2. Installer SDK

**Python :**
```bash
pip install anthropic
```

**TypeScript/JavaScript :**
```bash
npm install @anthropic-ai/sdk
```

### 3. Rate Limits & Pricing

**Rate Limits (Tier 1) :**
- 50 requests/minute
- 40,000 tokens/minute (input)
- 4,000 tokens/minute (output)

**Pricing (Claude Sonnet 4.5) :**
- Input : $3/million tokens
- Output : $15/million tokens

**Cost Estimate Examples :**
- Nielsen Audit (1 page) : ~$0.20
- Full workflow (5 agents) : ~$1.00

---

## Agent Invocation

### Python Examples

#### Example 1 : Single Agent (Nielsen Audit)

```python
import anthropic
import os

# Initialize client
client = anthropic.Anthropic(
    api_key=os.environ.get("ANTHROPIC_API_KEY")
)

# Load agent prompt
with open("agents/analysis/ux-auditor-nielsen.md", "r") as f:
    agent_prompt = f.read()

# User's specific request
user_request = """
Context: SaaS B2B dashboard for data analysts

Please audit the attached interface screenshots.

Screens:
1. Dashboard (main view)
2. Advanced Filters panel
3. Report generation page

Users: Data analysts, daily usage
Critical tasks: Create reports, analyze trends, set up alerts

Format: Detailed report for design team
"""

# Invoke agent
message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=8000,
    messages=[
        {
            "role": "user",
            "content": f"{agent_prompt}\n\n---\n\n{user_request}"
        }
    ]
)

# Extract response
audit_report = message.content[0].text
print(audit_report)

# Save to file
with open("output/nielsen_audit_report.md", "w") as f:
    f.write(audit_report)
```

#### Example 2 : Agent with Images (Vision)

```python
import anthropic
import base64

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

# Load agent
with open("agents/analysis/ux-auditor-nielsen.md") as f:
    agent_prompt = f.read()

# Load screenshot
with open("screenshots/dashboard.png", "rb") as img_file:
    img_data = base64.b64encode(img_file.read()).decode("utf-8")

# Invoke with vision
message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=8000,
    messages=[
        {
            "role": "user",
            "content": [
                {
                    "type": "text",
                    "text": f"{agent_prompt}\n\nAudit this dashboard screenshot:"
                },
                {
                    "type": "image",
                    "source": {
                        "type": "base64",
                        "media_type": "image/png",
                        "data": img_data
                    }
                }
            ]
        }
    ]
)

print(message.content[0].text)
```

#### Example 3 : Multi-Agent Workflow

```python
import anthropic
import os

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def invoke_agent(agent_path, user_context):
    """Helper function to invoke any agent"""
    with open(agent_path) as f:
        agent_prompt = f.read()

    message = client.messages.create(
        model="claude-sonnet-4-5-20250929",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"{agent_prompt}\n\n---\n\n{user_context}"
        }]
    )

    return message.content[0].text

# Workflow: Analytics → Qualitative → Journey Mapping
print("Step 1: Analytics Interpreter...")
analytics_report = invoke_agent(
    "agents/data-intelligence/analytics-interpreter.md",
    """
    Analyze GA4 data:
    - 68% drop-off at "Advanced Filters"
    - Power users 20%, spend 45min avg
    - Casual users 60%, spend 8min avg

    Provide quantitative insights.
    """
)
print(analytics_report)

print("\nStep 2: Qualitative Feedback Analyzer...")
qualitative_report = invoke_agent(
    "agents/data-intelligence/qualitative-feedback-analyzer.md",
    f"""
    Context from analytics:
    {analytics_report}

    Analyze support tickets themes:
    - "Filters too complex"
    - "Can't find advanced features"
    - "Steep learning curve"

    Provide thematic analysis.
    """
)
print(qualitative_report)

print("\nStep 3: User Journey Mapper...")
journey_map = invoke_agent(
    "agents/deliverables/user-journey-mapper.md",
    f"""
    Context:
    - Analytics insights: {analytics_report[:500]}...
    - Qualitative insights: {qualitative_report[:500]}...

    Create user journey map for "Data Analyst using dashboard to create report".
    """
)
print(journey_map)

# Save final outputs
with open("output/workflow_results.md", "w") as f:
    f.write(f"# Multi-Agent Workflow Results\n\n")
    f.write(f"## Analytics\n{analytics_report}\n\n")
    f.write(f"## Qualitative\n{qualitative_report}\n\n")
    f.write(f"## Journey Map\n{journey_map}")
```

---

### TypeScript Examples

#### Example 1 : Single Agent

```typescript
import Anthropic from "@anthropic-ai/sdk";
import fs from "fs";

const client = new Anthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
});

async function invokeAgent(agentPath: string, userRequest: string) {
  // Load agent prompt
  const agentPrompt = fs.readFileSync(agentPath, "utf-8");

  // Invoke
  const message = await client.messages.create({
    model: "claude-sonnet-4-5-20250929",
    max_tokens: 8000,
    messages: [
      {
        role: "user",
        content: `${agentPrompt}\n\n---\n\n${userRequest}`,
      },
    ],
  });

  return message.content[0].text;
}

// Usage
const report = await invokeAgent(
  "agents/analysis/ux-auditor-nielsen.md",
  "Audit this SaaS dashboard for usability issues."
);

console.log(report);
fs.writeFileSync("output/audit_report.md", report);
```

#### Example 2 : Async Batch Processing

```typescript
import Anthropic from "@anthropic-ai/sdk";
import fs from "fs";

const client = new Anthropic({ apiKey: process.env.ANTHROPIC_API_KEY });

async function batchAudit(screenshots: string[]) {
  const agentPrompt = fs.readFileSync(
    "agents/analysis/ux-auditor-nielsen.md",
    "utf-8"
  );

  // Process all screenshots in parallel
  const auditPromises = screenshots.map(async (screenshot) => {
    const message = await client.messages.create({
      model: "claude-sonnet-4-5-20250929",
      max_tokens: 4000,
      messages: [
        {
          role: "user",
          content: `${agentPrompt}\n\nAudit screenshot: ${screenshot}`,
        },
      ],
    });

    return {
      screenshot,
      report: message.content[0].text,
    };
  });

  return await Promise.all(auditPromises);
}

// Usage
const screenshots = ["screen1.png", "screen2.png", "screen3.png"];
const results = await batchAudit(screenshots);

results.forEach((result) => {
  console.log(`\n=== ${result.screenshot} ===`);
  console.log(result.report);
});
```

---

## Automation Scripts

### Script 1 : Weekly Automated Audit

```python
#!/usr/bin/env python3
"""
Weekly automated Nielsen audit
Runs every Monday, audits production dashboard, sends report to team
"""

import anthropic
import os
from datetime import datetime
import smtplib
from email.mime.text import MIMEText

def run_weekly_audit():
    client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

    # Load agent
    with open("agents/analysis/ux-auditor-nielsen.md") as f:
        agent_prompt = f.read()

    # Audit production
    message = client.messages.create(
        model="claude-sonnet-4-5-20250929",
        max_tokens=6000,
        messages=[{
            "role": "user",
            "content": f"""{agent_prompt}

            Audit our production dashboard (screenshots attached).
            Focus: Any new usability regressions since last week.
            Format: Sprint Action Items (P0/P1 only)
            """
        }]
    )

    report = message.content[0].text

    # Save report
    today = datetime.now().strftime("%Y-%m-%d")
    filename = f"audits/weekly_audit_{today}.md"
    with open(filename, "w") as f:
        f.write(report)

    # Email team
    send_email(
        to="design-team@company.com",
        subject=f"Weekly UX Audit - {today}",
        body=report
    )

    print(f"✅ Weekly audit complete: {filename}")

def send_email(to, subject, body):
    # Email sending logic (SMTP)
    pass

if __name__ == "__main__":
    run_weekly_audit()
```

**Cron job (Linux/Mac) :**
```bash
# Run every Monday at 9 AM
0 9 * * 1 /usr/bin/python3 /path/to/weekly_audit.py
```

---

### Script 2 : CI/CD Accessibility Check

```yaml
# .github/workflows/accessibility-check.yml
name: Accessibility Check

on:
  pull_request:
    paths:
      - 'src/**/*.tsx'
      - 'src/**/*.css'

jobs:
  wcag-audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Build app
        run: npm run build

      - name: Screenshot key pages
        run: npm run screenshot:all

      - name: Run WCAG Audit via Claude API
        env:
          ANTHROPIC_API_KEY: ${{ secrets.ANTHROPIC_API_KEY }}
        run: |
          python scripts/wcag_audit.py --screenshots ./screenshots/*.png

      - name: Comment on PR
        uses: actions/github-script@v6
        with:
          script: |
            const fs = require('fs');
            const report = fs.readFileSync('output/wcag_report.md', 'utf8');
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: `## ♿ WCAG Audit Results\n\n${report}`
            });
```

**Script Python (`scripts/wcag_audit.py`) :**
```python
import anthropic
import os
import sys

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

with open("agents/deliverables/accessibility-wcag-checker.md") as f:
    agent_prompt = f.read()

# Audit screenshots
message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=4000,
    messages=[{
        "role": "user",
        "content": f"""{agent_prompt}

        Audit these screenshots for WCAG 2.1 AA compliance.
        Focus: Critical violations (P0) only.
        Format: PR comment (concise, actionable)
        """
    }]
)

# Save report
with open("output/wcag_report.md", "w") as f:
    f.write(message.content[0].text)

# Exit with error if P0 violations found
if "P0" in message.content[0].text:
    sys.exit(1)  # Fail CI
```

---

### Script 3 : Analytics Daily Digest

```python
#!/usr/bin/env python3
"""
Daily analytics digest
Runs every morning, interprets yesterday's GA4 data, sends insights
"""

import anthropic
import os
from datetime import datetime, timedelta
import requests

def fetch_ga4_data():
    """Fetch yesterday's GA4 metrics"""
    # Integration with GA4 API
    yesterday = (datetime.now() - timedelta(days=1)).strftime("%Y-%m-%d")

    # Mock data (replace with real GA4 API call)
    return f"""
    Date: {yesterday}
    Sessions: 1,245 (-5% vs day before)
    Bounce Rate: 42% (+3% vs day before)
    Avg Session Duration: 3:24 (-8% vs day before)
    Top Exit Page: /dashboard/filters (68% exits)
    """

def run_daily_digest():
    client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

    # Fetch data
    ga4_data = fetch_ga4_data()

    # Load agent
    with open("agents/data-intelligence/analytics-interpreter.md") as f:
        agent_prompt = f.read()

    # Interpret
    message = client.messages.create(
        model="claude-sonnet-4-5-20250929",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""{agent_prompt}

            Analyze yesterday's metrics:
            {ga4_data}

            Provide:
            1. Key insights (3 bullet points)
            2. Alerts (if metrics drop >10%)
            3. Recommended actions (if any)

            Format: Slack message (concise, emoji OK)
            """
        }]
    )

    digest = message.content[0].text

    # Post to Slack
    post_to_slack(digest)

    print(f"✅ Daily digest sent")

def post_to_slack(message):
    webhook_url = os.environ["SLACK_WEBHOOK_URL"]
    requests.post(webhook_url, json={"text": message})

if __name__ == "__main__":
    run_daily_digest()
```

---

## Best Practices

### 1. Prompt Engineering

**DO :**
```python
# ✅ Provide context
context = """
Product: SaaS B2B analytics dashboard
Users: Data analysts, financial analysts
Phase: Post-launch (6 months live)
Problem: Engagement dropped 30% last quarter
"""

# ✅ Be specific about format
format_instructions = """
Format: Executive Summary
Audience: C-level stakeholders
Length: 1 page max
Include: Top 3 issues, ROI estimate, timeline
"""

# ✅ Combine agent + context + format
full_prompt = f"{agent_prompt}\n\n{context}\n\n{format_instructions}"
```

**DON'T :**
```python
# ❌ Vague request
"Audit this"  # Too vague

# ❌ No context
"Run Nielsen audit"  # Agent doesn't know product, users, objectives

# ❌ Unclear expectations
"Give me insights"  # What kind? For who? How detailed?
```

---

### 2. Error Handling

```python
import anthropic
from anthropic import APIError, APIConnectionError, RateLimitError

def safe_agent_invocation(agent_path, user_request, max_retries=3):
    client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

    for attempt in range(max_retries):
        try:
            with open(agent_path) as f:
                agent_prompt = f.read()

            message = client.messages.create(
                model="claude-sonnet-4-5-20250929",
                max_tokens=8000,
                messages=[{
                    "role": "user",
                    "content": f"{agent_prompt}\n\n---\n\n{user_request}"
                }]
            )

            return message.content[0].text

        except RateLimitError:
            if attempt < max_retries - 1:
                time.sleep(60)  # Wait 1 min, retry
                continue
            raise

        except APIConnectionError:
            if attempt < max_retries - 1:
                time.sleep(5)  # Wait 5s, retry
                continue
            raise

        except APIError as e:
            print(f"API Error: {e}")
            raise

# Usage
try:
    report = safe_agent_invocation(
        "agents/analysis/ux-auditor-nielsen.md",
        "Audit dashboard"
    )
except Exception as e:
    print(f"Failed after retries: {e}")
    # Fallback logic
```

---

### 3. Cost Optimization

**Strategies :**

```python
# ✅ Use shorter prompts when possible
# Nielsen Audit = 40KB agent prompt
# If you only need "quick scan", create a shortened version

# ✅ Batch similar requests
# Instead of 50 API calls (1 per screenshot)
# Combine into 5 calls (10 screenshots per call)

# ✅ Cache agent prompts (avoid re-reading files)
class AgentCache:
    def __init__(self):
        self._cache = {}

    def load_agent(self, path):
        if path not in self._cache:
            with open(path) as f:
                self._cache[path] = f.read()
        return self._cache[path]

cache = AgentCache()
agent_prompt = cache.load_agent("agents/analysis/ux-auditor-nielsen.md")

# ✅ Use appropriate max_tokens
# Nielsen Audit detailed report: max_tokens=8000
# Quick scan P0 only: max_tokens=2000 (cheaper)
```

---

### 4. Logging & Monitoring

```python
import logging
from datetime import datetime

# Setup logging
logging.basicConfig(
    filename=f"logs/api_usage_{datetime.now().strftime('%Y-%m-%d')}.log",
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

def invoke_agent_with_logging(agent_path, user_request):
    logging.info(f"Invoking agent: {agent_path}")

    start_time = datetime.now()

    try:
        # ... API call ...
        result = invoke_agent(agent_path, user_request)

        duration = (datetime.now() - start_time).total_seconds()
        logging.info(f"Success - Duration: {duration}s")

        return result

    except Exception as e:
        logging.error(f"Failed: {e}")
        raise
```

---

## Ressources

**Claude API Documentation :**
- https://docs.anthropic.com/claude/reference/getting-started-with-the-api

**SDKs :**
- Python : https://github.com/anthropics/anthropic-sdk-python
- TypeScript : https://github.com/anthropics/anthropic-sdk-typescript

**Rate Limits & Pricing :**
- https://docs.anthropic.com/claude/reference/rate-limits
- https://www.anthropic.com/pricing

**Agents Repository :**
- `/agents/` (18 agents)
- `/frameworks/` (7 frameworks)
- `/docs/` (guides)

---

**Version** : 1.0
**Auteurs** : UX Agents Repository Team
