# Classification vs regression

Fixed ALGO and ETH daily candle snapshots downloaded from Hyperliquid on 2026-11-03 using `hl.dl_ohlc_df`. The request covered seven years ending 2026-11-04 00:00 UTC; available history varies by symbol.

- ALGO-1d.csv: 1,699 rows, 2022-03-11 through 2026-11-03.
- ETH-1d.csv: 2,268 rows, 2020-08-19 through 2026-11-03.

The final candle (2026-11-03) was still in progress when captured and is intentionally frozen as downloaded. These are fresh snapshots, not an export of the original notebook's live kernel; its previous displayed results may differ.

`t` is the datetime index (candle open time); `T` is candle close time. Both are UTC represented without timezone suffixes, matching the original loader. Other columns: `s` (symbol), `i` (interval), `o`, `c`, `h`, `l` (prices), `v` (volume rounded to an integer by the loader), and `n` (trade count).

Load with `pd.read_csv(url, index_col='t', parse_dates=['t', 'T'])`. The notebook pins URLs to a Git commit so subsequent repository updates cannot change its input data.
