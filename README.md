# SEO Content Gap Analyzer

Interne SEO-tool van Pure Minds. Hij legt een pagina naast de organische
Google-top 10 (Nederland) voor een zoekwoord en laat zien welke onderwerpen,
termen en vragen de concurrenten behandelen en de pagina nog mist.

Plain HTML, CSS en JavaScript met één serverless function (`api/analyze.js`) op
Vercel; de API-keys en de instructies voor het model staan alleen op de server.

## Online zetten (Vercel)

1. Vercel → **Add New → Project** → importeer
   `PureMindsMarketingGroup/SEO-contentGap-Analyzer`.
2. Zet onder **Settings → Environment Variables**:

   | Variabele | |
   |---|---|
   | `ANTHROPIC_API_KEY` | Verplicht. Een key van Pure Minds uit de Anthropic Console. |
   | `SERPER_API_KEY` | Verplicht. De Google-top 10 via serper.dev. |
   | `SYSTEM_PROMPT` | Verplicht. De instructies voor het model. Staat bewust niet in deze repo; Pure Minds bewaart hem zelf. |
   | `APP_PASSWORD` | Optioneel. Zet de tool achter een wachtwoord. |

3. Deploy. Daarna deployt elke push naar `main` vanzelf.

Zonder `SYSTEM_PROMPT` start er geen analyse; de tool zegt dan wat er ontbreekt.

## Lokaal draaien

```bash
npm install
cp .env.example .env.local   # en vul de waarden in
npx vercel dev
```
