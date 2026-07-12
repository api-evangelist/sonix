# Sonix (sonix)

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
