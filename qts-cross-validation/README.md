# Quant trading strategies: cross-validation

Fixed BTC daily candle snapshot downloaded from Hyperliquid on 2026-11-25 with `hl.dl_ohlc_df`. The request covered seven years ending 2026-11-25 16:45 UTC; available history is shorter.

- BTC-1d.csv: 2,289 rows, 2020-08-19 through 2026-11-24.

Only completed candles are included. The in-progress 2026-11-25 candle was dropped.

`t` is the datetime index (candle open time); `T` is candle close time. Both are UTC represented without timezone suffixes, matching the original loader. Other columns: `s` (symbol), `i` (interval), `o`, `c`, `h`, `l` (prices), `v` (volume rounded to an integer by the loader), and `n` (trade count).

Load with `pd.read_csv(url, index_col='t', parse_dates=['t', 'T'])`. The notebook pins its URL to a Git commit so subsequent repository updates cannot change its input data.
