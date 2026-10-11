<p align="center"><img src="https://raw.githubusercontent.com/go-dataframe/brand/main/social/go-dataframe.png" alt="go-dataframe" width="720"></p>

# go-dataframe

🌐 **[Website](https://go-dataframe.github.io)** · 📚 **[Documentation](https://go-dataframe.github.io/docs/)**

**Labelled columnar tables in pure Go (CGO=0): Series, DataFrame and Index, CSV, Arrow and Parquet, group-by, joins, reshaping and time series — on go-ndarray.**

Numeric columns are [go-ndarray](https://github.com/go-ndarray/ndarray) arrays,
handed out without copying. The behavioural reference is pandas: the
operations give its answers (values, dtypes, index, row order), checked
against pandas 3.0 on 173 recorded cases, and the differences that remain are
deliberate and listed. polars is faster on most of the operations measured;
the documentation gives the numbers.

```go
df := dataframe.Must(dataframe.ReadCSVFile("weather.csv", dataframe.CSVParseDates("date")))
g, _ := df.GroupBy("station")
fmt.Println(g.Mean())
```

## Repositories

| Repo | What it is |
|------|------------|
| [**dataframe**](https://github.com/go-dataframe/dataframe) | the library: `Series`, `DataFrame`, `Index`, CSV, display; `arrowio` (Arrow IPC, Feather), `parquetio` (Parquet), `dfplot` (plots with go-plot) (Go 1.27.2 or later) |
| [**docs**](https://github.com/go-dataframe/docs) | the documentation site (Hugo + Hextra), served at [/docs/](https://go-dataframe.github.io/docs/) |
| [**go-dataframe.github.io**](https://github.com/go-dataframe/go-dataframe.github.io) | the landing page (Hugo) |
| [**brand**](https://github.com/go-dataframe/brand) | logo, icons and social images |

It is part of an ecosystem with [go-ndarray](https://github.com/go-ndarray/ndarray)
(N-dimensional arrays), [go-plot](https://github.com/go-plot/plot) (figures),
[go-numerics](https://github.com/go-numerics/optimize) (optimisation,
integration, special functions) and
[go-notebook](https://github.com/go-notebook/notebook), whose kernel shows a
frame through `Display`.
