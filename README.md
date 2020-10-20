# Particl.wiki

Hugo-based knowledge base for @particl Project


## Development

1. Clone repo
2. Install [Hugo](gohugo.io)
3. To run Hugo dev server: `hugo server -D`
4. To compile assets: `gulp` (one-time) or `gulp devel` (continuous)
5. To check production version locally: `hugo` and then check the result in `/public` folder


## Formatting

- Table of Contents: `{{< toc >}}`
- Tree ToC (list all child pages with hierarchy): `{{< tree-toc >}}`
- Buttons
  - Internal: `{{< button relref="/" [class="..."] >}}Text{{< /button >}}`
  - External: `{{< button href="/" [class="..."] >}}Text{{< /button >}}`
- Icons: `{{< ico NAME >}}` - names correspond to icon file names in `/static/media/icons/`, e.g. `{{< ico yes >}}`
- Youtube: `{{< youtube PRxmGh24ILU >}}` (`PRxmGh24ILU` stands for video ID found in it's URL)
- Vimeo: `{{< vimeo 330290302 >}}` (`330290302` stands for video ID found in it's URL)
- Labels: `<label type="primary|warning|alert|info">Label</label>`

### Tables

```markdown
| head | head |
| ---- | ---- |
| data | data |
| data | data |
```

### Hints/Callouts

```go
{{< hint [info|warning|alert] >}}
**Markdown content**\
Dolor sit, sumo unique argument um no. Gracie nominal id xiv. Romanesque acclimates investiture.
 Ornateness bland it ex enc, est yeti am bongo detract re.
{{< /hint >}}
```

### Images & video

To include static media, either put them in `/static` folder first (only applies for global site assets) OR create a [page bundle](https://gohugo.io/content-management/page-bundles/) (in short: convert `.md` file to folder of the same name + it's content into `index.md` + put all assets to be inluded in the same folder - you can then reference them relatively to the `index.md` file).

```
{{< image src="image.png" class="side-thumb" [alt="desc"] [caption="caption"] >}}

{{< video webm="video.webm" mp4="video.mp4" [alt="desc"] [caption="caption"] >}}
```

### List tagged articles

To get a list of articles tagged with e.g. "important" use:

```
{{< list-articles important >}}
```

### Columns

```
{{< columns >}}
  # first column
<--->
  # second column
{{< /columns >}}
```

### Tabs

```go
{{< tabs "uniqueid" >}}
{{< tab "Windows" >}} # Windows Content {{< /tab >}}
{{< tab "macOS" >}} # macOS Content {{< /tab >}}
{{< tab "Linux" >}} # Linux Content {{< /tab >}}
{{< /tabs >}}
```


## Notes

### Menus

Menus are defined in `data/menu/main.yml` and `../more.yml`

### TODO

- [ ] <label> shortcode
- [ ] image galleries/lightboxes (Learn > Privacy > TX types)
- [ ] fix taxonomy pages (tag lists)
- [x] link to missing/unfinished pages in footer (http://localhost:1313/tags/TODO/)
- [ ] highlight ★ important pages (w/ "important" tag) in lists - bold? star icon?
  - batch-replace `{{fa>star}}` with `★`

Moved pages:

- learn:transaction-types -> learn/privacy/transaction-types
- learn:staking: -> learn/staking/intro
- learn:wallets: -> learn/wallets/overview
- learn:hardware-wallets -> learn/wallets/hardware
- learn:market: -> learn/marketplace/overview

- tutorial:particl-desktop: -> tutorial/wallets/particl-desktop
  + same for core, copay, cli
- tutorial:ledger/trezor -> tutorial/wallets/ledger (trezor)
- tutorial:market: -> tutorial/market/intro
- tutorial:backup-restore-wallet -> tutorial/security/backup-restore-wallet
- tutorial:staking: -> tutorial/staking/intro
- tutorial:multisig -> tutorial/security/multisig
- tutorial:good-password -> tutorial/security/good-password
- tutorial:privacy-tips -> tutorial/privacy/tips
- tutorial:coin-control -> tutorial/privacy/coin-control
- tutorial:staking: -> tutorial/staking/overview
- tutorial:market: -> tutorial/market/intro
- tutorial:market:* -> tutorial/marketplace/*intro*
- tutorial:passphrase-security -> tutorial/security/recovery-phrase
- tutorial:verify-downloads -> tutorial/security/verify-downloads
- tutorial:good-passwprd -> tutorial/security/good-passwords

- support: -> support/overview

- dev: particl-desktop/particl-core:/trezor/ledger -> dev/wallets/*
- dev: rpc-api/insight-api/coingecko-api/coinmarketcap-api/chainz-api -> dev/api/ rpc/insight/coingecko/coinmarketcap/chainz

## Credits

Based on [@xoxys/hugo-geekdoc](https://github.com/xoxys/hugo-geekdoc)