# 🚇 molinetes-subte-caba

Todos los pasajeros del subte porteño, molinete por molinete y de 15 en 15 minutos, desde **enero de 2023 hasta junio de 2026**. Es el material de entrada del notebook `EDA_ETL_Subte_v2.ipynb` (Metodología, Grupo 20) para que cualquiera pueda correrlo sin depender de nuestro Drive. 🙌

## Qué hay adentro

| Ruta | Qué es |
|---|---|
| `data/<año>/*.csv.gz` | Los CSV mensuales originales, comprimidos uno por uno con gzip. El contenido es idéntico: solo pesan ~12 veces menos (casi 3,5 GB → unos 275 MB). |
| `data/manifest.txt` | La lista de archivos mensuales. El notebook la lee para saber qué bajar. |
| `data/tarifas_sbase_2023_2026.csv` | Tarifa general por fecha de vigencia. La columna `url_fuente` apunta a la fuente de cada valor (Boletín Oficial de la Ciudad desde 2025-03; prensa y Observatorio de la Ciudad en 2023-2024). |
| `data/lineas-de-subte.csv` | Trazado de las líneas en formato WKT, para calcular kilómetros de red y dibujar el mapa. |
| `data/viajes_anual.csv` | Viajes anuales. |

## Cómo se usa

No hay que clonar nada a mano: la celda 3 del notebook descarga todo a una carpeta `datos_subte/` la primera vez (y la reutiliza después). Abrís el notebook, corrés las celdas en orden y listo. ☕ La primera ejecución completa tarda unos 5 minutos.

Si preferís bajar los datos por tu cuenta, cada archivo se lee tal cual con `pandas` o con `gzip`; el formato interno es el mismo que publicó el portal.

## De dónde sale

- **Molinetes:** portal de datos abiertos de la Ciudad de Buenos Aires (Ley 104 de CABA).
- **Tarifas:** resoluciones de SBASE en el Boletín Oficial de la Ciudad. Los valores de 2023-2024 y el de enero de 2023 todavía no están contrastados contra el Boletín (la columna `fuente` lo aclara fila por fila).
