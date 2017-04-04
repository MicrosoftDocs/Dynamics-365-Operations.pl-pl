---
title: "Omówienie podatku"
description: "Ten artykuł zawiera omówienie systemu podatków. Objaśniono w nim elementy konfiguracji podatku od sprzedaży oraz ich współdziałanie."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 1adee145d705f239e0c663d310234286478fead0
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-overview"></a>Omówienie podatku

Ten artykuł zawiera omówienie systemu podatków. Objaśniono w nim elementy konfiguracji podatku od sprzedaży oraz ich współdziałanie.

<a name="overview"></a>Przegląd
--------

Platforma podatku obsługuje wiele rodzajów podatków pośrednich, takich jak podatek od sprzedaży, podatku od wartości dodanej (VAT), podatek towarów i usług (GST), opłat opartego na jednostkę i potrąconej zaliczki na podatek. Te podatki są obliczane i udokumentowane w trakcie transakcji zakupu i sprzedaży. Okresowo muszą być zgłaszane i wypłacane do organów podatkowych. 

Na poniższym diagramie przedstawiono jednostki podatku i jak są powiązane.

[![TaxOverview](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Dla którego konieczne jest uwzględnienie firmy co podatku musi być zdefiniowany kod podatku. Kody podatku zawierają stawki podatku oraz zasady obliczania dla każdego podatku. 

Każdy kod podatku musi być połączony z okresem rozliczania podatku. Okresy rozliczania podatku definiują interwały, w których należy zgłaszać i płacić podatek w urzędzie skarbowym. Każdy okres rozliczania podatku musi być przypisany do urzędu skarbowego. Urząd skarbowy to podmiot, w którym zgłasza się i opłaca podatek. Definiuje również układ raportu podatku. Urzędy skarbowe mogą być związane z kontami dostawców. 

Każdy kod podatku musi być również połączony z grupą księgowania w księdze. Grupa księgowania w księdze określa konta główne, na których są księgowane kwoty dla kodów podatku. 

Można również określić opcjonalne kody raportowania podatku. Można je przypisać w kodach podatku dla różnych typów kwot, które są obliczane dla kodu podatku. Raport **Płatności podatku według kodu** zawiera sumy według kodu raportowania podatku dla wybranego okresu i interwału rozliczania podatku. 

W każdej transakcji, która wymaga obliczenia i zaksięgowania podatku, trzeba ustawić grupę podatku i grupę podatków dla towaru. Grupy podatków są związane ze stroną (np. odbiorcą lub dostawcą) transakcji, podczas gdy grupy podatków dla towaru są powiązane z zasobami (np. kategoriami zaopatrzenia lub towaru) transakcji. Grupy podatków zawierają listę kodów podatków. Kody podatków obecne i w grupie podatku i w grupie podatku dla towaru w transakcji są kodami podatku obowiązującymi w tej transakcji. 

W poniższej tabeli opisano jednostki i kolejność konfiguracji podatku.

| Działanie konfiguracyjne                                                  | Wskaźnik wymagane/opcjonalne oraz opis                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie kont głównych.                                           | Wymagane. Przed rozpoczęciem konfigurowania funkcji podatku należy utworzyć konta główne używane w firmie do płacenia i rejestrowania podatków.                                                                                                                                                                             |
| Skonfiguruj grupy księgowania w księdze dla podatku.                     | Wymagane. Grupy księgowania definiują konta główne do rejestrowania i płacenia podatków.                                                                                                                                                                                                                            |
| Skonfiguruj urzędy skarbowe.                                   | Wymagane. Urzędy skarbowe są jednostkami, w których podatek musi zostać zgłoszony i zapłacony.                                                                                                                                                                                                                                   |
| Ustawianie okresów rozliczania podatku.                            | Wymagane. Okresy rozliczenia podatku informują kiedy i jak często podatek musi być zgłaszany i opłacany. Odnoszą się one do urzędu skarbowego.                                                                                                                                                       |
| Konfigurowanie kodów raportowania podatku.                               | Opcjonalne. Kody raportowania podatku można przypisać do kodów podatku w celu raportowania kwoty dla wielu kodów podatku w jednym kodzie raportowania podatku.                                                                                                                                                                 |
| Ustawianie kodów podatków.                                         | Wymagane. Kody podatku zawierają stawki podatku oraz zasady obliczania dla każdego podatku. Kody podatku są powiązane z okresem rozliczania podatku oraz grupę księgowania w księdze.                                                                                                                                        |
| Konfigurowanie grup podatków.                                        | Wymagane. Grupy podatków zawierają listę kodów sprzedaży dotyczącą strony (odbiorcy lub dostawcy) transakcji. Dla danej transakcji część wspólna kodów podatku w grupie podatku i grupie podatków od towaru określa kody podatku obowiązujące w tej transakcji.                  |
| Ustawianie grup podatków dla pozycji.                                   | Wymagane. Grupy podatków dla towarów zawierają listę kodów sprzedaży obowiązujących w przypadku zasobu (produktu, usługi itd.) transakcji. Dla danej transakcji część wspólna kodów podatku w grupie podatku i grupie podatków od towaru określa kody podatku obowiązujące w tej transakcji. |
| Konfigurowanie parametrów podatkowych na stronach parametrów aplikacji. | Wymagane. Różne obszary, takie jak Księga główna, Rozrachunki z odbiorcami i Rozrachunki z dostawcami, muszą określać parametry do prawidłowego obliczania podatków pośrednich. Mimo że większość z tych parametrów ma wartości domyślne, muszą one zostać dostosowane od wymagań każdej firmy.                                          |

## <a name="sales-tax-on-transactions"></a>Podatek od transakcji
Dla każdej transakcji (wierszy dokumentu sprzedaży/zakupu, arkuszy itd) należy wprowadzić grupę podatków i grupę podatków dla towaru do obliczania podatku od sprzedaży. Domyślne grupy są określone w danych głównych (na przykład nabywcy, dostawcy, towary i kategoria zaopatrzenia), ale można ręcznie zmienić grupy w transakcji. Obydwie grupy zawierają listę kodów podatku, a część wspólna obu list kodów podatku określa listę obowiązujących kodów podatku dla danej transakcji. 

Dla każdej transakcji można wyszukać obliczony podatek, otwierając stronę **transakcji podatku**. Można wyszukać podatek dla wiersza dokumentu lub całego dokumentu. W przypadku niektórych dokumentów (na przykład faktury od dostawcy i arkuszy finansowych) można skorygować podatek, jeśli oryginalny dokument wskazuje rozbieżne kwoty.

## <a name="sales-tax-settlement-and-reporting"></a>Rozliczanie i raportowanie podatku
Podatek należy zgłosić i zapłacić w urzędzie skarbowym w ustalonych interwałach (miesięcznie, kwartalnie itd.). Microsoft Dynamics 365 dla operacji zawiera funkcje, które umożliwia rozliczenia podatku dla interwału i przesunięcie salda na konto rozliczeniowe podatku, jak określono w grup księgowania w księdze. Dostęp do tej funkcji na **rozliczenia i księgowanie podatku** strony. Należy określić okres rozliczania podatku, który powinien rozliczenia podatku dla. 

Po zapłaceniu podatku saldo na koncie rozliczania podatku należy skorygować względem konta bankowego. Jeśli urząd skarbowy wskazany dla okresu rozliczania podatku jest związany z kontem dostawcy, saldo podatku jest księgowane jako otwarta faktura od dostawcy i może być uwzględnione w normalnej propozycji płatności.

## <a name="conditional-sales-tax"></a>Podatek warunkowy
Podatek warunkowy jest podatek od sprzedaży, która jest wypłacana proporcjonalnie do rzeczywistej kwoty płaconej na fakturze. I odwrotnie standardowy podatek jest obliczany podczas fakturowania. Po zaksięgowaniu płatności, nie, po zaksięgowaniu faktury podatku warunkowego należy zwrócić do urzędu skarbowego. Po zaksięgowaniu faktury transakcji należy podać w raporcie księgi podatkowej. Jednak transakcja musi być wykluczony z raportu płatności podatku. 

Po zaznaczeniu pola wyboru podatku warunkowego w formularzu Parametry księgi głównej, bez podatku od sprzedaży można odliczyć uiszczenia faktury. Jest to wymóg prawny w niektórych krajach/regionach.

> [!NOTE]
> Po zaznaczeniu pola wyboru podatku warunkowego, musi ustawiania kodów podatków i grup podatków, a także grupy księgowania można tworzyć, do obsługi funkcji. |

###  <a name="example"></a>Przykład

Podatki są rozliczane co miesiąc. 15 czerwca Utwórz fakturę dla odbiorcy 10 000 plus podatek od sprzedaży.
-   Podatek wynosi 25 procent lub 2 500 zł.
-   Płatność faktury jest wynikiem 30 lipca.

Zazwyczaj trzeba się osadowi zapłacić 2500 do urzędu skarbowego po zaksięgowaniu faktury w czerwcu, mimo że nie otrzymał płatności od odbiorcy. 

Jednakże jeśli używasz podatku warunkowego są rozliczane z urzędem skarbowym po otrzymaniu płatności od odbiorcy 30 lipca.


