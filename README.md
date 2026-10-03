# CheckMyPayRate — open salary benchmarks + MCP server

Salary benchmarks for **20 countries** and **13 sectors**, derived from official
OECD and Eurostat statistics. Gross annual pay in each country's own currency.

🌐 Website: https://checkmypayrate.com
📊 Live dataset (updated daily): https://checkmypayrate.com/data
📐 Methodology: https://checkmypayrate.com/methodology

## Dataset

- `salary-benchmarks.csv` — snapshot of the benchmark table
- Live CSV: https://checkmypayrate.com/api/public/dataset/csv
- Live JSON: https://checkmypayrate.com/api/public/dataset/json

**Columns:** country_code, country_name, sector, monthly_value, annual_value,
currency, reference_year, source, last_updated

**Countries:** United States, United Kingdom, Germany, France, Canada, Australia,
Estonia, Sweden, Finland, Norway, Netherlands, Switzerland, Austria, Ireland,
Italy, Spain, Portugal, Poland, Belgium, Denmark

**Sectors:** national average, IT & software, finance & insurance, energy &
utilities, professional & consulting, manufacturing, public administration,
healthcare, education, construction, transport & logistics, retail & wholesale,
hospitality & food

### How the figures are built

1. **National average** — OECD average annual wages per full-time equivalent
   employee (series AV_AN_WAGE).
2. **Sector ratio** — Eurostat national accounts (nama_10_a64): compensation of
   employees ÷ number of employees, relative to the whole economy.
   - 14 EU countries + Norway: each country's own Eurostat sector ratios
   - Canada and Australia: EU-27 average sector structure (marked as an estimate)
   - Switzerland: only sectors with Swiss data
   - United States and United Kingdom: no sector figures; the website offers
     occupation-level pay from BLS and ONS instead
3. **Sector benchmark** = national average × sector ratio.

**Limitations:** sector figures are modelled estimates, not directly measured
salaries. Sector ratios are per employee, not per full-time equivalent, so
sectors with many part-time workers (healthcare, education, retail, hospitality)
may appear lower than full-time pay. Figures are not adjusted for cost of living.

## MCP server

A remote MCP server lets AI assistants query the benchmarks directly.

- **Endpoint:** `https://checkmypayrate.com/mcp` (Streamable HTTP)
- **Authentication:** none required

**Tools**

| Tool | Description |
|---|---|
| `list_options` | Supported country and sector codes |
| `get_salary_benchmark` | Benchmark for a country and sector |
| `compare_salary` | Compare a salary with the benchmark as a percentage |

## License

Dataset: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Attribution: "Data via checkmypayrate.com (OECD/Eurostat-derived salary benchmarks)".
Underlying sources: OECD and Eurostat, used under their respective reuse terms.

## Contact

Corrections and questions: https://checkmypayrate.com/contact
