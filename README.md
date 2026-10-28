# Crypto card fees and RedotPay country lists (open data)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23722747.svg)](https://doi.org/10.5281/zenodo.23722747)

Two small datasets maintained by [CryptoCard Insider](https://cryptocardinsider.com), an independent comparison site for crypto debit cards. Each value comes from the issuer's own help center or product page, and every record carries the date it was last checked.

Both datasets are snapshots, not live feeds. Card fees and country lists change, and the issuer's app or checkout is always the final word.

## Files

| File | What it contains | Snapshot |
|---|---|---|
| `data/crypto-card-fees-2026-q3.json` / `.csv` | Issuance fees, FX fee and ATM fees for 11 crypto debit cards (RedotPay, Binance, Ether.fi, Kast, Bitget, Nexo, MetaMask, OKX, Crypto.com, BKJ, DPT) | 2026-Q3, generated 2026-10-27 |
| `data/redotpay-country-lists-20261022.json` / `.csv` | The 51 countries and regions named on any of RedotPay's four restriction lists, with one column per list | Read 2026-10-22 |

The JSON files are the source of truth. The CSV files are flattened copies for spreadsheets.

## Card fees: fields

| Field | Meaning |
|---|---|
| `id`, `brand`, `name` | Card identifier and names |
| `lastVerified` | Date the values were last checked against the issuer's source |
| `evidenceLevel` | Where the values come from, e.g. `L2-official-help-center` or `L2-official-product-page` |
| `virtual`, `physical` | Issuance fee for the virtual and physical card |
| `fx` | Fee on spending in a currency other than the card's own |
| `atm` | ATM withdrawal fees and limits |
| `factUrl` | Page on cryptocardinsider.com with the sources for that card |

Some cards are only issued in certain regions, and some values apply to one regional card only. The text says so where it matters (for example the Binance entry refers to the Brazil card).

## RedotPay country lists: fields

RedotPay's help center publishes four separate lists, and they don't match each other. This dataset puts them side by side.

| CSV column | JSON key | Source article (help center) | Article date |
|---|---|---|---|
| `listed_unsupported_for_verification` | `account` | [Unsupported Countries/Regions](https://helpcenter.redotpay.com/en/articles/10339263-unsupported-countries-regions) | 2026-08-28 |
| `listed_card_issuance_restricted` | `issuance` | [Card Issuance Restrictions](https://helpcenter.redotpay.com/en/articles/14254838-card-issuance-restrictions) | 2026-08-28 |
| `listed_card_delivery_restricted` | `delivery` | [Card Delivery Restrictions](https://helpcenter.redotpay.com/en/articles/14255319-card-delivery-restrictions) | 2026-07-21 |
| `listed_app_access_restricted` | `access` | [Location-Based Access Restrictions](https://helpcenter.redotpay.com/en/articles/14252906-location-based-access-restrictions) | 2026-08-28 |

`true` means the country is named on that list. A country that is missing from all four lists is not confirmed as supported, by this dataset or by RedotPay. Only the app can confirm that. Country names follow the help center's wording.

There's an interactive country checker built on the same data here: [Where RedotPay works](https://cryptocardinsider.com/content/guide-redotpay-available-countries-20261022).

## How to cite

Archived on Zenodo with a DOI: [10.5281/zenodo.23722747](https://doi.org/10.5281/zenodo.23722747) (always resolves to the latest version).

> CryptoCard Insider, "Crypto card fees 2026-Q3", https://cryptocardinsider.com/facts/crypto-card-fees-2026-q3 (snapshot 2026-10-27), CC BY 4.0.

> CryptoCard Insider, "RedotPay country restriction lists compared", https://cryptocardinsider.com/content/guide-redotpay-available-countries-20261022 (snapshot 2026-10-22), CC BY 4.0.

Please keep the snapshot date with any number you reuse.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You can copy, adapt and reuse the data, including commercially, as long as you credit CryptoCard Insider and link to the source page.

## Disclosure

CryptoCard Insider is a disclosed RedotPay partner and may earn a referral reward. That is why the RedotPay entry mentions the partner codes RDVIR and RDPHY. The fee values themselves come from RedotPay's help center fee table, not from the partnership. More: [affiliate disclosure](https://cryptocardinsider.com/affiliate-disclosure).

## Updates and corrections

New snapshots are published on the site first and copied here. If you find a value that no longer matches the issuer's source, open an issue with a link to that source.

The site also has a [3D comparison of all 11 cards](https://cryptocardinsider.com/?view=gallery).
