---
title: Od prospekta do kasy w podwójnym zapisie
description: Ten temat zawiera informacje dotyczące prospektów do kasy w ramach podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 249fde6f7bba5d6e0bc6cfde62fd792dee3f1301
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112499"
---
# <a name="prospect-to-cash-in-dual-write"></a>Od prospekta do kasy w podwójnym zapisie

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ważnym celem większości firm jest konwersja prospektów na odbiorców, a następnie utrzymywanie w ten sposób stałej relacji biznesowej z tymi odbiorcami. W przypadku aplikacji Microsoft Dynamics 365 proces prospektów do kasy jest realizowany za pośrednictwem ofert lub przepływów pracy przetwarzania zamówień, a finanse są uzgadniane i rozpoznawane. Integracja funkcji prospekty-gotówka z podwójnym zapisem powoduje utworzenie przepływu pracy, który składa ofertę i zamówienie, które pochodzi z systemu Dynamics 365 Sales lub Dynamics 365 Supply Chain Management i udostępnia ofertę i zamówienie dostępne w obu aplikacjach.

W interfejsach aplikacji można uzyskać dostęp do Stanów przetwarzania i informacji o fakturze w czasie rzeczywistym. Dzięki temu można łatwiej zarządzać funkcjami, takimi jak magazynowanie produktów, obsługa zapasów i realizacja w Supply Chain Management bez konieczności ponownego tworzenia ofert i zamówień.

![Przepływ danych o podwójnym zapisie od prospekta do kasy](../dual-write/media/dual-write-prospect-to-cash[1].png)

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

Aby można było synchronizować oferty sprzedaży, należy zaktualizować poniższe ustawienia.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

W Sales przejdź do **Ustawienia \> Administracja \> Ustawienia systemu \> Sprzedaż** i upewnij się, że używane są następujące ustawienia:

- Opcja systemowa **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
- Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="sites-and-warehouses"></a>Oddział i magazyny

W Supply Chain Management pola **oddział** i **magazyn** są wymagane w odniesieniu do wierszy oferty i wierszy zamówień. Jeśli ustawienie oddziału i magazynu zostanie ustawione w domyślnych ustawieniach zamówienia, pola te zostaną automatycznie ustawione podczas dodawania produktu do wiersza oferty lub wiersza zamówienia. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sekwencje numerów ofert i zamówień

Sekwencje numerów dla Supply Chain Management i Sales nie są łączone, gdy oferty i zamówienia są tworzone i synchronizowane w Sales i Supply Chain Management. Jeśli zamówienie sprzedaży utworzone w Sales jest synchronizowane z modułem Supply Chain Management, to ma ten sam numer zamówienia sprzedaży w Supply Chain Management. Aby mieć pewność, że numer zamówienia sprzedaży nie jest duplikowany, należy stosować różne systemy sekwencji numerów w dwóch aplikacjach.

Na przykład sekwencja numerów w Supply Chain Management ma wartość **1, 2, 3, 4, 5, ...**, a sekwencja numerów w sprzedaży to **100, 99, 98, ...**. Jeśli w sprzedaży zostanie utworzonych 100 zamówień sprzedaży, w końcu zostanie wygenerowany numer zamówienia, który już istnieje w Supply Chain Management. Innymi słowy, dwie sekwencje numerów będą nakładać się na siebie w miarę tworzenia zamówień sprzedaży w module Supply Chain Management i Sales. Zamiast tego można użyć sekwencji numerów, na przykład **F1, F2, F3, ...** w Supply Chain Management i sekwencjami numerów, takimi jak **C1, C2, C3, ...** w Sales. Te sekwencje numerów nigdy nie będą generowały zduplikowanych numerów zamówień sprzedaży.

## <a name="sales-quotations"></a>Oferty sprzedaży

