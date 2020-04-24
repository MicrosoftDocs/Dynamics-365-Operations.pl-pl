---
title: Cykl zamówienia partii od utworzenia do rozpoczęcia
description: Ta procedura prowadzi Cię przez pierwszą częścią cyklu życia szarży produkcyjnej.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16b55726fdb9ab15e74a9f752cac972b80a98de2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210992"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Cykl zamówienia partii od utworzenia do rozpoczęcia

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi Cię przez pierwszą częścią cyklu życia szarży produkcyjnej.

Od utworzenia, oszacowania kosztów i zaplanowania zadań produkcyjnych, aż do rzeczywistego rozpoczęcia szarży.



Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. 



Warunkiem wstępnym wykonania tej procedury przy użyciu innego zestawu danych jest istnienie zwolnionego produktu z aktywną formułą i wersją marszruty.


## <a name="create-a-batch-order"></a>Tworzenie zamówienia partii
1. Przejdź do okna Wszystkie zlecenia produkcyjne.
2. Kliknij opcję Nowe zamówienie partii.
3. W polu Numer towaru wprowadź lub wybierz wartość.
4. Kliknij Utwórz.
5. Użyj szybkiego filtru, aby wyfiltrować pole Produkcja według wartości „b”.

## <a name="view-production-formula-and-expected-co-products"></a>Wyświetlanie formuły produkcji i oczekiwanych produktów towarzyszących
1. W okienku akcji kliknij opcję Zlecenie produkcyjne.
2. Kliknij przycisk Formuła.
3. Zamknij stronę.
4. Kliknij przycisk Produkty towarzyszące.
5. Zamknij stronę.

## <a name="estimate-the-batch-order"></a>Szacowanie szarży produkcyjnej
1. Kliknij przycisk Szacuj.
2. Kliknij przycisk OK.
3. W okienku akcji kliknij pozycję Zarządzanie kosztami.
4. Kliknij opcję Wyświetl szczegóły obliczeń.
5. Zamknij stronę.

## <a name="release-the-batch-order"></a>Zwalnianie szarży produkcyjnej
1. W okienku akcji kliknij opcję Zlecenie produkcyjne.
2. Kliknij opcję Zwolnienie.
3. Kliknij przycisk OK.

## <a name="schedule-production-jobs"></a>Planowanie zadań produkcyjnych
1. W okienku akcji kliknij pozycję Harmonogram.
2. Kliknij harmonogram zadań.
3. W polu Ograniczone zdolności produkcyjne wybierz opcję Nie.
4. W polu Ograniczone materiały wybierz opcję Nie.
5. Kliknij przycisk OK.
6. W okienku akcji kliknij opcję Zlecenie produkcyjne.
7. Kliknij opcję Wszystkie zadania.
8. Zamknij stronę.

## <a name="start-the-batch-order"></a>Uruchamianie szarży produkcyjnej
1. Kliknij przycisk Rozpocznij.
2. Kliknij kartę Ogólne.
3. W polu Księgowanie listy pobrania wybierz wartość Nie.
4. Kliknij przycisk OK.
5. W okienku akcji kliknij pozycję Widok.
6. Kliknij opcję Lista pobrania.
7. Na liście kliknij łącze w wybranym wierszu.
8. Zamknij stronę.
9. Zamknij stronę.
10. Kliknij opcję Karta marszruty.
11. Na liście kliknij łącze w wybranym wierszu.
12. Zamknij stronę.
13. Zamknij stronę.

