# HCF (hcf)

HCF — The Hospitals Contribution Fund of Australia Limited (ABN 68 000 026 746, AFSL 241 414), founded in 1932 and headquartered in Sydney — is Australia's largest not-for-profit health fund, covering over 2 million members. It underwrites private health insurance (hospital, extras and ambulance cover) and Overseas Visitors Health Cover, and distributes life and Recover Cover products (life protect, income protect, critical illness), travel, pet, home, car and landlord insurance, plus the Flip accidental-injury brand, alongside its own HCF dental and eyecare centres and the HCF Research Foundation.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/hcf/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/hcf/refs/heads/main/apis.yml)

## Tags

- Insurance
- Australia
- Health Insurance
- Life Insurance
- Travel Insurance
- Pet Insurance
- Carrier
- Not-for-Profit
- Claims
- Member Services
- Partner Gated
- No Public API

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

**None.** HCF publishes no public, self-serve API and no developer portal, and this profile records that honestly rather than inventing a surface to fill the record.

As of the 2026-07-25 review:

- `developer.hcf.com.au`, `developers.hcf.com.au` and `docs.hcf.com.au` do not resolve.
- `/developers`, `/developer`, `/developer-portal`, `/apis`, `/docs`, `/partners`, `/integrations`, `/open-data` and `/innovation` on `www.hcf.com.au` all return **404**.
- `api.hcf.com.au` resolves but redirects to `https://corporate.hcf.com.au/api`, which is an incidentally-exposed Adobe Experience Manager content-services endpoint serving Siren hypermedia for the marketing site. It is undocumented, has no insurance semantics, and is not counted as an API.
- No OpenAPI, Swagger, AsyncAPI, GraphQL SDL, `.proto` or public Postman collection exists on any HCF-controlled host. Every spec candidate returned 404.

### ACORD posture

**No ACORD reference found.** Scans of `www.hcf.com.au` returned zero hits for ACORD, AL3, ACORD XML, NGDS or IVANS. This is structurally expected: ACORD standards govern property & casualty and life/annuity exchange, whereas Australian private health insurance runs on a separate national rail set.

### The real integration seams

HCF consumes integration rails rather than publishing them:

- **Point-of-service claiming** at extras providers over third-party HICAPS VX, HICAPS Trinity and CommBank Smart Health payment terminals.
- **Medical gap claims** requiring a Medicare Benefit Statement obtained from Medicare before submission to HCF.
- **Member self-service** through the My Membership app and online member services, behind an Okta-backed sign-in.

### Quote / bind / issue / FNOL

None of the four insurance verbs are exposed as an API. Quote and join are consumer HTML funnels; `/healthinsurance/join/` is explicitly disallowed in `robots.txt`. Claims (FNOL) go through the terminals, the app, or a branch.

### Auth model

OAuth2 / OIDC authorization-code via **Okta** at `https://id.hcf.com.au` (Okta Sign-In Widget 6.8.1), for **member sign-in only**. The OIDC discovery document is publicly readable and advertises stock Okta org-management and standard OIDC scopes — it describes the identity tenant, not an HCF product API. There is no third-party client registration, no API key issuance, and no published scope catalog for any HCF business API.

### Market context

Australia has the legal machinery for open insurance and no live obligation. APRA supervises prudentially, and the Consumer Data Right that opened banking and energy was designated to extend to general insurance and then deferred and de-prioritised — so the CDR seam that made Australian banking legible stops before insurance. Private health insurance is a separately regulated market with its own data flows and was never in CDR scope. With no forcing function, HCF has no external pressure to publish an API, and it has not.

## Links

- **Website:** [https://www.hcf.com.au/](https://www.hcf.com.au/)
- **About:** [https://www.hcf.com.au/about-us](https://www.hcf.com.au/about-us)
- **Contact:** [https://www.hcf.com.au/contact-us](https://www.hcf.com.au/contact-us)
- **Privacy Policy:** [https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/policies/privacy-policy](https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/policies/privacy-policy)
- **Terms and Conditions:** [https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/policies/terms-and-conditions](https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/policies/terms-and-conditions)
- **Trust Centre:** [https://www.hcf.com.au/about-hcf/privacy-information-trust-centre](https://www.hcf.com.au/about-hcf/privacy-information-trust-centre)
- **Blog (Health Agenda):** [https://www.hcf.com.au/health-agenda](https://www.hcf.com.au/health-agenda)
- **Media Centre:** [https://www.hcf.com.au/about-us/media-centre](https://www.hcf.com.au/about-us/media-centre)
- **Annual Report:** [https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/annual-report](https://www.hcf.com.au/about-us/about-HCF/governance-and-structure/annual-report)
- **Member Login:** [https://www.hcf.com.au/member-login](https://www.hcf.com.au/member-login)
- **OpenID Configuration:** [https://id.hcf.com.au/.well-known/openid-configuration](https://id.hcf.com.au/.well-known/openid-configuration)

## Review

See [review.yml](review.yml) for the full 2026-07-25 API Evangelist review, including every probed URL with its HTTP status.
