---
title: Interfejsy API wyceny handlowej
description: W tym artykule opisano różne interfejsy API wyceny udostępniane przez aparat cen Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294122"
---
# <a name="commerce-pricing-apis"></a>Interfejsy API wyceny handlowej

[!include [banner](../includes/banner.md)]

W tym artykule opisano różne interfejsy API wyceny udostępniane przez aparat cen Microsoft Dynamics 365 Commerce.

Aparat cen Dynamics 365 Commerce udostępnia następujące interfejsy API usługi Retail Server, które mogą być zużywane przez aplikacje zewnętrzne w celu obsługi różnych scenariuszy cen:

- **GetActivePrices** — ten interfejs API pobiera obliczoną cenę produktu, w tym proste rabaty.
- **CalculateSalesDocument** — ten interfejs API oblicza ceny i rabaty na produkty w podanych ilościach, jeśli są kupowane razem.
- **GetAvailablePromotions** — ten interfejs API otrzymuje odpowiednie rabaty na produkty w koszyku. 
- **AddCoupons** — ten interfejs API dodaje kupony do koszyka.
- **RemoveCoupons** — ten interfejs API usuwa kupony z koszyka.

Aby uzyskać więcej informacji dotyczących sposobu zużywania interfejsów API usługi Retail Server w aplikacjach zewnętrznych, zobacz [Zużycie interfejsów API usługi Retail Server w aplikacjach zewnętrznych](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

Interfejs *API GetActivePrices* został wprowadzony w wersji Commerce 10.0.4. Ten interfejs API pobiera obliczoną cenę produktu, w tym proste rabaty. Nie oblicza rabatów multiline i przyjmuje, że każdy produkt w żądaniu API ma ilość 1. Ten interfejs API może także przyjmować listę produktów jako dane wejściowe i kwerendę cen poszczególnych produktów masowo.

Interfejs *API GetActivePrices* obsługuje role **Pracownik**, **Odbiorca**, **Anonimowy** i **Aplikacja** Commerce.

Głównym powodem dla interfejsu API *GetActivePrices* jest strona szczegółów produktu (PDP), na której sprzedawcy detaliczni chcą wykorzystywać najlepszą cenę produktu, uwzględniając wszelkie rabaty efektywne.

W poniższej tabeli przedstawiono parametry wejściowe interfejsu *API GetActivePrices*.

| Nazwisko                                    | Nazwa podrzędna | Typ | Wymagane/Opcjonalne | Opis |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Wymagane | |
|                                         | ChannelId | długi | Wymagane | |
|                                         | CatalogId | długi | Wymagane | |
| productIds                              | | IEnumerable\<long\> | Wymagane | Lista produktów, dla których mają być obliczone ceny. |
| activeDate                              | | DateTimeOffset | Wymagane | Data obliczania cen. |
| customerId                              | | ciąg | Opcjonalnie | Numer konta klienta. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Opcjonalnie | Poziomy przynależności i lojalności. |
|                                         | AffiliationId | długi | Wymagane | Identyfikator przynależności. |
|                                         | LoyaltyTierId | długi | Opcjonalnie | Identyfikator poziomu lojalności. |
| includeSimpleDiscountsInContextualPrice | | bool | Opcjonalnie | Ustaw dla tego parametru wartość **Prawda,** aby w obliczeniach cen uwzględnić proste rabaty. Domyślna wartość to **false**. |
| includeVariantPriceRange                | | bool | Opcjonalnie | Ustaw ten parametr na **Prawda**, aby uzyskać ceny minimalne i maksymalne wśród wszystkich wariantów produktu głównego. Domyślna wartość to **false**. |
| includeAttainablePricesAndDiscounts     | | bool | Opcjonalnie | Ustaw dla tego parametru wartość **Prawda,** aby uzyskać dostępną cenę i rabaty. Domyślna wartość to **false**. |

**Przykładowa treść żądania**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Przykładowa treść odpowiedzi**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

Interfejs API *CalculateSalesDocument* został wprowadzony w wersji Commerce 10.0.25. Ten interfejs API oblicza ceny i rabaty na produkty w określonych ilościach, jeśli są kupowane razem w zamówieniu. W kalkulacji cen za interfejsem API *CalculateSalesDocument* są rozważane rabaty jedno wierszowe i rabaty wielo wierszy.

Głównym powodem dla interfejsu API *CalculateSalesDocument* jest obliczanie cen w scenariuszach, w których kontekst pełnego koszyka nie będzie się powtarzał (np. oferty sprzedaży). Scenariusze w punkt sprzedaży (POS) i Commerce e-commerce mogą również korzystać z tego przypadku. Niższa łączna cena, gdy pozycje koszyka są obliczane jako zestaw (na przykład w przypadku oddzielnych pakietów, powiązanych lub polecanych produktów lub produktów, które zostały już dodane do koszyka) może skłonić klientów do dodania produktów do koszyka.

Model danych dla żądania i odpowiedzi interfejsu API *CalculateSalesDocument* to **Koszyk**. Jednak w kontekście tego interfejsu API model danych nosi nazwę **SalesDocument**. Ponieważ większość właściwości jest opcjonalna, a tylko kilka z nich wpływa na kalkulację cen, w poniższej tabeli przedstawiono tylko pola związane z cenami. Nie zalecamy, aby żadne inne pola były zaangażowane w żądanie API.

Zakres interfejsu API *CalculateSalesDocument* to tylko obliczanie cen i rabatów. Podatki i opłaty nie są związane.

W poniższej tabeli przedstawiono parametry wejściowe wewnątrz obiektu o nazwie **salesDocument**.

| Nazwisko             | Nazwa podrzędna | Typ | Wymagane/Opcjonalne | Opis |
|------------------|----------|------|-------------------|-------------|
| Identyfikator               | | ciąg | Wymagane | Identyfikator dokumentu sprzedaży. |
| CartLines        | | IList\<CartLine\> | Opcjonalnie | Lista wierszy do kalkulacji cen i rabatów. |
|                  | Identyfikator produktu | długi | Wymagane w zakresie CartLine | Identyfikator rekordu produktu. |
|                  | ItemId | ciąg | Opcjonalnie | Identyfikator pozycji. Jeśli zostanie dostarczana wartość, musi być ona zgodne z wartością parametru **ProductId**. |
|                  | InventoryDimensionId | ciąg | Opcjonalnie | Umożliwia identyfikację wymiaru magazynowego. Jeśli zostanie podano wartość, kombinacja wartości **ItemId** i **InventoryDimensionId** musi odpowiadać wartości parametru **ProductId**. |
|                  | Ilość | dziesiętny | Wymagane w zakresie CartLine | Ilość produktu. |
|                  | UnitOfMeasureSymbol | ciąg | Opcjonalnie | Jednostka produktu. Domyślnie, jeśli nie zostanie włączona wartość, interfejs API używa jednostki sprzedaży tego produktu. |
| CustomerId       | | ciąg | Opcjonalnie | Numer konta klienta. |
| LoyaltyCardId    | | ciąg | Opcjonalnie | Identyfikator karty lojalnościowej. Wszystkie konta odbiorców skojarzone z kartą lojalnościową muszą być zgodne z wartością parametru **CustomerId** (jeśli jest dostarczana). Karta lojalnościowa nie będzie uznawana, jeśli nie znaleziono jej lub jej stan jest **Zablokowany**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Opcjonalnie | Linie poziomu lojalności przynależności. Jeśli zostaną podane wartości **CustomerId** i/lub **LoyaltyCardId**, odpowiednie wiersze warstwy lojalnościowej przynależności zostaną scalone z wierszami dostarczonymi w wartości **AffiliationLines**. |
|                  | AffiliationId | długi | Wymagane w zakresie AffiliationLoyaltyTier | Identyfikator rekordu przynależności. |
|                  | LoyaltyTierId | długi | Wymagane w zakresie AffiliationLoyaltyTier | Identyfikator rekordu poziomu lojalności. |
|                  | AffiliationTypeValue | liczba całkowita | Wymagane w zakresie AffiliationLoyaltyTier | Wartość wskazująca, czy wiersz przynależności jest typu **Ogólnego** (**0**) czy Typu **lojalności** (**1**). Jeśli ten parametr ma wartość **0**, interfejs API przyjmuje **wartość AffiliationId** jako identyfikator i ignoruje wartość **LoyaltyTierId**. Jeśli ten parametr ma wartość **1**, interfejs API przyjmuje **wartość LoyaltyTierId** jako identyfikator i ignoruje wartość **AffiliationId**. |
|                  | ReasonCodeLines | Ponaglenie\<ReasonCodeLine\> | Wymagane w zakresie AffiliationLoyaltyTier | Wiersze kodu przyczyny. Ten parametr nie ma wpływu na kalkulację cen, ale jest wymagany jako część obiektu **AffiliationLoyaltyTier**. |
|                  | CustomerId | ciąg | Wymagane w zakresie AffiliationLoyaltyTier | Numer konta klienta. |
| Kupony          | | IList\<Coupon\> | Opcjonalnie | Kupony, które nie mają zastosowania (nieaktywne, wygasłe lub nie można ich znaleźć), nie będą rozważane w kalkulacji cen. |
|                  | Kod | ciąg | Wymagane w zakresie kuponu | Kod kuponu. |
|                  | CodeId | ciąg | Opcjonalnie | Identyfikator kodu kuponu. Jeśli zostanie dostarczana wartość, musi być ona zgodne z wartością parametru **Kod**. |
|                  | DiscountOfferId | ciąg | Opcjonalnie | Identyfikator rabatu. Jeśli zostanie dostarczana wartość, musi być ona zgodne z wartością parametru **Kod**. |

**Przykładowa treść żądania**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

Cały obiekt koszyka jest zwracany jako treść odpowiedzi. Aby sprawdzić ceny i rabaty, należy skupić się na polach w poniższej tabeli.

| Nazwisko           | Nazwa podrzędna | Typ | Opis |
|----------------|----------|------|--------------|
| NetPrice       | | dziesiętny | Cena netto całego dokumentu sprzedaży przed zastosowaniem rabatów. |
| DiscountAmount | | dziesiętny | Całkowita kwota rabatu dla całego dokumentu sprzedaży. |
| TotalAmount    | | dziesiętny | Całkowita kwota dla całego dokumentu sprzedaży. |
| CartLines      | | IList\<CartLine\> | Wiersze obliczane, które zawierają szczegóły ceny i rabatu. |
|                | Cena | dziesiętny | Cena jednostkowa produktu. |
|                | NetPrice | dziesiętny | Cena netto całego dokumentu sprzedaży przed zastosowaniem rabatów (= *Cena* &times; *Ilość*). |
|                | DiscountAmount | dziesiętny | Kwota rabatu. |
|                | TotalAmount | dziesiętny | Ostateczny wynik ceny całkowitej dla wiersza. |
|                | PriceLines | IList\<PriceLine\> | Szczegóły ceny, w tym źródło ceny (podstawa ceny, korekta ceny lub umowa handlowa) i kwota. |
|                | DiscountLines | IList\<DiscountLine\> | Szczegóły rabatu. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

W danym koszyku, który ma kilka wierszy koszyka, interfejs API *GetAvailablePromotions* zwraca wszystkie odpowiednie rabaty dla wierszy koszyka. 

Głównym powodem dla interfejsu API *GetAvailablePromotions* jest strona koszyka, na której sprzedawcy detaliczni chcą zastosować rabaty lub dostępne kupony dla bieżącego koszyka.

W poniższej tabeli przedstawiono parametry wejściowe interfejsu API *GetAvailablePromotions*.

| Nazwisko        | Typ | Wymagane/Opcjonalne | Opis |
|-------------|------|-------------------|-------------|
| klucz         | ciąg | Wymagane | Identyfikator koszyka. |
| cartLineIds | IEnumerable\<string\> | Opcjonalnie | Ustaw ten parametr, aby zwracać rabaty tylko dla wybranych wierszy koszyka. |

**Przykładowa treść odpowiedzi**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

Interfejs API *AddCoupons* obsługuje dodawanie listy kuponów do koszyka. Zwraca obiekt koszyka po dodaniu kuponów.

W poniższej tabeli przedstawiono parametry wejściowe interfejsu API *AddCoupons*.

| Nazwisko                 | Typ | Wymagane/Opcjonalne | Opis |
|----------------------|------|-------------------|-------------|
| klucz                  | ciąg | Wymagane | Identyfikator koszyka. |
| couponCodes          | IEnumerable\<string\> | Wymagane | Kody kuponów do dodania do koszyka. |
| isLegacyDiscountCode | bool | Opcjonalnie | Ustaw ten parametr na wartość **True,** aby wskazać, że kupon jest starszego kodu rabatu. Domyślna wartość to **false**. |

## <a name="removecoupons"></a>RemoveCoupons

Interfejs API *RemoveCoupons* obsługuje usuwanie listy kuponów z koszyka. Zwraca przedmiot koszyka po usunięciu kuponów.

W poniższej tabeli przedstawiono parametry wejściowe interfejsu API *RemoveCoupons*.

| Nazwisko        | Typ | Wymagane/Opcjonalne | Opis |
|-------------|------|-------------------|-------------|
| klucz         | ciąg | Wymagane | Identyfikator koszyka. |
| couponCodes | IEnumerable\<string\> | Wymagane | Kody kuponów do usunięcia z koszyka. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
