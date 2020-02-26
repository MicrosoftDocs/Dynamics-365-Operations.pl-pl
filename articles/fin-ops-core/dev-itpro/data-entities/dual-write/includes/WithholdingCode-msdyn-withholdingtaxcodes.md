## <a name="withholding-tax-codes-to-msdyn_withholdingtaxcodes"></a>Kody potrąconych zaliczek na podatek do msdyn_withholdingtaxcodes

Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Common Data Service.

Pole aplikacji Finance and Operations | Typ mapy | Inne pole rozwiązania Dynamics 365 | Wartość domyślna
---|---|---|---
WITHHOLDINGCODE | = | msdyn_name | 
WITHHOLDINGTAXNAME | = | msdyn_description | 
WITHHOLDINGTAXROUNDOFF | = | msdyn_roundoff | 
WITHHOLDINGTAXROUNDOFFTYPE | >< | msdyn_roundofftype | 
CURRENCYCODEID | = | msdyn_currency.isocurrencycode | 
WITHHOLDINGTAXBASE | >< | msdyn_taxableamountorigin | 
