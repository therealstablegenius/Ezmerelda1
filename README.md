.AXIOM0 v0.7 — General-Purpose Raspberry Pi 5 Edition
New: AXIOM0 now offers a local Linux application management layer and general Ollama assistant, alongside its existing Living City research modules. This is a user-space application platform, not a new Linux kernel or a way to make incompatible software run.

Raspberry Pi 5 installation: bash deploy/raspberry-pi5/install.sh on Raspberry Pi OS 64-bit. It installs Ollama online, configures CPU/RAM-conscious settings, downloads a small model, and sets up local services. Details in [Raspberry Pi 5 guide](docs/RASPBERRY_PI_5.md). Source distribution does not include a preinstalled Ollama binary.

General AI: .venv/bin/axiom0-os ask "Hello AXIOM0"; Linux apps: .venv/bin/axiom0-os register editor -- /usr/bin/nano then .venv/bin/axiom0-os run editor; hardware: .venv/bin/axiom0-os doctor. Models cannot trigger app execution without explicit user commands.
AXIOM0 Living City v0.6 — SemiSoul / 3·6·9 Local Pilot
Author and concept originator: Howard Rice
Build status: local pilot reference implementation; not certified for production, not an official City of Kansas City, Missouri system.
Key distinction: Truth may exist before proof. A claim is not established by the fact that someone believes it, a model predicts it, or a number resembles a pattern.
The story behind AXIOM0: From the Cancer Advisory Board to Living City
AXIOM0 did not begin as a municipal AI project. It began with a problem of missing human information.

Howard Rice traces the idea to his work with a Cancer Advisory Board (CAB). He encountered incomplete data collection when some Black and Mexican men did not provide information sought for the datasets. That experience brought a consequential research problem into focus: a condition, experience, or need can exist even when the corresponding data field is empty. The available record may fail to capture an underlying reality; it does not follow that the underlying reality is absent.

Rice began developing AXIOM0 to compensate analytically for incomplete datasets—to work with what was known while investigating what could not yet be established. This was the origin of his guiding insight: “Truth exists before proof.” In this context, the phrase does not mean that a compelling guess becomes a fact. It means that reality does not wait for a complete survey, a successful interview, or an assembled evidentiary file. Our knowledge of reality, however, still depends on evidence, verification, and correction.

His original ambition should not be confused with an independently validated missing-data reconstruction algorithm. Missing responses must never silently become invented patient facts. A future AXIOM0 research pipeline can instead explicitly mark missingness, document how records were collected, examine the possibility of selection or nonresponse bias, produce bounded estimates or scenarios when justified, report uncertainty, and identify the information necessary for responsible follow-up. Particularly with health data, personal information should be handled only under appropriate consent and governance; no inferred clinical fact should be treated as an actual person's medical record.

That research experience shaped the later architecture:
- Numerical AXIOM0 became a formal, testable language for symbolic state and relationships; its harmony calculations are experimental telemetry, not verified substitutes for missing health observations.
- SemiSoul became a design for an intelligent system that remembers its sources, actions, uncertainty, commitments, and corrections across changes of model or hardware. Continuity is engineered and auditable; consciousness is not established.
- 3·6·9 inquiry became a discipline for observing, challenging and revisiting hypotheses. The numbers organize the inquiry; they do not create proof or guarantee manifestations.
- Living City extended the original concern with missing information into municipal administration: unheard residents, incomplete records, fragmented service requests, changing ordinances, and decisions lacking traceable follow-through.
Rice's later work in Kansas City's City Clerk's Office deepened the civic application. His committee and commission support, municipal research, technology interests, and attention to public accountability informed AXIOM0's versioned source library, evidence review and authorized human oversight.

Rice also brings a spiritual thesis to the project: that mathematical intelligibility and the existence of truth independent of our knowledge may point toward God. This is a philosophical and theological interpretation worth explaining accurately—not a theorem established by AXIOM0, the 3·6·9 pattern, the SemiSoul architecture, or an AI model. The software cannot demonstrate that God exists or inhabits an AI.

The engineering commitment arising from the story is concrete: do not mistake missing information for a missing reality, and do not mistake a plausible reconstruction for verified evidence.

