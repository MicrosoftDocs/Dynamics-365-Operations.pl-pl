---
title: Konfigurowanie podatku dla zamówień online
description: Ten artykuł stanowi przegląd wyboru grupy podatków dla różnych typów zamówień w trybie online w Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: c899bd020ec9536a906a98635a6c70fac1355789
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819277"
---
# <a name="configure-sales-tax-for-online-orders"></a>Konfigurowanie podatku dla zamówień online

[!include [banner](includes/banner.md)]

Ten artykuł zawiera omówienie wyboru grupy podatku dla różnych typów zamówień online przy użyciu ustawień podatku dla miejsca docelowego lub konta odbiorcy. 

Możesz chcieć, aby Twój kanał handlu elektronicznego obsługiwał takie opcje, jak dostawa lub odbiór zamówień online. Stosowanie podatku jest oparte na opcji wybranej przez klientów w trybie online. 

## <a name="destination-based-taxes-for-online-orders"></a>Podatki oparte na lokalizacji docelowej dla zamówień online

Na ogół podatki dla zamówień w trybie online, które są wysyłane na adresy odbiorców, są definiowane przez miejsce docelowe. Każda grupa podatków ma konfigurację podatku według lokalizacji docelowej sieci sprzedaży, w której firma może definiować szczegóły docelowe, takie jak powiat lub region, województwo i miasto w postaci hierarchicznej.

Konfigurację dla **Podatku na podstawie miejsca docelowego sprzedaży detalicznej** można znaleźć w sekcji **Moduł podatkowy > Podatki pośrednie > Podatek od sprzedaży > Grupy podatków**.

### <a name="orders-delivered-to-customer-address"></a>Zamówienia dostarczane na adres klienta

Po złożeniu zamówienia online aparat podatkowy Commerce używa adresu dostawy każdego elementu zamówienia w zamówieniu i znajduje grupy podatków z pasującymi kryteriami podatkowymi opartymi na miejscu docelowym. Na przykład w przypadku zamówienia online z adresem dostawy elementu zamówienia do San Francisco w Kalifornii aparat podatkowy znajdzie grupę podatków i kod podatku dla Kalifornii, a następnie odpowiednio obliczy podatek dla każdego elementu zamówienia.

### <a name="order-pick-up-in-store"></a>Odbiór zamówienia w sklepie

W przypadku wierszy zamówienia z określonym odbiorem w sklepie lub przy krawężniku zostanie zastosowana grupa podatkowa z wybranego punktu odbioru. Aby uzyskać szczegółowe informacje na temat konfigurowania podatków od sprzedaży dla danego sklepu, zapoznaj się z tematem [Konfigurowanie innych opcji podatków dla sklepów](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Podatki naliczane od konta klienta w przypadku zamówień online

Może istnieć scenariusz biznesowy, w którym chcesz skonfigurować grupę podatków na określonym koncie odbiorcy w centrali Commerce. W centrali są dwa miejsca, w których można skonfigurować podatek od sprzedaży na koncie odbiorcy. Aby uzyskać dostęp do tych informacji, najpierw musisz uzyskać dostęp do strony szczegółów odbiorcy, przechodząc do **Retail i Commerce \> Odbiorcy \> Wszyscy odbiorcy**, a następnie wybierając klienta.

Dwa miejsca, w których konfigurujesz podatek od sprzedaży dla konta klienta, to:

- **Grupa podatków** na skróconej karcie **Faktura i dostawa** na stronie szczegółów odbiorcy. 
- **Podatek** na skróconej karcie **Ogólne** na stronie **Zarządzanie adresami**. Aby uzyskać więcej informacji ze strony szczegółów dotyczących odbiorcy, wybierz określony adres na skróconej karcie **Adresy**, a następnie wybierz pozycję **Zaawansowane**.

> [!TIP]
> W przypadku zamówień odbiorcy online, jeśli chcesz tylko stosować podatki oparte na lokalizacji docelowej i uniknąć podatków opartych na kontach odbiorcy, upewnij się, że pole **Grupa podatków** jest puste na skróconej karcie **Faktura i dostawa** na stronie szczegółów odbiorcy. Aby nowi odbiorcy, którzy za pomocą kanału online nie dziedziczyli ustawień grupy podatków po ustawieniach domyślnego odbiorcy lub grupy odbiorców, upewnij się, że pole **Grupa podatków** jest również puste w przypadku domyślnych ustawień odbiorcy kanału online i ustawień grupy odbiorców (**Retail i Commerce \> Odbiorcy \> Grupy odbiorców**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Określ zastosowanie podatku opartego na miejscu docelowym lub podatku na koncie klienta 

W poniższej tabeli wyjaśniono, czy w przypadku zamówień online są stosowane podatki zależne od miejsca docelowego, czy podatki od konta klienta. 

| Typ odbiorcy | Adres wysyłkowy                   | Odbiorca > Faktura i dostawa > Grupa podatków? | Adres na koncie odbiorcy w centrali? | Adres odbiorcy > Zaawansowane > Ogólne > Grupa podatków?                                              | Zastosowana grupa podatków      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Gość         | Manhattan, NY                      | Nie (puste)                                                | Nie (puste)                              | Nie (puste)                                                                                                   | NY (podatki oparte na lokalizacjach docelowych) |
| Zalogowano     | Austin, TX                          | Nie (puste)                                             | Tak                               | None<br/><br/>Nowy adres dodany za pośrednictwem kanału online.                                                            | TX (podatki oparte na lokalizacjach docelowych) |
| Zalogowano     | San Francisco, CA (odbiór w sklepie) | Tak (NY)                                            | Nie dotyczy                              | Nie dotyczy                                                                                                    | CA (podatki oparte na lokalizacjach docelowych) |
| Zalogowano     | Houston, TX                         | Tak (NY)                                            | Tak                               | Tak (NY)<br/><br/>Nowy adres dodany przez kanał online i grupa podatku od sprzedaży odziedziczona z konta klienta. | NY (podatki według konta odbiorcy)  |
| Zalogowano     | Austin, TX                          | Tak (NY)                                            | Tak                               | Tak (NY)<br/><br/>Nowy adres dodany przez kanał online i grupa podatku od sprzedaży odziedziczona z konta klienta. | NY (podatki według konta odbiorcy)  |
| Zalogowano     | Sarasota, FL                       | Tak (NY)                                            | Tak                               | Tak (WA)<br/><br/>Ręcznie ustawiono na WA.                                                                          | WA (podatki według konta odbiorcy)  |
| Zalogowano     | Sarasota, FL                       | Nie (puste)                                                | Tak                               | Tak (WA)<br/><br/>Ręcznie ustawiono na WA.                                                                          | WA (podatki według konta odbiorcy)  |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Omówienie podatku](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Wybieranie metody obliczania podatku w polu Źródło](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[ Przypisanie i zastąpienia podatku](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Opcje Cała kwota i Obliczanie interwału dla kodów podatku](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Obliczanie zwolnienia z podatku](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
