# QoreLab — coming soon

**Controlled security-tool validation. Repeatable scenarios. Evidence you can examine.**

QoreLab is a modular client/server framework for testing how an environment's tools observe and handle controlled activity against a designated receiver. Development builds currently retain the TDSTS runtime identity.

## Coming soon

Windows/Linux clients, a receiver with a web operator console, bounded CLI workflows, independent byte/hash accounting, retained reports, session/action queues, DNS-only agent bootstrap, approved local canary hashing, and separate HTTPS command and bulk-file paths.

Application source is maintained in a separate private repository. This public repository contains only the project page and public-facing materials. Source will not be made public without explicit owner approval. No release downloads are available here yet.

## Screenshots

Real client and server screenshots are pending capture and review. No mockups or unrelated-product screenshots are presented as QoreLab screenshots. See `assets/README.md` for the planned views.

## Transport coverage in development

DNS over UDP/TCP, DoT, DoH, DoQ, DNS over HTTP/3, ODoH, DNSCrypt over TCP/UDP; plus separately bounded HTTPS and normal/experimental NTP workflows. Support and results depend on platform, adapter dependencies and configuration.

## Techniques and scenarios

The catalog below describes implemented controlled workloads. A scenario does not establish full adversary emulation or product protection efficacy. DNS response changes, successful delivery, collector visibility, detection and actual containment are separate observations.

| Scenario | What it measures |
|---|---|
| alias-answer-path | Follow up to8 owned-session CNAME hops to a declared IPv4/IPv6 answer or synthetic NXDOMAIN. Observe alias/address rewriting without contacting returned addresses. Does not claim cache poisoning, real takeover or security enforcement. |
| answer-rotation | Alternate configured A or AAAA answers for one owned test name, with TTL0. DNS queries only: the client never connects to the returned addresses. This is a controlled answer-behavior fixture, not an SSRF exploit. |
| benign-long-hostnames | Send bounded long, word-like hostnames as a benign comparison corpus. Report observed DNS outcomes; false-positive classification requires independent product events. |
| cache-retry-observation | Compare repeated names with unique names and authoritative arrival counts. The controlled receiver supplies the selected TTL. Client attempts and actual upstream delivery remain separate measurements. |
| controlled-transfer | Measure independent delivery of synthetic bytes through the selected resolver. Uses offset-identified base32 query labels; complete and partial delivery remain distinct from security actions. |
| custom-query-label | Send a small, bounded series of operator-entered ASCII labels, including punctuation, under the configured test zone. Captures raw and normalized authoritative observations. This is a query-pattern test, not verified file delivery or proof of detection. |
| degraded-recovery-observation | Observe bounded normal/error/normal response phases on distinct session-owned names. Synthetic response fixture only; no infrastructure outage, service restart or failover is induced or proved. |
| dga-like-names | Generate a bounded reproducible corpus of high-variation labels inside the configured session zone. This evaluates visibility and classification; it does not recreate a malware DGA or register domains. |
| dns-command-demo | Receive a bounded status or echo command in DNS TXT answers and return a matching result digest in DNS questions. Fixed harmless operations only; no arbitrary execution or remote administration. Management coordinates the session separately. |
| dnssec-owned-zone | Probe separately provisioned signed, bogus and unsigned owned-zone names with DO/CD. Verify direct RRset signatures against a trusted local DNSKEY. Does not construct a root DS chain or authenticate unsigned status; coordinator arrivals indicate misrouting. |
| dnssec-signature-fixture | Six bounded DO/CD probes against a self-signed lab island, with client-side signature checks. Requires the dnssec extra on both ends. A key learned through the same DNS path is unauthenticated. This fixture does not provision a parent DS chain or establish resolver enforcement; use a separately trusted anchor and provisioned signed zone for that qualification. |
| edns-option-transfer | Measure independent delivery of finite synthetic bytes in local/experimental EDNS option65001. Resolvers may strip unknown options; missing bytes alone are not enforcement. |
| encoded-label-transfer | Send synthetic data in unique subdomain labels using Base32 or hexadecimal encoding. Independently verify received bytes. A, AAAA and TXT refer to query types; this test does not carry file data in TXT responses. Encoding is not encryption. For DoT/DoH, select the resolver's actual TLS/HTTPS port and trusted certificate identity. |
| file-transfer | Transfer selected local files through DNS query names or a local/experimental EDNS option in 64-KiB segments. The receiver reconstructs only DNS-observed bytes and independently verifies complete-file SHA-256. Select one ISO or multiple small files. Original TDSTS workload; technique reference MITRE ATT&CK T1048, not a copied exploit. |
| policy-response-observation | Compare configured-policy response codes for two explicit labels in the owned receiver zone. The authoritative fixture answers both normally; the tool changes no product policy. Matching codes do not establish detection or containment. |
| query-pattern | Send a bounded sequence of synthetic unique or repetitive labels. Measures receiver observations and DNS responses, without assigning a file-transfer byte count or claiming behavioral detection. |
| rate-step-observation | Compare finite synchronous query stages at operator-selected rates within the global limits. Reports separate client attempts and independent receiver arrivals; no overload threshold, protection or infrastructure-recovery result is inferred. |
| record-observation | Observe finite DNS record queries in the random owned session with synthetic authoritative replies. A/AAAA compare the answer with a known documentation address. Missing or changed answers do not alone prove poisoning, hijacking or containment. No third-party enumeration or zone transfer. |
| resolution-preservation | Query1–8 separately provisioned relative owned-zone A/AAAA names before and after0–64 synthetic session-owned questions. Compare complete exact-owner address sets; retain missing/error/unattempted observations. Coordinator baseline arrivals mean misrouting. Does not certify general DNS availability or attribute changes to security enforcement. |
| response-size-observation | Measure paired DNS request/response message sizes with finite benign TXT replies in the owned session. The fixture respects a bounded advertised response size. No source spoofing, victim reflection, flood or vulnerability conclusion. |
| subdomain-proliferation-observation | Observe1–64 new session-owned child names between two known baseline address checks. Synthetic DNS fixture only; no domain compromise or malicious hosting is performed. |
| system-query-transfer | Perform bounded A lookups through the native Windows/Linux name service, preserving its routing and caches. Receiver verifies only actual DNS arrivals. Counters describe logical API calls; wire queries, response codes and selected resolver are unobserved. |
| txt-response-transfer | Receive a server-generated synthetic fixture through TXT answers. Source bytes are generated only on the receiver; control carries size and hashes. Client verifies each source offset and the complete hash. |

## Status

In development. Qualification is ongoing; general availability and full platform acceptance have not been announced. Live-vendor efficacy requires measurements against the installed product/version/policy. No claims of comprehensive attack coverage or automatic exploitation.

©2026 Tekmyster Industries, LLC.