Oferty sprzedaży mogą być tworzone albo w Sales, albo Supply Chain Management. W przypadku tworzenia oferty w Sales jest ona synchronizowana z Supply Chain Management w czasie rzeczywistym. Podobnie, w przypadku tworzenia oferty w Supply Chain Management jest ona synchronizowana z Sales w czasie rzeczywistym. Należy uwzględnić następujące informacje:

+ Można dodać rabat do produktu w ofercie. W takim przypadku rabat zostanie zsynchronizowany z Supply Chain Management. Pola **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez konfigurację w programie Supply Chain Management. Ta konfiguracja nie obsługuje mapowania integracji. Zamiast tego w obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są zarządzane i obsługiwane przez program Supply Chain Management.
+ Pola tylko do odczytu w nagłówku oferty sprzedaży: **% rabatu**, **Rabat** i **Kwota frachtu**.
+ Pola **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

## <a name="sales-orders"></a>Zamówienia sprzedaży

Zamówienia sprzedaży mogą być tworzone albo w Sales, albo Supply Chain Management. W przypadku tworzenia zamówienia sprzedaży w Sales jest ona synchronizowana z Supply Chain Management w czasie rzeczywistym. Podobnie, w przypadku tworzenia zamówienia sprzedaży w Supply Chain Management jest ono synchronizowane z Sales w czasie rzeczywistym. Należy uwzględnić następujące informacje:

+ Zamówienia można aktywować i synchronizować z Sales tylko wtedy, gdy wszystkie produkty z zamówienia pochodzą z aplikacji Finance and Operations. Dlatego nie mogą występować produkty dopisane.
+ Obliczanie i zaokrąglanie rabatów:

    - Model obliczania rabatu w rozwiązaniu Sales różni się od modelu obliczania rabatu w rozwiązaniu Supply Chain Management. W rozwiązaniu Supply Chain Management kwota ostatecznego rabatu w wierszu sprzedaży może wynikać z połączenia kwot rabatu i procentów rabatu. Jeżeli ta kwota ostatecznego rabatu zostanie podzielona przez ilość w wierszu, może nastąpić zaokrąglenie. Jednakże to zaokrąglenie nie jest uznawane, jeżeli zaokrąglony rabat na jednostkę zostanie zsynchronizowany z rozwiązaniem Sales. Aby zapewnić, że pełna kwota rabatu z wiersza sprzedaży w rozwiązaniu Supply Chain Management zostanie prawidłowo zsynchronizowana z rozwiązaniem Sales, należy zsynchronizować pełną kwotę bez dzielenia przez ilość w wierszu. Dlatego w rozwiązaniu Sales należy zdefiniować metodę obliczania rabatu jak **Pozycja w wierszu**.
    - Po zsynchronizowaniu wiersza zamówienia sprzedaży z rozwiązania Sales do rozwiązania Supply Chain Management używana jest pełna kwota rabatu wiersza. Ponieważ rozwiązanie Supply Chain Management nie ma pola umożliwiającego przechowywania pełnej kwoty rabatu dla wiersza, kwota jest dzielona przez ilość i przechowywana w polu **Rabat wiersza**. Każde zaokrąglenie powstałe podczas tego dzielenia jest przechowywane w polu **Opłaty od sprzedaży** w wierszu sprzedaży.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Przykład: synchronizacja z Sales do Supply Chain Management

Istnieją następujące zamówienia sprzedaży:

+ **Sprzedaż:** Ilość = 3, rabat na wiersz = 10,00 USD
+ **Supply Chain Management:** ilość = 3, kwota rabatu wiersza = 3,33 USD, opłata od sprzedaży = –0,01 USD

W przypadku synchronizacji z Supply Chain Management do Sales można uzyskać następujące wyniki:

+ **Supply Chain Management:** ilość = 3, kwota rabatu wiersza = 3,33 USD, opłata od sprzedaży = –0,01 USD
+ **Sprzedaż:** Ilość = 3, rabat na wiersz = (3 × 3,33 USD) + 0,01 USD = 10,00 USD

## <a name="dual-write-solution-for-sales"></a>Podwójny zapis dla Sales

