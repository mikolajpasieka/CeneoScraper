# CeneoScraper

## Kod produktu, o którym bedą pobierane  opinie 
84514582

## Algorytm pobierania opinii o pojedynczym proodukcje z serwisu Ceneo.pl 

1. wysłanie zapytania o dostep do stronny z opniami o produkcie (request, responce)
2. jesli operacja zakonczy sie sukcesem, wyodrebnienie z kodu strony fragmentow odpowiadajaacych poszczegolnym opiniom 
3. dla kazdej z opnii wyodybc z kodu html  poszczegolntch elementow i zapisaneie ich w postaci zlozonych stroktor danych 
4. jezeli istnieje kolejna strona z opiniami przejescie na ta strone i powtorzenie krokow 1-4
5. zapisanie opnii w bazie danych 

 
## Struktura opini w serwwsie Ceneo.pl
|składowa|zmienna|selektor|
|--------|-------|--------|
|opinia|review|div.js_product-review|
|identyfikator opinii|review_id|['data-entry-id']|
|autor|author|span.user-post__author-name|
|rekomendacja|recomendation|span.user-post__author-recomendation > em|
|liczba gwiazdek|stars|span.user-post__score-count|
|treść opinii|content|div.user-post__text|
|lista zalet|pros|div.review-feature__item--positive|
|lista wad|cons|div.review-feature__item--negative|
|ile osób uznało opinię za przydatną|likes|button.vote-yes > span|
|ile osób uznało opinię za nieprzydatną|dislikes|button.vote-no > span|
|data wystawienia opinii|publish_date|span.user-post__published > time:nth-child(1)['datetime']|
|data zakupu produktu|purchase_date|span.user-post__published > time:nth-child(2)['datetime']|