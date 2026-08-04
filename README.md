# HCF (hcf)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
