# Hugolify theme icons: Tabler

The [Tabler](https://tabler.io/icons) outline icons (5500+) for
[hugolify-theme-icons](https://github.com/hugolify/hugolify-theme-icons). Tabler
draws on the same grid as Lucide (24x24, 2px stroke, round caps and joins), and
covers subjects Lucide doesn't, such as trades and building work.

## Install

```yaml
# config/_default/module.yaml
imports:
  - path: github.com/hugolify/hugolify-theme-icons
  - path: github.com/hugolify/hugolify-theme-icons-tabler
```

Requires hugolify-theme-icons v1.7.0 or later.

## Usage

### As a complement (default)

Importing the module changes nothing on the site: Lucide stays the default set,
and Tabler icons are reached with their prefix.

```go-html-template
{{ partial "icon" "tabler:ladder" }}
{{ partial "icon" "solid:tabler:star" }}
```

In content: `{{< icon icon="tabler:trowel" >}}`, or `icon: tabler:crane` in a block.

### As the default set

To draw the names written without a prefix with Tabler, the site sets it as the
default. The icons the Hugolify themes call themselves (video play and pause,
vCard, map pin, rating stars) then switch to Tabler too.

```yaml
# config/_default/params.yaml
icons:
  set: tabler
```

Content then uses Tabler names: `photo`, `currency-euro`, `school` (Lucide's
`image`, `euro`, `graduation-cap`). Switching an existing site is a content
migration: names differ between the two sets.

The module ships three aliases in `assets/icons/tabler/`, for names the themes
call and Tabler draws under other names:

| Name the themes call | Tabler icon |
| --- | --- |
| `play` | `player-play` |
| `pause` | `player-pause` |
| `contact-round` | `user-square-rounded` |

## Trades and building work

Icons Lucide lacks, among others: `ladder`, `trowel`, `wall`, `bulldozer`,
`backhoe`, `crane`, `hammer-drill`, `air-conditioning`, `car-garage`,
`car-lifter`, `vacuum-cleaner`, `ironing`, `stairs`, `ruler-measure`, `tools`,
`paint`. Neither set has a tradesperson pictogram ("plumber"), and Tabler has no
faucet; for plumbing, Lucide's own `wrench`, `shower-head`, `toilet` or `heater`
remain available, and `faucet` on a site whose Lucide is from 2026-09-14 or later.

Lucide and Tabler share a grid but not every proportion: use Tabler for a whole
group (a list of trades), rather than alternating the two sets in one row.

## Tabler version

This module requires `github.com/tabler/tabler-icons` v3.53.0. Tabler tags its
releases, but ships no `go.mod`: Go names them `v3.x.y+incompatible`. A site moves
to a newer release on its own:

```sh
hugo mod get -u github.com/tabler/tabler-icons
```

## Documentations

- [Tabler icons](https://tabler.io/icons)
- [hugolify-theme-icons](https://github.com/hugolify/hugolify-theme-icons)
- [Hugolify](https://www.hugolify.io/docs/)

## Licensing

Hugolify is free for personal or commercial projects (MIT license). Tabler Icons
are licensed under the [MIT license](https://github.com/tabler/tabler-icons/blob/main/LICENSE),
© Paweł Kuna; the three aliases are copies of Tabler icons under that license.
