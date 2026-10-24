# ORCA - Ocean Resource Characterisation & Assessment

An Indian oceanographic data platform for scientific data integration, analysis, and visualisation.

## Project Status

ORCA is currently in the planning and early development stage. The architecture, product vision, and development roadmap describe proposed designs and capabilities. Features should not be considered implemented, tested, or validated unless explicitly documented as such.

Development will proceed incrementally, with each capability implemented, tested, and evaluated before being considered complete.


## 1. Overview

ORCA is a student-led marine-information, scientific-analysis, and ocean-intelligence initiative focused on India's coastline and island regions.

The project aims to integrate authoritative marine information, historical ocean observations, climate context, and scientific analysis into a unified, region-oriented platform. Its purpose is to make reliable marine information more accessible, identify meaningful changes in ocean conditions, and explain what available evidence supports—and what remains unknown.

ORCA is designed around two complementary missions: Marine Safety and Ocean Discovery.

## 2. Vision

To build an extensible, evidence-driven marine-intelligence platform connecting source data, scientific analysis, historical context, uncertainty, and understandable explanations for coastal communities, researchers, scientists, and concerned citizens.

## 3. Primary Missions

### Mission A - Marine Safety

Improve access to authoritative information about marine conditions, official safety warnings, ocean-state forecasts, and Potential Fishing Zone (PFZ) advisories.

The platform aims to help users locate relevant information for supported regions while preserving the authority of the agencies issuing official forecasts and warnings.

### Mission B - Ocean Discovery

Analyse marine observations, identify unusual patterns, investigate relationships between ocean and atmospheric variables, study climate phenomena, and support scientific characterisation of ocean resources.

Long-term research includes seabed-resource characterisation, including manganese nodules, when suitable authoritative or scientific survey data is available.

## 4. ORCA v1 - Ocean Pattern Explorer with Safety Context

The initial product vision combines reliable marine information with reproducible scientific analysis.

Proposed capabilities include:

1. Display a verified official marine forecast or advisory for a supported region, with its source and validity period.
2. Analyse historical sea-surface temperature (SST) anomalies using an appropriate historical baseline.
3. Provide a climate-context view using a documented ENSO or IOD indicator, clearly separated from local forecasts.
4. Provide interactive maps and timelines for exploring ocean conditions and comparing historical periods.
5. Use a controlled AI assistant to answer supported questions using validated records and links to underlying evidence.

These capabilities depend on confirming compatible data sources, access methods, historical coverage, and validation procedures. Where reliable integration is unavailable, verified features should be released first, with links to official sources retained as a fallback.

## 5. Product Principles

### Safety and Scientific Integrity

ORCA must distinguish official warnings, scientific observations, statistical anomalies, derived analytical results, and experimental predictions. An anomaly does not automatically indicate danger, and the absence of a warning does not establish that conditions are safe.

### Evidence Before Conclusions

Every scientific finding should be traceable to its source records, timestamps, analytical method, data quality, and known limitations.

### Controlled AI

AI should help users query, interpret, and understand verified information. Scientific calculations must be performed by tested analytical functions rather than improvised by a language model. The AI component must not invent missing observations or execute arbitrary code.

### Shared Foundation, Separate Domains

Marine safety, ocean observations, weather and climate analysis, and resource characterisation should share common infrastructure while retaining domain-specific data models, scientific meanings, and validation requirements.

### Incremental Development

Every version must deliver a working improvement, pass defined tests, and establish the foundation for the next stage.

### Transparent Limitations

Unavailable data, missing observations, stale information, uncertainty, and unsupported conclusions must be clearly identified.

## 6. Proposed System Architecture

ORCA is planned to begin as a Python-based modular monolith: one deployable application with clearly separated internal components. Separate servers or microservices should only be introduced when justified by actual technical or operational requirements.

The proposed architecture comprises eight layers:

1. Presentation and User Experience: Regional dashboard, interactive maps, region and time-period selection, charts, advisory views, and the AI question interface.
2. Application Coordinator: Resolves region and time range, selects domain services, coordinates retrieval and analysis, and enforces supported workflows.
3. Domain Services: Separate services for marine safety, ocean observations and anomaly analysis, weather and climate intelligence, and marine-resource characterisation.
4. Scientific Analysis: Historical baselines, anomaly detection, statistical analysis, spatial and time-series comparisons, and reproducible outputs.
5. Controlled AI Service: Interprets supported requests, calls approved retrieval and analysis functions, explains findings using evidence, and reports uncertainty.
6. Validation and Provenance: Source identification, timestamp and validity checks, unit and coordinate validation, coverage checks, missing-data handling, and traceability.
7. Shared Marine Information Foundation: Geographic and temporal metadata, source registry, original records, permitted historical snapshots, processing history, and shared data contracts.
8. Source Integration: Modular adapters for accessible official sources, APIs, feeds, and scientific datasets.

Validation should occur before analysis and again before results are presented. Different scientific data types must retain their distinct meanings rather than being forced into an unsuitable universal record.

## 7. Proposed Technology Direction

- Core language: Python
- Initial interface: Streamlit
- Data processing: Python-based scientific and analytical workflows
- Data storage: Structured datasets and lightweight storage where appropriate
- Visualisation: Interactive maps, charts, and time-series comparisons
- Version control: Git and GitHub
- AI integration: Controlled tool-calling workflows grounded in retrieved evidence

Technology choices may evolve as implementation requirements become clearer.

## 8. Development Roadmap

