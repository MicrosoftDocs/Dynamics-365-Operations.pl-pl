---
title: Od prospekta do kasy w podwójnym zapisie
description: Ten artykuł zawiera informacje dotyczące prospektów do kasy w ramach podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 4321d980f56e321a653ca4f4c5738ebd1bb0153d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289617"
---
# <a name="prospect-to-cash-in-dual-write"></a>Od prospekta do kasy w podwójnym zapisie

[!include [banner](../../includes/banner.md)]

Ważnym celem większości firm jest konwersja prospektów na odbiorców, a następnie utrzymywanie w ten sposób stałej relacji biznesowej z tymi odbiorcami. W przypadku aplikacji Microsoft Dynamics 365 proces prospektów do kasy jest realizowany za pośrednictwem ofert lub przepływów pracy przetwarzania zamówień, a finanse są uzgadniane i rozpoznawane. Integracja funkcji prospekty-gotówka z podwójnym zapisem powoduje utworzenie przepływu pracy, który składa ofertę i zamówienie, które pochodzi z systemu Dynamics 365 Sales lub Dynamics 365 Supply Chain Management i udostępnia ofertę i zamówienie dostępne w obu aplikacjach.

W interfejsach aplikacji można uzyskać dostęp do Stanów przetwarzania i informacji o fakturze w czasie rzeczywistym. Dzięki temu można łatwiej zarządzać funkcjami, takimi jak magazynowanie produktów, obsługa zapasów i realizacja w Supply Chain Management bez konieczności ponownego tworzenia ofert i zamówień.

