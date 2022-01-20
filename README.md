# TIL
Today I learnt (or remembered...) what this code does

---

## To parse numeric dates from excel (eg.: 4112)

```{r}
suslik2 <- import(here("data", "suslik2015_2021.xlsx")) %>% 
  dplyr::mutate(date = as.numeric(date)) %>% 
  dplyr::mutate(date = lubridate::as_date(date, origin = "1899-12-30"))
  ```