For an expanded account and research safeguards, see [`docs/ORIGIN_AND_MISSING_DATA.md`](docs/ORIGIN_AND_MISSING_DATA.md) and [`docs/PHILOSOPHY.md`](docs/PHILOSOPHY.md).
What is included
Layer	Implementation
Numerical AXIOM0	Original v0.1 protected-reduction and five-coordinate GENESIS=(1,2,8,7,5) / SOUL=(5,12,5,12,5) code, kept unchanged in axiom0/numerics.py
Persistent SemiSoul	Ed25519 local identity; signed, hash-chained ledger; epistemically labeled autobiographical memories; corrections; versioned purpose and commitments; signed attestation
Municipal Truth Library	Original v0.2 versioned legal-section ingestion, content hashes, superseded-section history, quote matching, source attribution
Proof Gate	Rejects purported source quotations not present in the referenced version; quotation matching does not establish legal or factual truth
Living City intelligence	Evidence-based occurrences, hypotheses, contrary evidence, recurring-signal scans, human verification
Early warning	Area-level historical service-request spike detection from authorized CSV; not person-level prediction
3·6·9 intention practice	Optional 3 repetitions × 6 sessions/day × 9 days; tracked separately from municipal evidence
3·6·9 inquiry	3 inquiry phases, 6 evidence checks, 9 review stages; no mystical truth scoring
Local model	Ollama adapter; query-grounded document/section excerpts; strict citation-ID validation; no cloud fallback
Resilient fetcher	Opt-in feeds; HTTPS hostname allowlist; DNS public-address guard; ETag/Last-Modified; TTL cache; jitter; HTML-to-text; versioned ingestion and audit records
Three integration methods	Import Axiom0 from Python, axiom0 --json ... CLI, or loopback HTTP API
Operator UI	Local dashboard served at http://127.0.0.1:8765


3·6·9 is a reasoning discipline, not a proof function
- 3 phases: observe → challenge → provisional explanation.
- 6 checks: source provenance, timeliness, independence, corroboration, contradictions, human authority.
- 9 steps: capture → identify source → timestamp → contextualize → hypothesize → seek support → seek counterevidence → human review → reassess.
Use axiom0 inquire369 HYPOTHESIS_ID after adding occurrences and opening a hypothesis. It cannot change a hypothesis to verified. The 3·6·9 intention practice is a separate personal goal-tracking workflow and cannot influence a legal finding.
Quick start — Windows PowerShell
Requirements: Windows 10/11, Python 3.11 or newer, internet access for initial dependency installation. From the extracted project folder:
.\deploy\windows\Install-AXIOM0.ps1 -Admin howard
.\deploy\windows\Start-AXIOM0.ps1
Then open http://127.0.0.1:8765/. The installer prints a local health report and creates unique service and reviewer keys stored under axiom0_data with an attempted user-only Windows file ACL. Inspect the ACL before handling sensitive sources. PowerShell execution policy or Python launcher configuration may require ordinary local setup adjustments. Windows installer and startup have not been exercised on a real Windows host in this build environment.

If running commands manually:
py -3 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e ".[test]"
axiom0 init --admin howard
axiom0 doctor
Quick start — Linux/macOS
bash deploy/linux/install.sh
bash deploy/linux/start.sh
Or manually:
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -e '.[test]'
axiom0 init --admin howard
axiom0 doctor
The supplied Linux installer uses local-user permissions (700 data directory, 600 secrets file). Startup binds the API to 127.0.0.1 only. It does not silently install services, schedule web scrapes, or expose AXIOM0 over the internet.
1. Run AXIOM0 inside a Python program
from axiom0.core import Axiom0

ax = Axiom0('./axiom0_data')
# For a new local data directory (once):
ax.set_admin('howard')

# Ingest a correctly headed, authorized source document:
with open('examples/SIMULATED_charter.md', encoding='utf-8') as f:
    report = ax.library.ingest_text(f.read(), actor='howard')

result = ax.ask('howard', 'What does the sample charter say about public records?')
for finding in result['findings']:
    print(finding['text'], '->', finding['cite'])

# Deterministic area-level statistical flags using an example fixture:
flags = ax.warn('howard', 'examples/SIMULATED_service_requests.csv')
print(flags)
The imported sample files are fictional fixtures, not Kansas City law or live service statistics. The local Python interface enforces actor-label checks within its facade, but Python executed under the same operating-system account can still access private files or import lower-level modules. This is not an untrusted-code sandbox.
2. Use the machine-readable command line
axiom0 --json status
axiom0 --json ingest examples/SIMULATED_charter.md
axiom0 --json ask 'What does the fictional charter say about public records?'
axiom0 --json warn examples/SIMULATED_service_requests.csv
axiom0 --json queue
axiom0 --json verify
axiom0 --json doctor
From PowerShell, axiom0 --json status | ConvertFrom-Json returns a structured object. The command exits nonzero and emits a JSON error object for validation errors when --json is used. The local CLI relies on trusted computer-user/OS permissions and is not per-employee authentication.
3. Use the local web API
With the server started, pass the installer-generated service key as the X-AXIOM0-Key header. Routes include:
Route	Intent
POST /ask	Source-matched citations; optional local model draft
POST /ingest	Ingest structured legal text into versioned Truth Library
POST /warn	Analyze a named CSV staged under axiom0_data/imports/
GET /queue, POST /queue	Review-queue listing and recommendation proposals
POST /queue/review	Needs both service and distinct reviewer keys
POST /v1/inquiry369	Run symbolic structured inquiry over an existing hypothesis
GET /v1/legal/sections, POST /v1/legal/quote	Source history and quote verification
GET /v1/semisoul/profile, /memories, /attestation	SemiSoul profile, memory and signed continuity attestation
GET /v1/verify	Verify local signed event history


