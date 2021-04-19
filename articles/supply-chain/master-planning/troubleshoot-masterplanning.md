---
title: Rozwiązywanie problemów dotyczących planowania głównego
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z planowaniem głównym.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8e78634c0efb1c401297559ce40b2ca30519f3bf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809477"
---
# <a name="troubleshoot-master-planning"></a>Rozwiązywanie problemów dotyczących planowania głównego

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z planowaniem głównym.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>Rozłożenie listy składowej zachowuje się inaczej w przypadku ustalonych zleceń produkcyjnych i szacowanych zleceń produkcyjnych dla ręcznie utworzonych prac.

### <a name="issue-description"></a>Opis problemu

Po utrwaleniu zlecenia produkcyjnego towary nie są rozkładane podczas rozkłądania listy składowej (BOM). Jednak podczas ręcznego tworzenia zlecenia produkcyjnego, a następnie szacowania zlecenia produkcyjnego, towary są rozkładane.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

System działa zgodnie z oczekiwaniami. Rozłożenie występujące podczas ustalania zlecenia produkcyjnego wskazuje zamówienie planowane, ale zamówienie planowane chyba nie jest obecnie ustalone w tym przypadku. Jeśli jednak zlecenie produkcyjne zostało oszacowane, rozłożenie jest wyzwalane ze zwolnionego zlecenia produkcyjnego, w którym nie istnieje planowane zamówienie

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>Wartość Opóźnienia nie jest aktualizowana podczas ponownego planowania zamówienia planowanego.

Aby zaktualizować opóźnienie zamówień planowanych, otwórz okno dialogowe **Ponowne planowanie** dla zamówienia planowanego. Na skróconej karcie **Rozłożenie** należy upewnić się, że opcja **Wykonaj rozłożenie po zmianie harmonogramu** jest ustawiona na wartość *Tak*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>Planowanie produkcji nie uwzględnia marginesów bezpieczeństwa, które są ustawione dla pokrycia pozycji dla ustalonej dostawy.

### <a name="issue-description"></a>Opis problemu

Planowanie główne uwzględnia marginesy bezpieczeństwa. Jednak marginesy bezpieczeństwa są ignorowane podczas planowania zaplanowanych zleceń produkcyjnych.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Marginesy są brane pod uwagę tylko podczas planowania głównego, a nie w planowaniu ręcznym. Marginesy są tak zaprojektowane, aby pełniły charakter buforu podczas fazy planowania, co umożliwia podanie pewnego „marginesu” dla właściwego procesu.

Aby uzyskać pożądany wynik, można usunąć margines. Następnie należy zaktualizować marszrutę, aby obejmowała ona żądany czas (np. jako czas oczekiwania). Zarówno planowanie główne, jak i planowanie ręczne, powinny dawać ten sam wynik.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>Zamówienia planowane są generowane nawet wtedy, gdy istnieją towary w magazynie i istnieją już dla nich zlecenia produkcyjne.

Można rozwiązać ten problem, zwiększając wartość **Ilość dni z dodatnim stanem magazynu** dla odpowiednich grup na stronie **Grupa zapotrzebowania**. Ta zmiana spowoduje, że system określi, czy dla popytu można używać dostępnych zapasów. Wtedy nowe zamówienie planowane nie zostanie wygenerowane dla towarów znajdujących się w magazynie.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>Wydaje się, że planowanie główne nie uwzględnia ograniczeń zdolności produkcyjnej i obejmuje planowanie większe niż dostępna zdolność produkcyjna.

### <a name="issue-description"></a>Opis problemu

W przypadku korzystania z planowania operacji w przypadku, gdy wydajność jest ograniczona, a trasa określa mieszankę wymagań zarówno dla grupy zasobów, jak i dla poszczególnych zasobów, istnieje niewielka szansa na przepełnienie rezerwacji ze względu na sposób, w jaki algorytm sprawdza poprawność pod kątem konfliktów pojemności. Taka rezerwacja ponad możliwości może wystąpić podczas używania pomocników w celu uruchomienia planowania głównego. Najprawdopodobniej dzieje się tak, jeśli istnieje wiele zadań o stosunkowo krótkim czasie wykonywania.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jeśli konieczne jest, aby w planowaniu operacji nie dochodziło do przepełnienia rezerwacji, można uczynić planowanie jednowątkową częścią planowania głównego, włączając opcję **Dokładne ograniczone zdolności produkcyjne do planowania operacji** na stronie **Parametry planowania głównego**. Ta opcja jest domyślnie niedostępna. Musisz ręcznie dodać ją do strony, używając funkcji personalizacji. W przypadku korzystania z tej opcji planowanie będzie działać wolniej z powodu braku równoległego przetwarzania.

## <a name="planned-orders-take-a-long-time-to-update"></a>Aktualizacja zamówień planowanych zajmuje dużo czasu.

### <a name="issue-description"></a>Opis problemu

Podczas aktualizowania ilości zapotrzebowania i/lub daty dostawy w planowanym zamówieniu zapisanie aktualizacji zajmuje zwykle co najmniej 30 sekund na zamówienie.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to znany błąd dotyczący wbudowanego aparatu planowania głównego. Jest to spowodowane przez podstawowe automatyczne rozłożenie przez strukturę BOM podczas edycji. Ten problem rozwiązano w optymalizacji planowania, w której planista może aktualizować i zatwierdzać odpowiednie zamówienia oraz, w razie potrzeby, uruchamiać przebieg planowania w celu zaktualizowania zamówień planowanych dla podstawowej struktury BOM.

Jednym ze sposobów poprawienia wydajności przy użyciu wbudowanego aparatu planowania głównego jest wykonanie następujących czynności:

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz plan.
1. Rozwiń kartę skróconą **Horyzont czasowy w dniach**.
1. Ustawienie **Rozłożenie** na wartość *Tak* i ustawienie pola poniżej tego ustawienia na wartość 0 (zero).

> [!NOTE]
> Ograniczy to okres rozłożeń wykonywanych dla tego planu głównego do jednego dnia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]