The following roadmap represents the proposed development plan. A version is complete only when its defined deliverables have been implemented, tested, and documented.

| Version  | Focus |
| ---|---|
| V0.1     | ORCA Blueprint: requirements, architecture, data-source feasibility, and governance |
| V0.2     | Marine Data Foundation: retrieval, metadata, validation, provenance, and reproducible processing |
| V0.3     | Marine Information MVP: supported regions, official-source registry, advisory links, and basic historical views |
| V0.4     | Ocean Anomaly Engine: historical baselines, anomaly calculations, quality filtering, and evaluation |
| V0.5     | Weather and Climate Intelligence: historical climate context and ocean-atmosphere analysis |
| V0.6     | Controlled AI Assistant: evidence-grounded questions and explanations |
| V0.7     | Ocean Resource Characterisation: survey-based resource research |
| V0.8     | Cross-Domain Ocean Intelligence: integrated analysis across supported domains |
| V0.9     | Integrated Pilot: end-to-end testing, failure handling, demonstrations, and review |
| V1.0     | Validated ORCA Release: documented scope, tested calculations, deployment instructions, and known limitations |
| V1.1-V1.5| Coverage and Reliability: additional regions, validated sources, accessibility, and operational robustness |
| V2.0     | Advanced Pattern Discovery: multivariable analysis and evaluated spatial and temporal patterns |
| V2.x     | Forecasting and Decision-Support Research: evaluated experimental models and uncertainty estimates |
| V3.0+    | Expanded Ocean Intelligence Platform: broader datasets, research workflows, resource characterisation, and appropriate decision support |

### Recommended Development Order

The recommended target is V0.5 as the initial scientific demonstration, with V0.3 as the minimum working foundation. Later stages should proceed only after earlier stages meet their completion criteria.

## 9. Scientific Analysis and Innovation 

ORCA's proposed differentiation is not an anomaly-detection formula alone. It is the integration of several capabilities:

- Cross-source evidence: Preserve source identity, units, time conventions, and quality information.
- Context-aware detection: Compare observations against appropriate historical and seasonal baselines instead of applying a single global threshold.
- Evidence-backed explanations: Present observed values, baselines, deviations, quality status, source records, and uncertainty.
- Climate context: Support comparisons with documented ENSO, IOD, and other relevant climate indicators.
- Separate but connected resource intelligence: Distinguish surveyed evidence, derived estimates, and unknown areas.
- Reproducible analysis: Retain sufficient source records, methods, and configuration details to reproduce findings.

These are proposed differentiators, not claims of established novelty. Their distinctiveness requires comparison with existing platforms and scientific research.

## 10. Data Sources

Candidate sources include:

- "INCOIS Data Holdings" (https://incois.gov.in/site/dataholdings.jsp)
- "INCOIS ERDDAP Catalogue" (https://erddap.incois.gov.in/erddap/griddap/NOAA_AVHRR_AMSR_datasets.html)

Sources will be assessed for accessibility, historical coverage, metadata, data quality, and usage conditions before integration. Listing a source does not imply that it has been integrated or validated.

## 11. Team Structure

Haider - Team Lead and Interface, Documentation, Demo and AI Integration Lead

Responsible for team coordination, user interface and experience, regional map and result presentation, documentation, demonstrations, and collaboration on AI integration.

LinkedIn: [Moien Haider](https://www.linkedin.com/in/moien-haider-430b6139b/)

Anurag - Lead Developer and Agent Integration Lead

Responsible for application architecture, core Python development, shared data contracts, integration of data and scientific services, and coordination of agent workflows.

LinkedIn: [Anurag Chand](https://www.linkedin.com/in/anurag-chand-22149a437/)

Sarthak - Testing and Reliability Lead and AI Component Lead

Responsible for software and scientific testing, anomaly-detection evaluation, reliability, failure handling, AI component development, and evidence-grounded response validation.

LinkedIn: [Sarthak Singh](https://www.linkedin.com/in/sarthak-singh-a0856a275/)

Saurabh - Git Organisation and Code Review Lead

Responsible for repository organisation, Git and GitHub workflows, code reviews, pull requests, technical critique, architectural review, and development discipline.

LinkedIn: [Saurabh Singh](https://www.linkedin.com/in/saurabh-singh-it/)

### Collaborative Decisions

Major versions should receive team review. Architectural changes, scientific thresholds, and claims about results require appropriate technical scrutiny.

## 12. Definition of Success

ORCA's progress will be measured by demonstrated capabilities rather than the number of features.

A successful early prototype should be able to:

- Retrieve or load documented marine data.
- Validate records and preserve their provenance.
- Display relevant information for a supported region.
- Detect unusual observations relative to an appropriate baseline.
- Reproduce analytical findings.
- Compare selected historical ocean and climate patterns.
- Explain findings with evidence and limitations.
- Clearly distinguish official warnings from ORCA-derived analysis.
- Establish a credible path towards marine-resource characterisation without unsupported claims.

## 13. Disclaimer

ORCA is a student-led scientific and engineering project. Its proposed capabilities require appropriate data access, implementation, testing, and validation before practical use.

Experimental predictions must never be presented as official forecasts or warnings. Correlation does not establish causation, and observations or anomalies do not independently establish the presence, abundance, or commercial recoverability of marine resources.

ORCA is intended to complement authoritative marine information, not replace official agencies or guarantee marine safety.

---

ORCA - Ocean Intelligence Through Evidence

A single platform connecting marine information, scientific analysis, and understandable evidence.