Example PowerShell, from a shell where the secrets have been loaded:
. .\axiom0_data\axiom0-secrets.ps1
$headers = @{ 'X-AXIOM0-Key' = $env:AXIOM0_API_KEY }
$body = @{ question = 'What does the fictional charter say about records?' } | ConvertTo-Json
Invoke-RestMethod -Method Post -Uri 'http://127.0.0.1:8765/ask' -Headers $headers -ContentType 'application/json' -Body $body
Other computers/apps: v0.6 is a localhost integration endpoint, not an internet-ready API. A Clerk Access or Chambers Desk backend running on the same trusted workstation can call it through a server-side integration, but browser clients must not be given permanent service secrets. Cross-device access awaits a reverse proxy with approved SSO/OIDC, real staff identities and roles, TLS, audit integration, rate limits, origin restrictions, and security review.
Optional local Ollama
1. Install Ollama independently and pull an instruction model supported by your computer, e.g. ollama pull llama3.2:3b.
2. Leave it bound to localhost at http://127.0.0.1:11434.
3. Import authorized sources first.
4. Run axiom0 ask 'What is the sample policy?' --llm.
If the model is missing, the command reports a local model error. There is no external model fallback. The LLM can generate a draft with validated source IDs, but there is no general semantic-entailment guarantee that each sentence follows from its citations. That requires a separate review process.
Opt-in resilient feed monitoring
No sources are auto-scraped or bundled as official law. To monitor an official or authorized HTTPS source, register its exact hostname (DNS and private-network checks occur at fetch time):
axiom0 feed-add city-policy https://example.com/policy demo-policy --authority policy --title 'DEMO NOT OFFICIAL'
axiom0 --json fetch-once city-policy
axiom0 --json feed-list
axiom0 fetch-loop --hours 6
example.com above is only a syntax example. Register a real authorized source only after confirming ownership, permission, applicability, and acceptable scraping rules. Prefer official feeds/APIs where possible. The fetcher supports conditional HTTP checks and TTL: no download occurs during the locally configured freshness window; after the window, a conditional request may return 304 Not Modified. A content hash alone cannot prevent the initial request.

The optional headless browser is disabled unless a feed is explicitly registered using --render; install its extra requirements with pip install -e '.[render]' and playwright install chromium. JavaScript rendering and hostile-site defenses require further testing before production use. Do not run multiple overlapping feed-loop processes. For unattended operation, configure one Windows Task Scheduler job or cron/systemd timer under a restricted user after local validation.
SemiSoul: inspect, correct, and attest
from axiom0.core import Axiom0
from axiom0.semisoul import SemiSoul
ax = Axiom0('./axiom0_data')
ax.semisoul.remember(statement='Research result needs an independent check',
    memory_type='reflection', epistemic_status='uncertain',
    source_type='operator', actor='howard')
attestation = ax.semisoul.attest()
assert SemiSoul.verify_attestation(attestation)
SemiSoul memories carry attribution and epistemic labels; corrections add signrecords referencing earlier entries. The model can be replaced without resetting identity. axiom0 verify checks both the signed ledger and SemiSoul memory/profile histories. The private identity key must be backed up securely with its database and never shared.
Deployment and assurance limits
A local pilot can be deployed from this package after the listed installation steps. This build has automated tests for the software API and data/ledger pathways, but has not been validated against live municipal infrastructure, real Windows hardware, production identity providers, or a deployed model on target hardware.

Do not operate as a City enforcement system or process restricted records until the data owner authorizes the use. A municipal production decision requires penetration testing, threat modeling, data classification, legal review, signed off access controls, independent audit witnessing, backups/restores, WCAG accessibility testing, incident response, and an identity provider with human-specific authentication. HTTPS URL allowlisting is not complete SSRF mitigation, and a locally signed ledger can be rolled back in tandem with its signing key by someone who controls the whole host.

Read [`docs/DEPLOYMENT.md`](docs/DEPLOYMENT.md), [`docs/SECURITY.md`](docs/SECURITY.md), and [`docs/PHILOSOPHY.md`](docs/PHILOSOPHY.md) before using real sources.
Package lineage
This build combines the recovered v0.1 AXIOM0 numerical specification and Python code; the original v0.2 Municipal Intelligence Core (preserved under reference/axiom0-v0.2-original.zip); v0.3 occurrence intelligence; v0.4 intention practice; and v0.5 SemiSoul and municipal-source libraries. It is not a complete implementation of earlier Ezmerelda hardware, remote witnessing or production authorization components.

Licensing: no general-purpose redistribution license is granted here. Review intellectual-property rights, third-party dependencies, and data licenses before distribution or commercial licensing.
