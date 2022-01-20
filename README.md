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
## To parse crazy dates 

```{r}
suslik2 <- import(here("data", "suslik2015_2021.xlsx")) %>% 
    dplyr::mutate(date = lubridate::parse_date_time(date, "%y-%m-%d"))
  ```
  
  If there are several versions of dates, you can provide them eg as:
  
  ```{r}
x <- c("09-01-01", "090102", "09-01 03", "09-01-03 12:02")
parse_date_time(x, c("ymd", "ymd HM"))
  ```
