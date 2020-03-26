---
title: Omówienie podatku
description: Ten temat zawiera omówienie systemu podatków. Objaśniono w nim elementy konfiguracji podatku od sprzedaży oraz ich współdziałanie.
author: ShylaThompson
manager: AnnBe
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e827ede0508d07b6800ecdc4cc99cb2b6a0bcc78
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124504"
---
# <a name="sales-tax-overview"></a>Omówienie podatku

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie systemu podatków. Objaśniono w nim elementy konfiguracji podatku od sprzedaży oraz ich współdziałanie.

<a name="overview"></a>Przegląd
--------

Struktura podatku obsługuje wiele różnych rodzajów podatków pośrednich, takich jak podatek, podatek od wartości dodanej (VAT), podatek od towarów i usług (GST), opłaty oparte na jednostce i potrącona zaliczka na podatek. Te podatki są obliczane i dokumentowane podczas transakcji zakupów i sprzedaży. Okresowo należy je zgłaszać i wpłacać do urzędu skarbowego. 

Na poniższym diagramie przedstawiono jednostki podatku i jak są powiązane.

[![Diagram przedstawiający omówienie jednostek konfiguracji podatku](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Dla każdego podatku, z którego firma musi się rozliczać, należy zdefiniować kod. Kody podatku zawierają stawki podatku oraz zasady obliczania dla każdego podatku. 

Każdy kod podatku musi być połączony z okresem rozliczania podatku. Okresy rozliczania podatku definiują interwały, w których należy zgłaszać i płacić podatek w urzędzie skarbowym. Każdy okres rozliczania podatku musi być przypisany do urzędu skarbowego. Urząd skarbowy to podmiot, w którym zgłasza się i opłaca podatek. Definiuje również układ raportu podatku. Urzędy skarbowe mogą być związane z kontami dostawców. Aby uzyskać więcej informacji, zobacz [Ustawianie okresów rozliczania podatku](tasks/set-up-sales-tax-settlement-periods.md).

Każdy kod podatku musi być również połączony z grupą księgowania w księdze. Grupa księgowania w księdze określa konta główne, na których są księgowane kwoty dla kodów podatku. 

Można również określić opcjonalne kody raportowania podatku. Można je przypisać w kodach podatku dla różnych typów kwot, które są obliczane dla kodu podatku. Raport **Płatności podatku według kodu** zawiera sumy według kodu raportowania podatku dla wybranego okresu i interwału rozliczania podatku. 

W każdej transakcji, która wymaga obliczenia i zaksięgowania podatku, trzeba ustawić grupę podatku i grupę podatków dla towaru. Grupy podatków są związane ze stroną (np. odbiorcą lub dostawcą) transakcji, podczas gdy grupy podatków dla towaru są powiązane z zasobami (np. kategoriami zaopatrzenia lub towaru) transakcji. Grupy podatków zawierają listę kodów podatków. Kody podatków obecne i w grupie podatku i w grupie podatku dla towaru w transakcji są kodami podatku obowiązującymi w tej transakcji. 

W poniższej tabeli opisano jednostki i kolejność konfiguracji podatku.

| Działanie konfiguracyjne                                                  | Wskaźnik wymagane/opcjonalne oraz opis                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie kont głównych.                                           | Wymagane. Przed rozpoczęciem konfigurowania funkcji podatku należy utworzyć konta główne używane w firmie do płacenia i rejestrowania podatków.                                                                                                                                                                             |
| Skonfiguruj grupy księgowania w księdze dla podatku.                     | Wymagane. Grupy księgowania definiują konta główne do rejestrowania i płacenia podatków.   Aby uzyskać więcej informacji, zobacz [Konfigurowanie grup księgowania dla podatku](tasks/set-up-ledger-posting-groups-sales-tax.md)                                                                                 |
| Skonfiguruj urzędy skarbowe.                                   | Wymagane. Urzędy skarbowe są jednostkami, w których podatek musi zostać zgłoszony i zapłacony.    Aby uzyskać więcej informacji, zobacz [Konfigurowanie urzędów skarbowych](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Ustawianie okresów rozliczania podatku.                            | Wymagane. Okresy rozliczenia podatku informują kiedy i jak często podatek musi być zgłaszany i opłacany. Odnoszą się one do urzędu skarbowego.                                                                                                                                                       |
| Konfigurowanie kodów raportowania podatku.                               | Opcjonalne. Kody raportowania podatku można przypisać do kodów podatku w celu raportowania kwoty dla wielu kodów podatku w jednym kodzie raportowania podatku. Aby uzyskać więcej informacji, zobacz [Ustawianie kodów raportowania podatku](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Ustawianie kodów podatków.                                         | Wymagane. Kody podatku zawierają stawki podatku oraz zasady obliczania dla każdego podatku. Kody podatku są powiązane z okresem rozliczania podatku oraz grupę księgowania w księdze. Aby uzyskać więcej informacji, zobacz [Konfigurowanie kodów podatków](tasks/set-up-sales-tax-codes.md).                                |
| Konfigurowanie grup podatków.                                        | Wymagane. Grupy podatków zawierają listę kodów sprzedaży dotyczącą strony (odbiorcy lub dostawcy) transakcji. Dla danej transakcji część wspólna kodów podatku w grupie podatku i grupie podatków od towaru określa kody podatku obowiązujące w tej transakcji.                  |
| Ustawianie grup podatków dla pozycji.                                   | Wymagane. Grupy podatków dla towarów zawierają listę kodów sprzedaży obowiązujących w przypadku zasobu (produktu, usługi itd.) transakcji. Dla danej transakcji część wspólna kodów podatku w grupie podatku i grupie podatków od towaru określa kody podatku obowiązujące w tej transakcji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie grup podatków i grup podatków dla towarów](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Konfigurowanie parametrów podatkowych na stronach parametrów aplikacji. | Wymagane. Różne obszary, takie jak Księga główna, Rozrachunki z odbiorcami i Rozrachunki z dostawcami, muszą określać parametry do prawidłowego obliczania podatków pośrednich. Mimo że większość z tych parametrów ma wartości domyślne, muszą one zostać dostosowane od wymagań każdej firmy.                                          |

## <a name="sales-tax-on-transactions"></a>Podatek od transakcji
Dla każdej transakcji (wierszy dokumentu sprzedaży/zakupu, arkuszy itd) należy wprowadzić grupę podatków i grupę podatków dla towaru do obliczania podatku od sprzedaży. Domyślne grupy są określone w danych głównych (na przykład nabywcy, dostawcy, towary i kategoria zaopatrzenia), ale można ręcznie zmienić grupy w transakcji. Obydwie grupy zawierają listę kodów podatku, a część wspólna obu list kodów podatku określa listę obowiązujących kodów podatku dla danej transakcji. 

Dla każdej transakcji można wyszukać obliczony podatek, otwierając stronę **transakcji podatku**. Można wyszukać podatek dla wiersza dokumentu lub całego dokumentu. W przypadku niektórych dokumentów (na przykład faktury od dostawcy i arkuszy finansowych) można skorygować podatek, jeśli oryginalny dokument wskazuje rozbieżne kwoty.

## <a name="sales-tax-settlement-and-reporting"></a>Rozliczanie i raportowanie podatku
Podatek należy zgłosić i zapłacić w urzędzie skarbowym w ustalonych interwałach (miesięcznie, kwartalnie itd.). Zawiera funkcje, które umożliwiają rozliczanie kont podatku za okres, a następnie ustawienie salda jako przeciwstawne na koncie rozliczania podatku, jak określono w grupach księgowania księgi. Dostęp do tej funkcji można uzyskać na stronie **Rozlicz i zaksięguj podatek**. Należy określić okres rozliczania podatku, dla którego ma być rozliczony podatek. 

Po zapłaceniu podatku saldo na koncie rozliczania podatku należy skorygować względem konta bankowego. Jeśli urząd skarbowy wskazany dla okresu rozliczania podatku jest związany z kontem dostawcy, saldo podatku jest księgowane jako otwarta faktura od dostawcy i może być uwzględnione w normalnej propozycji płatności.

## <a name="conditional-sales-tax"></a>Podatek warunkowy
Podatek warunkowy to podatek płacony proporcjonalnie do rzeczywistej kwoty zapłaconej z tytułu faktury. Z kolei standardowy podatek jest obliczany podczas fakturowania. Podatki warunkowe należy wpłacać do urzędu skarbowego po zaksięgowaniu otrzymanej wpłaty, a nie faktury. Po zaksięgowaniu faktury transakcję należy wykazać w raporcie księgi podatkowej. Jednak transakcji nie można wykazać w raporcie zapłaty podatku. 

Jeśli w formularzu Parametry księgi głównej zaznaczono pole wyboru Podatek warunkowy, podatek można odliczyć dopiero po zapłaceniu faktury. Jest to prawny wymóg w niektórych krajach/regionach.

> [!NOTE]
> Po zaznaczeniu pola wyboru Podatek warunkowy musisz skonfigurować kody podatków i grupy podatków oraz utworzyć grupy księgowania w księdze. |

###  <a name="example"></a>Przykład

Rozliczasz podatki co miesiąc. 15 czerwca utworzono fakturę dla odbiorcy na kwotę 10 000 plus podatek.
-   Podatek wynosi 25 procent, czyli 2,500.
-   Fakturę należy zapłacić do 30 lipca.

Zazwyczaj trzeba rozliczyć i zapłacić podatek 2500 do urzędu skarbowego po zaksięgowaniu faktury w czerwcu, mimo że nie masz jeszcze wpłaty od odbiorcy. 

Jednakże jeśli używasz podatku warunkowego, rozliczasz się z urzędem skarbowym po otrzymaniu zapłaty od odbiorcy w dniu 30 lipca.

### <a name="postdated-check"></a>Czek postdatowany

Jeśli jako metoda płatności jest używany czek postdatowany, w momencie utworzenia płatności konto bankowe nie zostanie rozliczone. W niektórych krajach podatek VAT staje się zobowiązaniem „zrealizowanym”, gdy płatność jest rozliczana przez bank, co oznacza, że czek postdatowany został rozliczony. Tę funkcję można włączyć, wybierając opcję **Realizuj podatek warunkowy w momencie wystawiania czeków postdatowanych** w obszarze **Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami > Czeki postdatowane**.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie potrąconych zaliczek na podatek](tasks/set-up-withholding-tax.md).
