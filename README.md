# Social Research API

Node.js + Express API for campaign research using Claude AI.

## Quick Start

```bash
npm install
cp .env.example .env
# Add your ANTHROPIC_API_KEY to .env
npm start
```

## API Endpoints

### GET /health
Health check.

### POST /api/research
Generate campaign research.

**Request:**
```json
{
  "brand_config": {
    "brand_name": "string",
    "markets": ["HK"],
    "languages": ["zh-HK", "en"],
    "platforms": ["IG", "Threads"]
  },
  "campaign_brief": {
    "title": "string",
    "objectives": ["Awareness"],
    "primary_audience": "string",
    "product_description": "string"
  }
}
```

**Response:**
```json
{
  "campaign_research_result": {
    "content_directions": [...],
    "trends": [...],
    "competitors": [...]
  }
}
```

## Deploy to Fly.io

```bash
fly launch
fly secrets set ANTHROPIC_API_KEY=your_key
fly deploy
```
