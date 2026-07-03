# MOHIM Equity Architecture

This repository implements a reference architecture for an equity-oriented
occupational health system aligned with the MOHIM Integrated 23 Framework.

## Non-negotiable architectural requirements

1. **Mandatory SDOH data layer**  
   All 19 independent variables (IVs) are modeled as first-class, FHIR-aligned
   data fields integrated into the risk stratification pipeline alongside
   clinical and environmental data.

2. **Disaggregated equity KPIs across all 12 dependent variables (DVs)**  
   Every performance metric is reported separately for subgroups defined by:
   race/ethnicity, gender, disability status, wage tier, geographic region,
   and intersectionality burden index, with explicit equity benchmarks and
   accountability for subgroup disparities.

3. **Anti-surveillance governance protocols as enforceable policy**  
   Institutional betrayal (C-6) is treated as a governance risk, mitigated via:
   employer access prohibitions, worker-controlled data deletion rights,
   anonymization-by-default for aggregates, and community oversight of data use.

## Services

- `sdoh_layer`: SDOH data model + FHIR mapping
- `kpi_engine`: disaggregated equity KPI computation
- `governance`: policy-as-code, access control, anonymization

## Quick start

```bash
git clone https://github.com/<your-username>/mohim-equity-architecture.git
cd mohim-equity-architecture
pip install -r requirements.txt
uvicorn app.main:app --reload
