# Biennial Update Sentinel

Is this US motor carrier's biennial MCS-150 update due, or already missed?

Every interstate motor carrier must refresh its MCS-150 every 24 months, by the last day of the month set by the last digit of its USDOT number, in odd or even years according to the next-to-last digit (49 CFR 390.19T). Missing it exposes the carrier to civil penalties and deactivation of its USDOT number.

For 1 to 10 USDOT numbers, this MCP server and HTTP API return: the last and next filing deadlines, the days left counted in the carrier's state time zone, the date of the last MCS-150 update on file, an overdue flag (true, false, or null when the rule or the data does not settle it), the exposure to deactivation, and the USDOT status. Source: the FMCSA Company Census File (data.transportation.gov), refreshed daily. It returns a regulatory status, never a score or a ranking of carriers.

- MCP (streamable HTTP): `https://mcs150.amacunia.fr/mcp`, tools `mcs150_lookup` (paid, 0.005 USDC per call via x402 on Base) and `mcs150_example` (free).
- HTTP: `GET https://mcs150.amacunia.fr/v1/mcs150?usdot=3327` (x402, 0.005 USDC; free trial: 3 calls per day).
- Free sample: `https://mcs150.amacunia.fr/v1/exemple`.
- Machine-readable: `/llms.txt`, `/.well-known/x402`, `/terms`.
- Paying client example: [`examples/pay_mcp.py`](examples/pay_mcp.py).

No account, no API key. No personal data is returned (no names, phones, e-mails or officers).

## Disclaimer

Information only, not legal advice; it does not replace a qualified attorney. Not affiliated with or endorsed by the FMCSA, the U.S. Department of Transportation or any U.S. government agency. Not a consumer report under the FCRA: do not use it to decide on employment, credit or insurance. The file does not show State (PRISM) exemptions, and a missed deadline does not mean the number is already deactivated: the FMCSA SAFER Company Snapshot is the authoritative record. Terms of use: https://mcs150.amacunia.fr/terms. Contact: contact@amacunia.fr