![Przepływ danych o podwójnym zapisie od prospektu do kasy.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Aby uzyskać informacje o integracji odbiorcy i kontaktów, zobacz temat [Zintegrowany wzorzec klienta](customer-mapping.md). Aby uzyskać informacje na temat integracji produktów, zobacz temat [Ujednolicone działanie produktu](product-mapping.md).

> [!NOTE]
> W przypadku usługi Dynamics 365 Sales prospekt i odbiorca odwołują się do rekordu w tabeli **Konta**, w której kolumna **RelationshipType** to **Prospekt** lub **Odbiorca**. Jeśli logika biznesowa zawiera proces kwalifikacji **konta**, w którym najpierw jest tworzony rekord **konta** i zakwalifikowany jako prospekt, a następnie jako klient, rekord jest synchronizowany z aplikacją finansową i operacyjną tylko wtedy, gdy jest to klient (`RelationshipType=Customer`). Jeśli chcesz, aby wiersz **Konto** był synchronizowany jako prospekt, musisz mieć niestandardową mapę, aby zintegrować dane prospektu.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

Aby można było synchronizować oferty sprzedaży, należy zaktualizować poniższe ustawienia.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

W Sales przejdź do **Ustawienia \> Administracja \> Ustawienia systemu \> Sprzedaż** i upewnij się, że używane są następujące ustawienia:

- Opcja systemowa **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
- Kolumna **Metoda kalkulacji rabatów** jest ustawiona na **Pozycja w wierszu**.

### <a name="sites-and-warehouses"></a>Oddział i magazyny

W Supply Chain Management kolumny **oddział** i **magazyn** są wymagane w odniesieniu do wierszy oferty i wierszy zamówień. Jeśli ustawienie oddziału i magazynu zostanie ustawione w domyślnych ustawieniach zamówienia, kolumny te zostaną automatycznie ustawione podczas dodawania produktu do wiersza oferty lub wiersza zamówienia. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sekwencje numerów ofert i zamówień

Sekwencje numerów dla Supply Chain Management i Sales nie są łączone, gdy oferty i zamówienia są tworzone i synchronizowane w Sales i Supply Chain Management. Jeśli zamówienie sprzedaży utworzone w Sales jest synchronizowane z modułem Supply Chain Management, to ma ten sam numer zamówienia sprzedaży w Supply Chain Management. Aby mieć pewność, że numer zamówienia sprzedaży nie jest duplikowany, należy stosować różne systemy sekwencji numerów w dwóch aplikacjach.

Na przykład sekwencja numerów w Supply Chain Management ma wartość **1, 2, 3, 4, 5, ...**, a sekwencja numerów w sprzedaży to **100, 99, 98, ...**. Jeśli w sprzedaży zostanie utworzonych 100 zamówień sprzedaży, w końcu zostanie wygenerowany numer zamówienia, który już istnieje w Supply Chain Management. Innymi słowy, dwie sekwencje numerów będą nakładać się na siebie w miarę tworzenia zamówień sprzedaży w module Supply Chain Management i Sales. Zamiast tego można użyć sekwencji numerów, na przykład **F1, F2, F3, ...** w Supply Chain Management i sekwencjami numerów, takimi jak **C1, C2, C3, ...** w Sales. Te sekwencje numerów nigdy nie będą generowały zduplikowanych numerów zamówień sprzedaży.

## <a name="sales-quotations"></a>Oferty sprzedaży

Oferty sprzedaży mogą być tworzone albo w Sales, albo Supply Chain Management. W przypadku tworzenia oferty w Sales jest ona synchronizowana z Supply Chain Management w czasie rzeczywistym. Podobnie, w przypadku tworzenia oferty w Supply Chain Management jest ona synchronizowana z Sales w czasie rzeczywistym. Należy uwzględnić następujące informacje:

+ Można dodać rabat do produktu w ofercie. W takim przypadku rabat zostanie zsynchronizowany z Supply Chain Management. Kolumny **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez konfigurację w programie Supply Chain Management. Ta konfiguracja nie obsługuje mapowania integracji. Zamiast tego w obecnym kształcie systemu kolumny **Cena**, **Rabat**, **Opłata** i **Podatek** są zarządzane i obsługiwane przez program Supply Chain Management.
+ Kolumny tylko do odczytu w nagłówku oferty sprzedaży: **% rabatu**, **Rabat** i **Kwota frachtu**.
+ Kolumny **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te kolumny, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana tabela.

Jeśli używane jest także rozwiązanie Field Service, należy ponownie włączyć parametr **Szybkie utworzenie wiersza oferty**. Ponowne włączenie parametru umożliwia kontynuowanie tworzenia wierszy oferty przy użyciu funkcji szybkiego tworzenia.

1. Przejdź do aplikacji Dynamics 365 Sales.
2. Wybierz ikonę ustawienia na górnym pasku nawigacyjnym.
3. Wybierz **Ustawienia zaawansowane**.
4. Wybierz opcję **Dostosuj system**.
5. Wybierz pozycję w menu **Wiersz oferty**.
6. Przejdź do sekcji **Usługi danych** i zaznacz pole wyboru **Zezwalaj na szybkie tworzenie**.

## <a name="sales-orders"></a>Zamówienia sprzedaży

Zamówienia sprzedaży mogą być tworzone albo w Sales, albo Supply Chain Management. W przypadku tworzenia zamówienia sprzedaży w Sales jest ona synchronizowana z Supply Chain Management w czasie rzeczywistym. Podobnie, w przypadku tworzenia zamówienia sprzedaży w Supply Chain Management jest ono synchronizowane z Sales w czasie rzeczywistym. Należy uwzględnić następujące informacje:

+ Produkty korzystające z podwójnego zapisu w systemie Dynamics 365 Sales są wyświetlane jako kategorie produktów w systemie Dynamics 365 Supply Chain Management.
+ Obliczanie i zaokrąglanie rabatów:

    - Model obliczania rabatu w rozwiązaniu Sales różni się od modelu obliczania rabatu w rozwiązaniu Supply Chain Management. W rozwiązaniu Supply Chain Management kwota ostatecznego rabatu w wierszu sprzedaży może wynikać z połączenia kwot rabatu i procentów rabatu. Jeżeli ta kwota ostatecznego rabatu zostanie podzielona przez ilość w wierszu, może nastąpić zaokrąglenie. Jednakże to zaokrąglenie nie jest uznawane, jeżeli zaokrąglony rabat na jednostkę zostanie zsynchronizowany z rozwiązaniem Sales. Aby zapewnić, że pełna kwota rabatu z wiersza sprzedaży w rozwiązaniu Supply Chain Management zostanie prawidłowo zsynchronizowana z rozwiązaniem Sales, należy zsynchronizować pełną kwotę bez dzielenia przez ilość w wierszu. Dlatego w rozwiązaniu Sales należy zdefiniować metodę obliczania rabatu jak **Pozycja w wierszu**.
    - Po zsynchronizowaniu wiersza zamówienia sprzedaży z rozwiązania Sales do rozwiązania Supply Chain Management używana jest pełna kwota rabatu wiersza. Ponieważ rozwiązanie Supply Chain Management nie ma kolumny umożliwiającej przechowywanie pełnej kwoty rabatu dla wiersza, kwota jest dzielona przez ilość i przechowywana w kolumnie **Rabat wiersza**. Każde zaokrąglenie powstałe podczas tego dzielenia jest przechowywane w kolumnie **Opłaty od sprzedaży** w wierszu sprzedaży.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Przykład: synchronizacja z Sales do Supply Chain Management

Istnieją następujące zamówienia sprzedaży:

+ **Sprzedaż:** Ilość = 3, rabat na wiersz = 10,00 USD
+ **Supply Chain Management:** ilość = 3, kwota rabatu wiersza = 3,33 USD, opłata od sprzedaży = –0,01 USD

W przypadku synchronizacji z Supply Chain Management do Sales można uzyskać następujące wyniki:

+ **Supply Chain Management:** ilość = 3, kwota rabatu wiersza = 3,33 USD, opłata od sprzedaży = –0,01 USD
+ **Sprzedaż:** Ilość = 3, rabat na wiersz = (3 × 3,33 USD) + 0,01 USD = 10,00 USD

## <a name="dual-write-solution-for-sales"></a>Podwójny zapis dla Sales

Nowe kolumny zostały dodane do tabeli **Zamówienie** i są wyświetlane na stronie. Większość tych kolumn jest wyświetlana na karcie **integracja** w module Sales. Aby dowiedzieć się więcej o mapowaniu kolumn stanu, zobacz [Skonfiguruj mapowanie dla kolumn stanu zamówienia sprzedaży](sales-status-map.md).

+ Przyciski **Utwórz fakturę** i **Anuluj zamówienie** na stronie **zamówienia sprzedaży** są ukryte w Sales.
+ Wartość **Stan zamówienia sprzedaży** pozostanie **Aktywna**, aby zapewnić przepływ zmian z rozwiązania Supply Chain Management do zamówienia sprzedaży w programie Sales. Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne**.

## <a name="invoices"></a>Faktury

Faktury sprzedaży są tworzone w Supply Chain Management i synchronizowane z programem Sales. Należy uwzględnić następujące informacje:

+ Kolumna **Numer faktury** została dodana do tabeli **Faktura** i jest wyświetlana na stronie.
+ Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Supply Chain Management i zsynchronizowane z programem Sales. Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Supply Chain Management.
+ Wartość **Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano** po zsynchronizowaniu powiązanej faktury z rozwiązania Supply Chain Management do programu Sales. Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury. Dlatego właściciel zamówienia sprzedaży może wyświetlić fakturę.
+ Kolumny **Warunki frachtu**, **Warunki dostawy** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te kolumny, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana tabela.

## <a name="templates"></a>Szablony

Moduł Od prospektu do gotówki zawiera mapy tabeli podstawowej, które działają wspólnie podczas interakcji, jak pokazano w poniższej tabeli.

| Aplikacje finansowe i operacyjne | Aplikacje Customer Engagement | Opis |
|-----------------------------|-----------------------------------|-------------|
[Wszystkie produkty](mapping-reference.md#138) | msdyn_globalproducts | |
[Odbiorcy (wersja 3)](mapping-reference.md#101) | Konta | |
[Odbiorcy (wersja 3)](mapping-reference.md#116) | kontakty | |
[Kontakty wersja 2](mapping-reference.md#221) | msdyn_contactforparties | |
[Nagłówki zamówień sprzedaży CDS](mapping-reference.md#217) | salesorders | |
[Wiersze zamówienia sprzedaży CDS](mapping-reference.md#216) | salesorderdetails | |
[Nagłówek oferty sprzedaży CDS](mapping-reference.md#215) | Cytaty | |
[Wiersze oferty sprzedaży CDS](mapping-reference.md#214) | quotedetails | |
[Zwolnione produkty (wersja 2)](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Nagłówki faktur sprzedaży wer. 2](mapping-reference.md#118) | faktury | Tabela nagłówków faktur sprzedaży (wersja 2) w aplikacji finansowej i operacyjnej zawiera faktury dla zamówień sprzedaży i faktury niezależne. W przypadku podwójnego zapisu jest stosowany filtr usługi Dataverse, który odfiltruje wszystkie dokumenty faktur niezależnych. |
[Wiersze faktur sprzedaży wer. 2](mapping-reference.md#117) | invoicedetails | |
[Kody źródeł zamówień sprzedaży](mapping-reference.md#186) | msdyn_salesorderorigins | |

Więcej informacji o cennikach, zobacz temat [Ujednolicone działanie produktu](product-mapping.md).

## <a name="limitations"></a>Ograniczenia

- Zamówienia zwrotu nie są obsługiwane.
- Faktury kredytowe nie są obsługiwane.
- Wymiary finansowe muszą być ustawione dla danych głównych, na przykład dla odbiorcy lub dostawcy. Gdy odbiorca jest dodawany do oferty lub zamówienia sprzedaży, wymiary finansowe skojarzone z rekordem odbiorcy automatycznie przepływają do zamówienia. Obecnie podwójny zapis nie uwzględnia danych wymiarów finansowych dla danych głównych.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

