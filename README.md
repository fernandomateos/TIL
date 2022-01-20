# TIL
Today I learnt (or remembered...) what this code does

---

## To parse numeric dates from excel (eg.: 4112)

(Although in the end I fixed it in excel by putting all cells in the same format)

```{r}
suslik2 <- import(here("data", "suslik2015_2021.xlsx")) %>% 
  dplyr::mutate(date = as.numeric(date)) %>% 
  dplyr::mutate(date = lubridate::as_date(date, origin = "1899-12-30"))
  ```
