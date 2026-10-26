# Sonix (sonix)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Sonix is an AI-powered platform for automated audio and video transcription, subtitles, and translation. It transcribes in 54+ languages with speaker labels and word-level timestamps, translates transcripts into 55+ languages, generates subtitles and captions (SRT, VTT, TXT, JSON, DOCX, PDF), and runs AI analysis (summaries, chapters, sentiment, entities). The Sonix REST API - available to subscribers - lets developers upload media, poll transcription status, retrieve and edit transcripts, export subtitles, and translate, all authorized with a Bearer API key against `https://api.sonix.ai/v1`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sonix/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sonix/refs/heads/main/apis.yml)

## Access Model

The Sonix API is public and documented at [https://sonix.ai/docs/api](https://sonix.ai/docs/api), but it requires a Sonix account to obtain credentials. API access is included on every paid plan - Pay As You Go ($10/hr) and the Core, Advanced, and Pro subscriptions. Subscribers retrieve their API key at `https://my.sonix.ai/api`; trial accounts (which include a small amount of free transcription) can request a key from Sonix support. All requests are authorized with `Authorization: Bearer <API Key>`. The current API version is `v1`.

Transcription is asynchronous: you upload media, then either poll the media/transcript resource for status (preparing → transcribing → aligning → completed) or receive an HTTP webhook at an optional `callback_url` when transcription finishes. Sonix markets a real-time streaming transcription option, but it is gated behind a sales conversation and is not publicly documented, so it is not modeled here.

## Tags

- Audio Transcription
- Transcription
- Speech-to-Text
- Subtitles
- Captions
- Translation
- AI
- Media

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Sonix Media & Transcription API

Upload audio and video media - by multipart file (up to 100MB) or `file_url` - for automated speech-to-text transcription in 54+ languages, then list, retrieve, update, and delete media and poll transcription status. An optional `callback_url` delivers a webhook when transcription finishes.

- **Human URL:** [https://sonix.ai/docs/api](https://sonix.ai/docs/api)
- **Base URL:** `https://api.sonix.ai/v1`

#### Tags

- Audio Transcription
- Speech-to-Text
- Media Upload

#### Properties

- [Documentation](https://sonix.ai/docs/api)
- [API Reference](https://sonix.ai/api)
- [OpenAPI](openapi/sonix-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sonix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sonix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sonix Transcripts API

Retrieve a media file's transcript as plain text or as JSON with word-level timings, speaker labels, and confidence scores, and edit transcript content programmatically after transcription completes.

- **Human URL:** [https://sonix.ai/docs/api](https://sonix.ai/docs/api)
- **Base URL:** `https://api.sonix.ai/v1`

#### Tags

- Transcription
- Transcripts
- Word Timestamps

#### Properties

- [Documentation](https://sonix.ai/docs/api)
- [OpenAPI](openapi/sonix-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sonix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sonix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sonix Translations API

Translate a completed transcript into any of 55+ target languages and poll the translation status per target language, enabling multilingual transcripts and subtitles from a single source media file.

- **Human URL:** [https://sonix.ai/docs/api](https://sonix.ai/docs/api)
- **Base URL:** `https://api.sonix.ai/v1`

#### Tags

- Translation
- Transcription
- Localization

#### Properties

- [Documentation](https://sonix.ai/docs/api)
- [OpenAPI](openapi/sonix-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sonix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sonix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sonix Exports & Subtitles API

Export transcripts as SRT and VTT subtitles, JSON, and other formats, split transcripts into subtitle segments by characters-per-line and lines-per-subtitle, burn subtitles into video, and export source media as mp3, wav, or mp4.

- **Human URL:** [https://sonix.ai/docs/api](https://sonix.ai/docs/api)
- **Base URL:** `https://api.sonix.ai/v1`

#### Tags

- Subtitles
- Captions
- Exports

#### Properties

- [Documentation](https://sonix.ai/docs/api)
- [OpenAPI](openapi/sonix-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sonix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sonix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sonix AI Analysis API

Run AI analysis over a transcript to generate summaries, chapters, sentiment analysis, and entity extraction, and retrieve or batch these summarization jobs across a folder of media.

- **Human URL:** [https://sonix.ai/docs/api](https://sonix.ai/docs/api)
- **Base URL:** `https://api.sonix.ai/v1`

#### Tags

- AI
- Summarization
- Sentiment

#### Properties

- [Documentation](https://sonix.ai/docs/api)
- [OpenAPI](openapi/sonix-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sonix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sonix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Authentication](authentication/sonix-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/sonix-ai)
- [Website](https://sonix.ai)
- [Documentation](https://sonix.ai/docs/api)
- [Plans](plans/sonix-plans-pricing.yml)
- [Rate Limits](rate-limits/sonix-rate-limits.yml)
- [Fin Ops](finops/sonix-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

---

> Note: The OpenAPI, Postman, and Open Collection artifacts were modeled by API Evangelist from Sonix's public API documentation ([https://sonix.ai/docs/api](https://sonix.ai/docs/api)). Endpoint paths, the base URL, Bearer authentication, and media/transcript status values are grounded in the public docs; individual request/response field schemas are honestly modeled where the docs do not enumerate every field.
