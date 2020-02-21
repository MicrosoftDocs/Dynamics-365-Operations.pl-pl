## <a name="exchange-rate-currency-pair-to-msdyn_currencyexchangeratepairs"></a>Para walut kursu wymiany do msdyn_currencyexchangeratepairs

Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Common Data Service.

Pole aplikacji Finance and Operations | Typ mapy | Inne pole rozwiązania Dynamics 365 | Wartość domyślna
---|---|---|---
EXCHANGERATEDISPLAYFACTOR | >< | msdyn_displayfactor | 
EXCHANGERATETYPENAME | = | msdyn_currencyexchangeratetypeid.msdyn_name | 
FROMCURRENCYCODE | = | msdyn_fromtransactioncurrencyid.isocurrencycode | 
TOCURRENCYCODE | = | msdyn_totransactioncurrencyid.isocurrencycode | 
