# jyotisha-posts

Auto-captured Jyotiṣa / Vedic astrology posts from [@VEDANJANAM](https://x.com/VEDANJANAM), each stored with a short take in my own voice.

## Layout

- `posts/YYYY-MM-DD.json` — one file per day, dated in Asia/Kuala_Lumpur
- `seen.json` — `last_id` (newest captured post id) and `ids` (every post already stored)
- `voice.md` — voice notes used when writing `my_take`

## JSON schema

Each daily file is an object:

| Field | Meaning |
| --- | --- |
| `source` | Account the posts were taken from |
| `date` | Calendar date in Asia/Kuala_Lumpur (`YYYY-MM-DD`) |
| `topic` | Filter applied when capturing |
| `count` | Number of posts in the file |
| `posts` | Array of post objects |

Each entry in `posts` keeps the original fields from X (`id`, `url`, `author`, `created_at`, `created_at_local`, `text`, `public_metrics`, `quoted_post`) and adds:

| Field | Meaning |
| --- | --- |
| `my_take` | 1–3 sentences in my voice, reacting to the point (agreement, a question, how I would apply it, or what is new). Not a claim about my own chart. |
| `captured_at` | ISO 8601 timestamp when the post was stored |
| `zernio_draft_id` | Zernio draft id for the take saved to the @VikkneshwaranR X account, or `null` if draft creation failed |

`quoted_post` is the post being quoted, when X returned it (`id`, `url`, `author`, `text`). Some early-day quotes may have a null author or text if the original was not available at capture time.
