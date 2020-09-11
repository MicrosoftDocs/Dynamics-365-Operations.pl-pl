---
title: Optymalizacja zadań wsadowych BYOD w harmonogramie
description: W tym temacie wyjaśniono, jak optymalizować wydajność, gdy jest używana funkcja „Dobierz własną bazę danych (BYOD)” w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: d08762ff40b4da8264bd5bc4a1c16fd2afc4d610
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712620"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Optymalizacja zadań wsadowych BYOD w harmonogramie

W tym temacie wyjaśniono, jak optymalizować wydajność, gdy jest używana funkcja „Dobierz własną bazę danych (BYOD)”. Aby uzyskać więcej informacji o BYOD, zapoznaj się z tematem [Dobierz własną bazę danych (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json).

## <a name="performance-considerations-for-data-export"></a>Zagadnienia dotyczące wydajności eksportu danych

Po opublikowaniu jednostek w docelowej bazie danych można skorzystać z funkcji eksportu w obszarze roboczym **Zarządzanie danymi**, aby przenieść dane. Funkcja eksportu umożliwia zdefiniowanie zadania przenoszenia danych, które zawiera jedną lub więcej encji. Aby uzyskać więcej informacji o funkcji zarządzania danymi do eksportowania danych, zapoznaj się z [Omówieniem importowania i eksportowania danych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json).

Strony **Eksport** można używać do eksportowania danych do różnych docelowych formatów danych, takich jak plik CSV (wartości rozdzielane przecinkami). Ta strona obsługuje również bazy danych SQL jako inne miejsce docelowe.

Istnieje możliwość utworzenia projektu danych, który ma wiele jednostek, i użycia zadania wsadowego w celu zaplanowania działania tego projektu danych. W przypadku wybrania opcji **Eksportuj w partii** można zaplanować zadanie eksportu danych, które będzie uruchamiane okresowo.

Aby zachować ogólną wiarygodność eksportu BYOD, należy zachować ostrożność podczas dodawania wielu jednostek do projektu eksportu. Podczas określania liczby jednostek, które mają zostać dodane do tego samego projektu, należy wziąć pod uwagę następujące parametry:

- Złożoność encji
- Oczekiwany wolumen danych na jednostkę
- Całkowity czas wymagany do zakończenia eksportu na poziomie zadania

Aby osiągnąć najlepszą wydajność, należy unikać dodawania setek jednostek do jednego projektu. Zaleca się utworzenie wielu zadań, z których każdy zawiera mniej jednostek.

## <a name="scheduling-byod-batch-jobs"></a>Planowanie zadań wsadowych BYOD

Aby zmniejszyć wpływ na użytkowników systemu Microsoft Dynamics 365 Human Resources, należy uruchomić zadania wsadowe BYOD w nocy lub po godzinach. Należy sprawdzić strefę czasową cyklicznych zadań wsadowych. Niektóre zadania wsadowe mogą wykorzystywać standardowy czas pacyficzny (PST).

Aby uniknąć problemów z wydajnością, podczas konfigurowania częstotliwości planowania dla zadań wsadowych BYOD należy wziąć pod uwagę następujące czynniki:

- Czas wymagany do ukończenia każdego zadania wsadowego
- Zapotrzebowanie na firmę dla danych w BYOD

Umożliwia ustawienie częstotliwości dla każdego zadania wsadowego na wartość, która zapewnia, że zadanie będzie można zakończyć przed następnym zaplanowanym czasem uruchomienia. Unikaj uruchamiania wielu zadań równolegle, ponieważ może to mieć negatywny wpływ na wydajność Human Resources.

Aby uzyskać najlepszą wydajność, należy zawsze stosować opcję **Eksportuj w partii** na stronie **Eksport**, aby zaplanować zadania wsadowe BYOD. Unikaj planowania cyklicznych eksportów poprzez **Zarządzanie \> Zarządzanie cyklicznymi zadaniami danych**.

## <a name="incremental-export"></a>Eksportowanie przyrostowe

Podczas dodawania jednostki do eksportu danych można wykonać zarówno operację przyrostową (eksport), jak i pełne wypychanie. Pełna wypychanie powoduje usunięcie wszystkich istniejących rekordów z jednostki w bazie danych BYOD. Następnie wstawia bieżący zbiór rekordów z encji Human Resources.

Aby wykonać operację wypychania przyrostowego, należy włączyć śledzenie zmian dla każdej encji na stronie **Encje**. Aby uzyskać więcej informacji, przejrzyj temat [Włączanie śledzenia zmian dla encji](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

W przypadku wybrania opcji wypychania przyrostowego pierwszy punkt wypychania będzie zawsze pełnym wypychaniem. Program SQL śledzi te zmiany z pierwszego pełnego wypychania. Po wstawieniu nowego rekordu lub po zaktualizowaniu lub usunięciu rekordu, zmiana jest odzwierciedlana w encji docelowej.

## <a name="time-outs"></a>Limity czasu

Oto domyślne limity czasu dla eksportu BYOD:

- Dziesięć minut dla operacji obcinania
- Jedna godzina dla operacji wstawiania zbiorczego

Gdy ilość danych jest bardzo duża, te ustawienia limitu czasu mogą być niewystarczające. Aby je zaktualizować, przejdź do **Zarządzania danymi \> Ustawienia ramowe \> Wprowadzanie własnej bazy danych**. Te limity czasu są specyficzne dla firmy i muszą być ustawiane osobno dla każdej firmy.

## <a name="known-limitations"></a>Znane ograniczenia

Funkcja BYOD ma następujące ograniczenia:

- Podczas synchronizacji nie powinno być aktywnych blokad w bazie danych. Aktywne blokady mogą powodować powolne zapisy lub nawet niepowodzenie w eksportowaniu danych do bazy danych SQL Azure.
- Nie można eksportować jednostek złożonych do własnej bazy danych. Obecnie jednostki złożone nie są obsługiwane. Należy eksportować poszczególne jednostki składające się na jednostkę złożoną. Można jednak eksportować obie jednostki z tego samego projektu danych.
- Jednostki, które nie mają unikatowych kluczy, nie mogą być eksportowane za pomocą polecenia wypychania przyrostowego. Ograniczenie to może być szczególnie przydatne podczas próby stopniowego eksportowania rekordów z kilku gotowych jednostek. Ponieważ te jednostki zostały zaprojektowane w celu umożliwienia importowania danych, nie mają unikatowego klucza.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="incremental-push-doesnt-work-correctly"></a>Wypychanie przyrostowe nie działa poprawnie

**Problem:** Podczas wykonywania pełnego wypychania dla danej encji widoczne jest wiele rekordów BYOD po wybraniu instrukcji **wybierz**. Jednak w przypadku wypychania przyrostowego widoczna jest tylko liczba rekordów w BYOD. Wygląda na to, jakby przyrostowa metoda wypychania usunęła wszystkie rekordy i dodała tylko zmienione rekordy w BYOD.

**Rozwiązanie:** tabele śledzenia zmian SQL mogą nie znajdować się w oczekiwanym stanie. W przypadku tego typu sytuacji zaleca się wyłączenie śledzenia zmian dla jednostki, a następnie włączenie funkcji z powrotem. Aby uzyskać więcej informacji, przejrzyj temat [Włączanie śledzenia zmian dla encji](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie zarządzania danymi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages?toc=/dynamics365/human-resources/toc.json)<br>
[Używanie własnej bazy danych (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json)<br>
[Omówienie zadań importowania i eksportowania danych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json)<br>
[Włączanie śledzenia zmian dla jednostek](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json)
