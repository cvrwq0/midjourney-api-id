# Midjourney API (`midjourney`)

<!-- conv-kit:v1 -->

<p align="center">
  <img src="assets/badges/price.svg" alt="observed unit price"> <img src="assets/badges/billing.svg" alt="billing model"> <img src="assets/badges/compat.svg" alt="OpenAI-compatible endpoint">
</p>

<p align="center">
  <img src="assets/01-product-hero-perfume.jpg" width="820" alt="Sample render via the APIMart image API">
</p>

> **from $0.045 per image** on the APIMart route — satu endpoint yang kompatibel dengan OpenAI di `https://api.apimart.ai/v1`, tanpa paket bulanan. *(diamati 2026-10-12)*

**[Dapatkan API key](https://go.apimart.ai/k-02a612)** · **[Harga live](https://go.apimart.ai/k-0e1de8)** · **[Halaman model](https://go.apimart.ai/k-2a3c5e)** · [⚡ Quickstart 60 detik](#quickstart)

**Alasan tim memakai Midjourney (`midjourney`) lewat APIMart**

- **Satu key untuk seluruh katalog.** base URL `https://api.apimart.ai/v1` dan header `Authorization` yang sama menjangkau Midjourney (`midjourney`) plus 300+ model gambar, video, dan bahasa lainnya — cukup ganti field `model`, bukan klien Anda.
- **Minimum $1, bayar sesuai pemakaian.** Tanpa langganan dan tanpa paket prabayar yang harus dihitung di awal: isi saldo mulai $1 dan pakai untuk panggilan.
- **Biaya dikembalikan di respons.** Setiap task yang selesai melaporkan jumlah yang ditagih (`cost` / `credits_cost`); task berstatus `failed` dikembalikan dananya.
- **Asinkron sejak awal.** Kirim, ambil `task_id`, polling `GET /v1/tasks/{id}` — batching dan retry hanyalah pekerjaan antrean biasa, bukan integrasi khusus.

<!-- /conv-kit:v1 -->



Midjourney is the industry-leading text-to-image engine, prized for its painterly aesthetic, strong composition, and signature lighting. APIMart exposes Midjourney as a programmable API — call /v1/midjourney/generations for the default Imagine flow, choose v8.1, v7, v6.1, v5.2, v5.1 or Niji 7 / Niji 6, dial in stylize / chaos / weird, and run on relax, fast, or turbo queues without touching Discord.

## Model id and routes

| Route | `model` value | Billing | Notes |
| --- | --- | --- | --- |
| Per-image | `midjourney` | per delivered image, by resolution | see the [model page](https://go.apimart.ai/k-2a3c5e) for the exact tiers |

Endpoint: `POST https://api.apimart.ai/v1/images/generations`, then poll `GET /v1/tasks/{task_id}`.

## Pricing

<!-- pricing:model:start -->
| Output | List price | Effective price |
| --- | --- | --- |
| default | 0.0563 | 0.04504 |
| blend | 0.0688 | 0.05504 |
| blend-fast | 0.0688 | 0.05504 |
| blend-turbo | 0.125 | 0.1 |
| describe | 0.0688 | 0.05504 |
| describe-fast | 0.0688 | 0.05504 |
| describe-turbo | 0.125 | 0.1 |
| edits | 0.0688 | 0.05504 |
| edits-fast | 0.0688 | 0.05504 |
| edits-turbo | 0.125 | 0.1 |
| high_variation | 0.0688 | 0.05504 |
| high_variation-fast | 0.0688 | 0.05504 |
| high_variation-turbo | 0.125 | 0.1 |
| imagine | 0.0563 | 0.04504 |
| imagine-fast | 0.0688 | 0.05504 |
| imagine-niji6 | 0.0563 | 0.04504 |
| imagine-niji6-fast | 0.0688 | 0.05504 |
| imagine-niji6-turbo | 0.125 | 0.1 |
| imagine-niji7 | 0.0563 | 0.04504 |
| imagine-niji7-fast | 0.0688 | 0.05504 |
| imagine-niji7-turbo | 0.125 | 0.1 |
| imagine-turbo | 0.125 | 0.1 |
| imagine-v5.1 | 0.0563 | 0.04504 |
| imagine-v5.1-fast | 0.0688 | 0.05504 |
| imagine-v5.1-turbo | 0.125 | 0.1 |
| imagine-v5.2 | 0.0563 | 0.04504 |
| imagine-v5.2-fast | 0.0688 | 0.05504 |
| imagine-v5.2-turbo | 0.125 | 0.1 |
| imagine-v6.1 | 0.0563 | 0.04504 |
| imagine-v6.1-fast | 0.0688 | 0.05504 |
| imagine-v6.1-turbo | 0.125 | 0.1 |
| imagine-v7 | 0.0563 | 0.04504 |
| imagine-v7-fast | 0.0688 | 0.05504 |
| imagine-v7-turbo | 0.125 | 0.1 |
| imagine-v8.1 | 0.0563 | 0.04504 |
| imagine-v8.1-fast | 0.0688 | 0.05504 |
| imagine-v8.1-turbo | 0.125 | 0.1 |
| imagine-v8.2 | 0.0563 | 0.04504 |
| imagine-v8.2-fast | 0.0688 | 0.05504 |
| imagine-v8.2-turbo | 0.125 | 0.1 |
| inpaint | 0.0688 | 0.05504 |
| inpaint-fast | 0.0688 | 0.05504 |
| inpaint-turbo | 0.125 | 0.1 |
| low_variation | 0.0688 | 0.05504 |
| low_variation-fast | 0.0688 | 0.05504 |
| low_variation-turbo | 0.125 | 0.1 |
| modal | 0.0688 | 0.05504 |
| modal-fast | 0.0688 | 0.05504 |
| modal-turbo | 0.125 | 0.1 |
| pan | 0.0688 | 0.05504 |
| pan-fast | 0.0688 | 0.05504 |
| pan-turbo | 0.125 | 0.1 |
| remix_strong | 0.0688 | 0.05504 |
| remix_strong-fast | 0.0688 | 0.05504 |
| remix_strong-turbo | 0.125 | 0.1 |
| remix_subtle | 0.0688 | 0.05504 |
| remix_subtle-fast | 0.0688 | 0.05504 |
| remix_subtle-turbo | 0.125 | 0.1 |
| reroll | 0.0688 | 0.05504 |
| reroll-fast | 0.0688 | 0.05504 |
| reroll-turbo | 0.125 | 0.1 |
| shorten | 0.0688 | 0.05504 |
| shorten-fast | 0.0688 | 0.05504 |
| shorten-turbo | 0.125 | 0.1 |
| upscale-hd | 0.0688 | 0.05504 |
| upscale-hd-fast | 0.0688 | 0.05504 |
| upscale-hd-turbo | 0.125 | 0.1 |
| variation | 0.0688 | 0.05504 |
| variation-fast | 0.0688 | 0.05504 |
| variation-turbo | 0.125 | 0.1 |
| video | 0.25 | 0.2 |
| video-720p | 0.5 | 0.4 |
| zoom | 0.0688 | 0.05504 |
| zoom-fast | 0.0688 | 0.05504 |
| zoom-turbo | 0.125 | 0.1 |


<!-- pricing:model:end -->

Prices are a snapshot; the [pricing page](https://go.apimart.ai/k-0e1de8) and [`data/model.json`](data/model.json) are refreshed by CI, and a completed task reports the exact amount in its `cost` field.

## Request parameters

| Field | Type | Default | Notes |
| --- | --- | --- | --- |
| `model` | string | required | the model id shown in the route table above |
| `prompt` | string | required | what to generate, or what to change when editing |
| `size` | string | `auto` / `1:1` | aspect ratio, or `auto` where the route supports it |
| `resolution` | string | `1K` | output resolution tier — cost scales with it |
| `n` | integer | `1` | number of images per task, where the route allows more than one |
| `image_urls` | string[] | — | reference images as public HTTP(S) URLs or base64 data URLs |
| `nsfw_check` | boolean | `false` | runs `omni-moderation-latest` before submitting |

The table lists the fields accepted by the APIMart `images/generations` endpoint. Check the [model page](https://go.apimart.ai/k-2a3c5e) for anything this model adds on top.

## Quickstart

```bash
curl --request POST --url https://api.apimart.ai/v1/images/generations \
  --header "Authorization: Bearer $APIMART_API_KEY" --header 'Content-Type: application/json' \
  -d '{"model":"midjourney","prompt":"A bamboo forest at sunrise, slow push-in","size":"1:1","resolution":"1K"}'
```

```python
import os, time, requests

BASE = "https://api.apimart.ai/v1"
HEADERS = {"Authorization": f"Bearer {os.environ['APIMART_API_KEY']}", "Content-Type": "application/json"}

created = requests.post(f"{BASE}/images/generations", headers=HEADERS, timeout=60, json={
    "model": "midjourney", "prompt": "A bamboo forest at sunrise, slow push-in",
}).json()
task_id = created["data"]["id"]

while True:
    task = requests.get(f"{BASE}/tasks/{task_id}", headers=HEADERS, timeout=60).json()["data"]
    if task["status"] in ("completed", "failed"):
        break
    time.sleep(5)
print(task.get("cost"), task["result"]["images"][0]["url"])
```

Runnable versions: [`examples/`](examples). The task lifecycle is `pending → processing → completed | failed`.

## FAQ

**Apa id model Midjourney?**

`midjourney`. Lihat tabel rute di atas.

**Bagaimana penagihannya?**

**from $0.045 per image** on the APIMart route. Task yang selesai melaporkan jumlah tepatnya di field `cost`; task yang gagal dikembalikan dananya.

**How do I get a key?**

Use the [Get an API key](https://go.apimart.ai/k-02a612) link — $1 minimum top-up, no plan required.

<!-- related-repos:auto -->
## Related repositories

- **Same model, this language** — the other half of this pair: [midjourney-prompts-id](https://github.com/cvrwq0/midjourney-prompts-id)
- **Same model, other languages** — 9 more language builds: 中文 [midjourney-api-cn](https://github.com/apimartycl6k972t/midjourney-api-cn) · Deutsch [midjourney-api-de](https://github.com/h5fd0cofy/midjourney-api-de) · Español [midjourney-api-es](https://github.com/xbuu0/midjourney-api-es) · Français [midjourney-api-fr](https://github.com/apimartt1q/midjourney-api-fr) · Relay/gateway [midjourney-api-gateway](https://github.com/apimartxc3iskw/midjourney-api-gateway) · 日本語 [midjourney-api-ja](https://github.com/apimartt1q/midjourney-api-ja) · 한국어 [midjourney-api-ko](https://github.com/ocvewn2-9ueo/midjourney-api-ko) · Português [midjourney-api-pt](https://github.com/l-ca0/midjourney-api-pt) · Русский [midjourney-api-ru](https://github.com/sfpxvicw/midjourney-api-ru)
- **More models in this language** — [gemini-2-5-flash-image-preview-api-id](https://github.com/gmrg0s/gemini-2-5-flash-image-preview-api-id) · [nano-banana-api-id](https://github.com/vsa185x9ecrd/nano-banana-api-id) · [gemini-3-1-flash-image-preview-api-id](https://github.com/p61qrgpg/gemini-3-1-flash-image-preview-api-id) · [nano-banana-2-api-id](https://github.com/n1rf4ezzz/nano-banana-2-api-id) · [gemini-3-pro-image-preview-api-id](https://github.com/s78ve5v4x9ji2/gemini-3-pro-image-preview-api-id) · [nano-banana-pro-api-id](https://github.com/qn7wpqwsvs/nano-banana-pro-api-id)
- **Topic hubs** — every build of this model, all languages: [midjourney](https://github.com/topics/midjourney) · [midjourney-api](https://github.com/topics/midjourney-api)

This repository is one build in a cross-linked set of API guides for the same model family; each language build links back to the others.
<!-- /related-repos:auto -->

## Attributed links (how this repository is measured)

| Purpose | Attributed link | Target |
| --- | --- | --- |
| Model page | <https://go.apimart.ai/k-2a3c5e> | `apimart.ai/id/model/midjourney` |
| Live pricing | <https://go.apimart.ai/k-0e1de8> | `apimart.ai/id/pricing` |
| Get an API key | <https://go.apimart.ai/k-02a612> | `apimart.ai/id/keys` |

Outbound APIMart links are minted through the promo link API; hand-made tracking parameters are rejected by
`tools/check_links.py` in CI.

## Disclosure

Midjourney is a third-party model served through APIMart; this repository documents how to call it and publishes
model ids and prices, and does not claim official status. Model names, prices and documentation belong to their
respective owners.

## License

MIT — see [LICENSE](LICENSE).
