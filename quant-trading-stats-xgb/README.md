# Quant trading stats: XGBoost

Fixed ALGO daily candle snapshot downloaded from Hyperliquid on 2026-11-06 with the same transforms as `hl.dl_ohlc_df`. The request covered seven years ending 2026-11-06 19:41 UTC; available history is shorter.

- ALGO-1d.csv: 1,701 rows, 2022-03-11 through 2026-11-05.

Only completed candles are included. The in-progress 2026-11-06 candle was dropped.

`t` is the datetime index (candle open time); `T` is candle close time. Both are UTC represented without timezone suffixes, matching the original loader. Other columns: `s` (symbol), `i` (interval), `o`, `c`, `h`, `l` (prices), `v` (volume rounded to an integer by the loader), and `n` (trade count).

Load with `pd.read_csv(url, index_col='t', parse_dates=['t', 'T'])`. The notebook pins its URL to a Git commit so subsequent repository updates cannot change its input data.
