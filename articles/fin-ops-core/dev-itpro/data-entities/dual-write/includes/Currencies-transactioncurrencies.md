## <a name="currencies-to-transactioncurrencies"></a>Waluty do transactioncurrencies

Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Common Data Service.

Filtr źródła: ((CURRENCYCODE ! = „999”))

Pole aplikacji Finance and Operations | Typ mapy | Inne pole rozwiązania Dynamics 365 | Wartość domyślna
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NAME | = | currencyname | 
SYMBOL | = | currencysymbol | 
none | >> | exchangerate | 1
