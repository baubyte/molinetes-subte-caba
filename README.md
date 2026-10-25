# molinetes-subte-caba

Monthly turnstile data (15-minute blocks) of the Buenos Aires subway, January 2023 to June 2026, plus auxiliary tables used by the EDA/ETL notebook `EDA_ETL_Subte_v2.ipynb`.

- `data/<year>/*.csv.gz`: original monthly CSV files, gzip-compressed one by one (content unchanged).
- `data/manifest.txt`: list of the compressed files; the notebook downloads from it.
- `data/tarifas_sbase_2023_2026.csv`: general fare per effective date. `url_fuente` links to the source (Boletín Oficial de la Ciudad for 2025-03 onward; press/Observatorio for 2023-2024).
- `data/viajes_anual.csv`: annual trips.

Source of the turnstile data: Buenos Aires open data portal (Ley 104 de CABA).
