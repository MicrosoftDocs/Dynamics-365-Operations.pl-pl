---
title: Zastępowanie materiałów w procesie produkcji
description: W tym temacie opisano sposób zastępowania materiałów w procesie produkcji.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 461b717acafb5ccf37acae23a1564069cea6828a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543452"
---
# <a name="material-substitution-in-manufacturing"></a>Zastępowanie materiałów w procesie produkcji

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zastępowania materiałów w procesie produkcji. 

Są trzy metody zastępowania materiałów w produkcji:

-   Według daty, kiedy jeden materiał jest zastępowany innym po określonej dacie
-   Podczas planowania głównego, gdy materiał w formule jest zastępowany innym materiałem, ponieważ jest on dostępny w magazynie
-   Podczas produkcji, gdy materiał nieoczekiwanie się wyczerpie i jest zastępowany innym materiałem

## <a name="substituting-material-by-date"></a>Zastępowanie materiału według daty
Rozważmy następujący scenariusz: maszyna produkowana przez firmę zawiera składnik, który za dwa miesiące zostanie wycofany z katalogu dostawcy. Później dostawca będzie oferował nowy składnik, który może zastąpić stary składnik. W wierszach listy składowej (BOM) można ustawić datę ważności „od” i „do”. W tym przykładzie konfiguruje się stary składnik, który ma zostać wycofany, wpisując datę ważności w polu **Do dnia**. Następnie w BOM definiuje się nowy składnik zastępczy, który będzie obowiązywał od dnia po wycofaniu starego komponentu. W tym celu należy wprowadzić datę początkową w **Od dnia**.

## <a name="substituting-material-by-planning"></a>Zastępowanie materiału podczas planowania
Materiały można zastąpić podczas planowania tylko za pomocą formuł, nie za pomocą BOM. Rozważmy następujący scenariusz: firma produkująca żywność wytwarza sos z formuły zawierającej 20 składników. Jeden składnik w formule można zastąpić jednym z dwóch innych składników. Ponieważ jednak te dwa składniki są droższe od preferowanej substancji, zastępowanie następuję tylko wtedy, gdy preferowanej substancji nie ma w magazynie. Materiał, który można zastąpić, nazywa się A, a dwa materiały, którym można go zastąpić, to B i C. Zastępowanie materiału podczas planowania jest konfigurowane za pomocą pól **Grupa planowania** i **Priorytet** w wierszach formuły. W tym przykładzie tworzone są wiersze formuły dla trzech materiałów i kojarzy się wiersze formuły z tą samą grupą planowania. W konfiguracji wiersz formuły dla materiału A ma najwyższy priorytet (najniższa liczba), wiersz formuły dla materiału C ma najniższy priorytet, a wiersz formuły dla materiału B ma priorytet znajdujący się między priorytetami dwóch pozostałych wierszy. Jeśli masz popyt dla gotowego towaru, planowanie główne najpierw określa, czy popyt na materiały A może zostać zaspokojony. Jeśli nie można zaspokoić popytu, planowanie główne analizuje materiały B i C według priorytetu. Jeśli materiał B jest dostępny, zostanie on użyty po ustaleniu planowanego zamówienia dla formuły. Jeśli żaden z materiałów nie jest dostępny, planowanie główne tworzy planowane zamówienie na materiał A. **Uwaga:** podczas konfigurowania wierszy formuły w grupie planowania należy określić ilość tylko w przypadku materiału, który ma najwyższy priorytet. Ta ilość zostanie użyta do obliczania popytu na wszystkie materiały w planie, także na materiały o niższym priorytecie. Nie można określić innych ilości dla pozycji o niższym priorytecie w grupie planowania.

## <a name="substituting-material-during-production"></a>Zastępowanie materiału podczas produkcji
Rozważmy następujący scenariusz: do spawania potrzebna jest metalowa płytka. W trakcie realizacji zadania pracownik magazynu informuje operatora maszyny, że zapasy płytki się wyczerpały. Zapada jednak decyzja, że płytkę można zastąpić inną płytką, która jest trochę cieńsza. Dzięki temu zadanie może zostać ukończone. Materiał można dodać do BOM dla otwartego zlecenia produkcyjnego. Jeżeli zlecenie produkcyjne ma stan **Rozpoczęte**, użytkownik musi ponownie oszacować zlecenie w chwili dodania nowego towaru do BOM produkcji. Po dodaniu materiału dla nowej pozycji można utworzyć nową listę pobrania. Nie trzeba dodawać nowego materiału do BOM produkcji. Zamiast tego można go dodać bezpośrednio do listy pobrania produkcji. Następnie podczas księgowania listy pobrania system doda materiał do BOM produkcji.