Nowe pola zostały dodane do jednostki **Zamówienie** i są wyświetlane na stronie. Większość tych pól jest wyświetlana na karcie **integracja** w module Sales. Dostępne są następujące pola specjalne:

+ Pole **Stan przetwarzania** — to pole służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Supply Chain Management. To pole jest zablokowane i wyświetlany jest tylko stan zamówienia na podstawie Supply Chain Management. Dostępne są następujące wartości:

    + **Aktywna** — stan po uaktywnieniu zamówienia w rozwiązaniu Sales za pomocą przycisku **Uaktywnij**.
    + **Potwierdzone**
    + **Dostarczone**
    + **Zafakturowane**
    + **Częściowo dostarczone**
    + **Częściowo zafakturowane**
    + **Pobrane**
    + **Anulowane**

    W poniższej tabeli przedstawiono sposób mapowania stanu przetwarzania na wartość **kodu stanu modułu CRM**.

    | Stan przetwarzania           | Kod stanu CRM    |
    |-----------------------------|--------------------|
    | Aktywna                      | Nowe/oczekujące/wstrzymane |
    | Potwierdzone/pobrane            | W toku        |
    | Częściowo dostarczone         | Częściowy            |
    | Dostarczone                   | Pełna informacja           |
    | Zafakturowane/częściowo zafakturowane | Zafakturowane           |
    | Anulowane                    | Brak pieniędzy           |

+ Przyciski **Utwórz fakturę** i **Anuluj zamówienie** na stronie **zamówienia sprzedaży** są ukryte w Sales.
+ Wartość **Stan zamówienia sprzedaży** pozostanie **Aktywna**, aby zapewnić przepływ zmian z rozwiązania Supply Chain Management do zamówienia sprzedaży w programie Sales. Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne**.

## <a name="invoices"></a>Faktury

Faktury sprzedaży są tworzone w Supply Chain Management i synchronizowane z programem Sales. Należy uwzględnić następujące informacje:

+ Pole **Numer faktury** zostało dodane do jednostki **Faktura** i jest wyświetlane na stronie.
+ Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Supply Chain Management i zsynchronizowane z programem Sales. Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Supply Chain Management.
+ Wartość **Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano** po zsynchronizowaniu powiązanej faktury z rozwiązania Supply Chain Management do programu Sales. Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury. Dlatego właściciel zamówienia sprzedaży może wyświetlić fakturę.
+ Pola **Warunki frachtu**, **Warunki dostawy** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

## <a name="templates"></a>Szablony

Moduł Od prospektu do gotówki zawiera mapy jednostek podstawowych, które działają wspólnie podczas interakcji, jak pokazano w poniższej tabeli.

| Aplikacje Finance and Operations | Aplikacje oparte na modelu w systemie Dynamics 365 | opis |
|-----------------------------|-----------------------------------|-------------|
| Nagłówki faktur sprzedaży wer. 2    | faktury                          |             |
| Wiersze faktur sprzedaży wer. 2      | invoicedetails                    |             |
| Nagłówki zamówień sprzedaży CDS     | salesorders                       |             |
| Wiersze zamówienia sprzedaży CDS       | salesorderdetails                 |             |
| Kody źródeł zamówień sprzedaży    | msdyn\_salesorderorigins          |             |
| Nagłówek oferty sprzedaży CDS  | Cytaty                            |             |
| Wiersze oferty sprzedaży CDS   | quotedetails                      |             |

Oto powiązane mapowania jednostek podstawowych dla prospektu do gotówki:

+ [Odbiorcy (wersja 3) do kont](customer-mapping.md#customers-v3-to-accounts)
+ [Kontakty CDS (wersja 2) do contacts](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [Odbiorcy (wersja 3) do contacts](customer-mapping.md#customers-v3-to-contacts)
+ [Wydane produkty (wersja 2) do msdyn_sharedproductdetails](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [Wszystkie produkty do msdyn_globalproducts](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Cennik](product-mapping.md)

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]
