<div align="center">
  <img src="Whisper_Logo.png" alt="Whisper Logo" width="400"/>

  # Whisper API SDK - Python

[![CI](https://github.com/whisper-sec/sdk-python/actions/workflows/python.yml/badge.svg)](https://github.com/whisper-sec/sdk-python/actions/workflows/python.yml)
[![PyPI version](https://badge.fury.io/py/whisper_api_sdk.svg)](https://badge.fury.io/py/whisper_api_sdk)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **Official Python SDK for Whisper API** - Comprehensive threat intelligence and security operations for domains, IPs, and web infrastructure.

**[Website](https://www.whisper.security)** | **[Documentation](https://docs.whisper.security)** | **[API Reference](https://developer.whisper.security)** | **[API Playground](https://dash.whisper.security/playground)** | **[Contact Us](https://www.whisper.security/contactus)**

</div>

---

## Quick Start

### Installation

```bash
pip install whisper_api_sdk
```

### Get Your API Key

Sign up at [dash.whisper.security](https://dash.whisper.security) to get your API key.

### First Request

```python
import whisper_api_sdk

configuration = whisper_api_sdk.Configuration(
    host="http://api.whisper.security",
    access_token="YOUR_API_KEY"
)

with whisper_api_sdk.ApiClient(configuration) as api_client:
    api = whisper_api_sdk.IndicatorsApi(api_client)

    # Enrich an IP address
    response = api.get_indicator("ip", "8.8.8.8")
    print(response)
```

---

## Key Features

- **Async Support** - Built-in support for async/await patterns
- **Fully Typed** - Complete type hints for IDE autocomplete
- **Comprehensive** - IP, Domain, DNS, WHOIS, Routing, Geolocation, Screenshots, AI/ML
- **Fast** - Sub-500ms typical response times with strategic caching
- **Python 3.8+** - Modern Python with full type annotations

---

## API Overview

### Indicators API
Enrich IPs and domains with comprehensive threat intelligence.

```python
api = whisper_api_sdk.IndicatorsApi(api_client)

# Basic enrichment
ip_data = api.get_indicator("ip", "8.8.8.8")

# With additional data modules
domain_data = api.get_indicator("domain", "example.com", include="whois,dns_details")

# Get relationship graph
graph = api.get_indicator_graph("ip", "8.8.8.8")

# Historical data
history = api.get_indicator_history("domain", "example.com", limit=10)

# Predictive risk score (AI-powered)
risk = api.get_predictive_risk("ip", "8.8.8.8")

# Subdomain discovery
subdomains = api.get_subdomains("example.com", limit=100)
```

### Location API
Geolocation lookups and network analysis.

```python
api = whisper_api_sdk.LocationApi(api_client)

# Single IP geolocation
location = api.get_ip_location("8.8.8.8")

# Bulk geolocation (up to 1000 IPs)
bulk_result = api.get_bulk_ip_location(bulk_request)

# Network/CIDR lookup
network = api.get_network_location("8.8.8.0/24")

# Search by attributes
results = api.search_location(field="city", value="San Francisco", limit=100)
```

### Operations API
Async operations for scanning, monitoring, and AI-powered analysis.

```python
api = whisper_api_sdk.OperationsApi(api_client)

# Screenshot capture (returns job ID)
job = api.create_screenshot(screenshot_request)

# Infrastructure scan
scan_job = api.create_infrastructure_scan(scan_request)

# Check job status
status = api.get_job(job.job_id)

# AI-powered investigation
investigation = api.ai_investigate(investigate_request)

# Similar threat cases
cases = api.ai_similar_cases(similar_cases_request)
```

---

## Authentication

All endpoints require Bearer token authentication:

```python
import os

configuration = whisper_api_sdk.Configuration(
    host="http://api.whisper.security",
    access_token=os.getenv("WHISPER_API_KEY")
)
```

---

## Rate Limits

| Category | Limit |
|----------|-------|
| Standard Enrichment | 100 req/min |
| Bulk Operations | 10 req/min |
| Search/Discovery | 5 req/min |
| Screenshots | 10 req/min |

Rate limits return HTTP 429 with a `Retry-After` header.

---

## Documentation

- **API Documentation**: [docs.whisper.security](https://docs.whisper.security)
- **API Reference**: [developer.whisper.security](https://developer.whisper.security)
- **Python Docs**: See the `docs/` directory

---

## Support

- **Email**: [support@whisper.security](mailto:support@whisper.security)
- **Issues**: [github.com/whisper-sec/sdk-python/issues](https://github.com/whisper-sec/sdk-python/issues)

---

## License

MIT License - See [LICENSE](LICENSE) file for details.

---

*Built with Python by Whisper Security*
