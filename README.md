# EU & UK VAT Validator & Rate Engine — Python SDK

[![PyPI version](https://img.shields.io/pypi/v/stanzaapi-vat-validator.svg)](https://pypi.org/project/stanzaapi-vat-validator/)
[![Python Versions](https://img.shields.io/pypi/pyversions/stanzaapi-vat-validator.svg)](https://pypi.org/project/stanzaapi-vat-validator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> Deterministic offline checksum validator for EU-27 and UK VAT numbers with instant 2026 standard & reduced tax rate lookups.

Official, zero-dependency Python 3.8+ client library for **EU & UK VAT Validator & Rate Engine**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Intended for enterprise data pipelines, backend verification, and sub-5ms edge compute.

* 🌐 **Live Web Playground:** [Test your inputs online](https://stanzaapi.com/tools/vat-validator)
* 📚 **API Documentation:** [View full schema on Stanza](https://stanzaapi.com/tools/vat-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
pip install stanzaapi-vat-validator
```

---

## 🚀 Quickstart

```python
import os
from stanzaapi_vat_validator import VatValidatorClient

# Initialize client (api_key optional for local evaluation)
client = VatValidatorClient(
    api_key=os.getenv("STANZA_API_KEY")
)

# Execute deterministic validation
response = client.validate("DE123456789")

if response.get("success"):
    print("Verification Success:", response["data"])
else:
    print("Validation Error:", response.get("error"), response.get("code"))
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "vat_number": "DE123456789",
    "country_code": "DE",
    "standard_rate": 19,
    "reduced_rate": 7
  }
}
```

---

## ⚙️ Client Options

| Parameter | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `api_key` | `Optional[str]` | `os.getenv("STANZA_API_KEY")` | Your [Stanza API Key](https://stanzaapi.com). Required for production quotas. |
| `base_url` | `Optional[str]` | `"https://api.stanzaapi.com/vat-validator"` | Public edge API base URL. |
| `timeout` | `int` | `15` | Request timeout in seconds. |


---

## 🔗 Useful Links

* [EU & UK VAT Validator & Rate Engine Interactive Sandbox](https://stanzaapi.com/tools/vat-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/StanzaAPI/vat-validator-python)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
