# CORS-Validator

A lightweight Python-based CORS validation tool that tests a target URL against a series of forged `Origin` values to detect misconfigured Cross-Origin Resource Sharing (CORS) policy behavior.

This project is designed for security testing and reconnaissance in a responsible, authorized context. It helps identify whether a web application reflects or accepts unexpected origins via the `Access-Control-Allow-Origin` response header.

## What it does

The script sends requests to a specified target while varying the `Origin` header using common bypass payloads and localhost-style values. If the server responds with `Access-Control-Allow-Origin` matching one of those values, it flags the response as potentially vulnerable or misconfigured.

## Requirements

- Python 3
- `requests`

Install dependencies:

```bash
pip install requests
```

## Usage

Basic usage:

```bash
python3 cors-validator.py -d https://example.com
```

With a cookie file:

```bash
python3 cors-validator.py -d https://example.com -c cookies.txt
```

### Arguments

- `-d`, `--domain`: The target URL to fuzz
- `-c`, `--cookie`: Optional file containing cookies to include in requests

## Example

```bash
python3 cors-validator.py -d https://example.com
```

The tool will iterate through common origin permutations and report any response where the server allows an origin value that appears suspicious or reflected.

## Notes

- Only test sites that you own or have explicit authorization to assess.
- This tool is intended for security research and authorized penetration testing.
- Use caution when handling cookies or authentication material.

## Disclaimer

This project is for educational and authorized security testing purposes only. The author and contributors are not responsible for misuse of this tool.
