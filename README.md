# Czechitas--SQL---Domaci ukol 1: where-podminky
Úloha procvičující základní práci s SQL dotazy – výběr dat z tabulek, filtrování podle podmínek, řazení výsledků a úprava výstupu. Vypracováno v rámci vzdělávacího programu Czechitas (Kurz SQL). Pracovali jsme s fiktivní databází v systému Oracle, ke které jsme měli přístup během kurzu.

Zadání:
1. Vyberte prvních 5 výrobců (`manufacturers`), seřazených podle názvu abecedně vzestupně
SELECT*FROM SQL1.MANUFACTURERS
ORDER BY manufacturer asc
FETCH FIRST 5 ROWS ONLY;

2. Zjistěte všechny produkty z kategorie `Youth` a seřaďte je podle ceny (`priceNew`) sestupně.
SELECT* FROM SQL1.PRODUCTS
WHERE Category = 'Youth'
ORDER BY PRICENEW desc;

3. Vyberte všechny prodeje uskutečněné v únoru, jejichž tržba je mezi 1800 a 1900.
   Zobrazte pouze sloupce `productid`, `calendarid` a tržbu za jeden kus, a vhodně je česky pojmenujte.
SELECT productid AS číslo_produktu, calendarid AS datum, (revenue/units) AS tržba_za_ks
FROM SQL1.SALES
WHERE to_char(calendarid, 'MM')= '02' and revenue between 1800 and 1900;
