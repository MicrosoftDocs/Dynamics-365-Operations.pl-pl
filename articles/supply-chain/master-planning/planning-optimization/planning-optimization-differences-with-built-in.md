---
title: Różnice między optymalizacją planowania i przestarzałym aparatem planowania głównego
description: W tym artykule wymieniono funkcje, których optymalizacja planowania jeszcze nie obsługuje, a które nie są wymienione na stronie Analiza dopasowań optymalizacji planowania.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745369"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Różnice między optymalizacją planowania i przestarzałym aparatem planowania głównego

[!include [banner](../../includes/banner.md)]

Wyniki optymalizacji planowania mogą różnić się od wyników przestarzałego aparatu planowania głównego. Różnice mogą być spowodowane przez oczekujące funkcje. W tym artykule wymieniono funkcje, których optymalizacja planowania jeszcze nie obsługuje, a które nie są wymienione na stronie **[Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md)**].

| Funkcja | Bieżące zachowanie w optymalizacji planowania |
|---|---|
| Produkty ilości efektywnej | Produkty ilości efektywnej są uważane za zwykłe produkty.|
| Rozszerzalne wymiary | Optymalizacja planowania nie obsługuje wymiarów rozszerzalnych. Podczas używania optymalizacji planowania wymiary rozszerzalne są puste w zamówieniach planowanych, nawet jeśli zaznaczono pole wyboru **Plan zapotrzebowania według wymiaru** na stronie **Grupy wymiarów magazynowania** lub **Grupy wymiarów śledzenia**. |
| Filtrowane przebiegi produkcyjne | Szczegółowe informacje zawiera temat [Planowanie produkcji — filtry](production-planning.md#filters). |
| Planowanie prognozy | Planowanie prognozy nie jest obsługiwane. Zaleca się korzystanie z planowania głównego, w którym model prognozy jest przypisany do planu głównego. |
| Sekwencje numerów planowanych zamówień | Sekwencje numerów planowanych zamówień nie są obsługiwane. Numery planowanych zamówień są generowane po stronie usługi. Numer planowanego zamówienia zazwyczaj składa się z 10 cyfr, jednak sekwencja składa się z 20 znaków, 10 cyfr przypisanych do liczby przebiegów planowania, a pozostałych 10 cyfr dla liczby zamówień planowanych. |
| Kopiowanie planu, usuwanie planu i czyszczenie wersji planu | <p>Następujące elementy są wyłączone w obszarze **Planowanie główne \> Planowanie główne \> Obsługa planów** w okienku nawigacji:</p><ul><li>Kopiowanie planu</li><li>Usuń plan</li><li>Oczyszczanie wersji planu</li></ul> |
| Zamówienia zwrotu | Zamówienia zwrotu nie są rozpatrywane. |
| Funkcje związane z planowaniem | Szczegółowe informacje zawiera temat [Planowanie z nieskończoną pojemnością](infinite-capacity-planning.md#limitations). |
| Realizacja zapasu bezpieczeństwa | Optymalizacja planowania zawsze używa opcji *Dzisiejsza data + czas zamówienia* w polu **Zrealizuj minimum** na stronie **Pokrycie pozycji**. Pomaga to zapobiegać niechcianym zamówieniom planowanym i innym problemom, ponieważ jeśli czas zaopatrzenia nie jest uwzględniony w przypadku zapasów bezpieczeństwa, zamówienia planowane tworzone dla niskich zapasów byłyby zawsze opóźnione ze względu na czas realizacji. |
| Ustalanie zapasów bezpieczeństwa i wymagania dotyczące sieci | Typ *zapotrzebowania na zapas bezpieczeństwa* nie jest uwzględniony i nie jest wyświetlany na stronie **Zapotrzebowanie netto**. Zapas bezpieczeństwa nie reprezentuje popytu i nie ma skojarzonej z nim daty zapotrzebowania. Określa natomiast ograniczenia dotyczące ilości zapasów, jaka musi być obecna przez cały czas. Jednak wartość pola **Minimum** jest nadal uwzględniana podczas obliczania zamówień planowanych podczas planowania głównego. Aby sprawdzić, czy ta wartość została względna, należy sprawdzić kolumnę **Skumulowana ilość** na stronie **Wymagania netto**. Ponieważ oznaczanie transakcji odbywa się w różny sposób, mogą być proponowane różne akcje. |
| Kalendarze transportu | Wartość w kolumnie **Kalendarz transportu** na stronie **Tryby dostawy** jest ignorowana. |
| Kod zapotrzebowania minimum/maksimum bez wartości| W przypadku przestarzałego planowania głównego, gdy używany jest kod minimalnego/maksymalnego pokrycia, w którym nie ustawiono wartości minimalnych ani maksymalnych, aparat planowania traktuje kod pokrycia jako wymaganie i tworzy jedno zamówienie dla każdego wymagania. Dzięki optymalizacji planowania system utworzy jedno zamówienie na dzień, aby pokryć pełną kwotę za ten dzień.  |
| Wymagania netto i ręcznie tworzone planowane zamówienia | W przestarzałym silniku planowania głównego ręcznie utworzone zamówienia na dostawy dla pozycji automatycznie pojawiają się wśród wymagań netto dla tej pozycji. Na przykład podczas tworzenia zamówienia zakupu na podstawie zamówienia sprzedaży, zamówienie zakupu pojawia się na stronie **Wymagania netto**, nie wymagając żadnych wcześniejszych działań. Dzieje się tak, ponieważ przestarzały silnik planowania głownego rejestruje transakcje inwentaryzacyjne w tabeli `inventLogTTS` i pokazuje zmiany na stronie **Potrzeby netto** dla planów dynamicznych. Jednak w przypadku Optymalizacji planowania ręcznie utworzone zamówienia nie pojawią się wśród wymagań netto pozycji, dopóki nie zostanie uruchomiona Optymalizacja planowania (z użyciem planu, który zawiera daną pozycję) lub dopóki nie wybierzesz **Uaktualnij \> Planowanie główne** na panelu akcji na stronie **Wymagania netto**, co spowoduje uruchomienie planowania głównego dla danej pozycji. Aby uzyskać więcej informacji na temat pracy ze stroną **Wymagania netto**, zobacz [Wymagania netto i informacje o kołkowaniu](net-requirements.md). |
| Przydział zasobów | Podczas pracy z nieskończoną zdolnością produkcyjną przestarzały aparat planowania głównego przypisuje wszystkie planowane zamówienia do tego samego zasobu w danej grupie zasobów. Optymalizacja planowania usprawnia ten proces, wybierając zasoby losowo, aby różne zlecenia produkcyjne wykorzystywały różne zasoby. Aby do wszystkich planowanych zamówień użyć tego samego zasobu, należy określić ten zasób w marszrucie. |
| Rozszerzone typy danych (EDT) | Optymalizacja planowania nie obsługuje zmian zgodnie z dokładnością EDT. Oznacza to, że ten proces nie jest oficjalnie obsługiwany i nie jest gwarantowany do pracy. |
| Realizacja zapasu bezpieczeństwa | Optymalizacja planowania zawsze używa **Uzupełnij stany minimalne** o wartości  *Daty dzisiejszej + czasu zaopatrzenia*. Przygotowuje to system do korzystania w przyszłości z uproszczonej konfiguracji planowania i zapewnia wynik, który można wykorzystać w działaniu. Jeśli czas zaopatrzenia nie jest uwzględniony w zapasach bezpieczeństwa, zamówienia planowane utworzone dla niskiego stanu zapasów będą zawsze opóźnione z powodu czasu realizacji. To zachowanie może spowodować powstanie istotnych zakłóceń i niechcianych zamówień planowanych. Najlepszym rozwiązaniem jest zmiana tego ustawienia, tak aby była używana *Data dzisiejsza + czas zaopatrzenia*. Zaktualizuj dane podstawowe, aby uniknąć ostrzeżeń. |
| Kopiuj plan statyczny do dynamicznego | Optymalizacja planowania nie kopiuje planów statycznych do planów dynamicznych, niezależnie od ustawienia na stronie **Parametry planowania głównego**. Ogólnie rzecz biorąc, ta operacja jest mniej istotna ze względu na szybkość i pełną regenerację, którą zapewnia Optymalizacja planowania. Jeśli użyto dwóch lub więcej planów, planowanie główne powinno być wyzwalane dla każdego planu. |

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md)
- [Parametry nieużywane przez optymalizację planowania](not-used-parameters.md)
- [Parametry daty i godziny używane przez optymalizację planowania](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
