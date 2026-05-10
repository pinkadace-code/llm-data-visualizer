# LLM Data Visualizer

Rīks kas automātiski analizē datubāzes datus un izveido vizuālo pārskatu, izmantojot LLM.

## Kā tas strādā

1. **Plāna ģenerēšana** — LLM analizē datubāzes struktūru un izveido vizualizāciju plānu
2. **SQL ģenerēšana** — katram plāna punktam LLM ģenerē SQL vaicājumu
3. **Datu vizualizācija** — dati tiek attēloti grafikos (stabiņu, līnijas, sektoru u.c.)
4. **AI ieskati** — LLM ģenerē aprakstu un secinājumus par katru vizuāli
5. **HTML pārskats** — visi vizuāļi apkopoti vienā HTML lapā

## Tehnoloģijas

- **Python** — Google Colab vide
- **Groq API** — LLM (llama-3.3-70b-versatile)
- **MySQL** — datubāze (direct_payments)
- **Pandas** — datu apstrāde
- **Matplotlib / Seaborn** — vizualizācijas
- **HTML/CSS** — pārskata lapa

## Datubāzes struktūra
- `organisations` — organizācijas (id, created_at, parent_vertical)
- `mandates` — maksājumu mandāti (id, created_at, scheme, organisation_id)
- `payments` — maksājumi (id, amount, currency, created_at, source, charge_date, mandate_id)

## Faili

- `llm_data_visualizer.ipynb` — galvenais Colab notebook
- `report.html` — ģenerētais vizuālais pārskats
- `.env.example` — API atslēgas piemērs

## Uzstādīšana

1. Atver `llm_data_visualizer.ipynb` Google Colab
2. Pievieno Colab Secrets:
   - `GROQ_API_KEY` — Groq API atslēga
   - `DB_PASSWORD` — MySQL parole
3. Palaid visas šūnas secībā
4. `report.html` tiks lejupielādēts automātiski
