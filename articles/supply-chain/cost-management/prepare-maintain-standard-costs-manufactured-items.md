---
title: Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów
description: W tym temacie opisano etapy przygotowywania się do zarządzania kosztami wytwarzanych towarów.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbd7344f3d542cbd46e3568d8a7911ab4ab53b17
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545955"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów

[!include [banner](../includes/banner.md)]

W tym temacie opisano etapy przygotowywania się do zarządzania kosztami wytwarzanych towarów. Kroki dla towarów wytwarzanych różnią się nieco od kroków dla towarów zakupionych.

Zasady przypisane do towarów wytwarzanych mogą wpływać na obliczanie kosztów nadrzędnych towarów wytwarzanych. Aby się przygotować do zarządzania kosztami towarów wytwarzanych, wykonaj następujące czynności:

1. Przypisz grupa modeli pozycji do wytwarzanego towaru. 

   Grupa modeli pozycji wskazuje, że będą używane koszty standardowe.

2. Przypisz grupę towarów do wytwarzanego towaru. 

   Grupa towarów zawiera konta księgowe dotyczące wytwarzanego towaru. Konta księgowe wytwarzanego towaru używającego modelu zapasów opartego na kosztach standardowych obsługują różne odchylenia produkcji, odchylenia zmian kosztów i przeszacowania kosztów zapasów.

3. Przypisz magazynową jednostkę miary do towaru. 

   Koszty towaru są zawsze wyrażane w jednostkach miary zapasów.

4. Nie przypisuj grupy kosztów do wytwarzanego towaru, dopóki towar nie jest traktowany jako zakupiony towar.

5. Przypisz grupę obliczeń listy składowej (BOM) do wytwarzanego towaru. 

   Grupa obliczeń BOM towaru określa warunki ostrzeżeń, które mają zastosowanie. W ten sposób po zakończeniu obliczania BOM mogą być generowane komunikaty ostrzegawcze o możliwych źródłach błędów w obliczeniach. Na przykład komunikat ostrzegawczy może wystąpić, gdy aktywna lista BOM lub marszruta nie istnieje. Grupa obliczeń BOM zawiera zasadę zatrzymania rozłożenia, która określa, kiedy wytworzony towar powinien być traktowany jako zakupiony.

6. Jeśli wytworzony towar ma koszty stałe, przypisz mu standardową ilość zamówienia. 

   Standardowa ilość zamówienia to księgowa wielkość partii na potrzeby amortyzacji kosztów stałych. Przykłady kosztów stałych to m.in. czasy przezbrajania w operacjach marszruty czy stała ilość składnika na liście BOM.

7. Określ BOM dla wytwarzanego towaru. 

   Można zdefiniować jedną lub więcej wersji BOM. Sprawdź, czy wersje zostały oznaczone jako zatwierdzone i aktywne oraz mają przydzielone odpowiednie daty obowiązywania. Wersja BOM może obowiązywać w całej firmie lub w wybranym oddziale.

8. Określ marszrutę dla wytwarzanego towaru. 

   Można zdefiniować jedną lub więcej wersji marszruty. Sprawdź, czy wersje zostały oznaczone jako zatwierdzone i aktywne oraz mają przydzielone odpowiednie daty obowiązywania. Wersja marszruty musi obowiązywać w wybranym oddziale.

Jeśli chcesz używać informacji o marszrucie do wyceny, potrzebne są dodatkowe czynności przygotowawcze. Na przykład kategorie kosztów przypisane do operacji marszrut muszą być prawidłowe i kompletne.

<a name="related-topics"></a>Powiązane tematy
--------

[Amortyzowanie kosztów stałych wytworzonego towaru](amortize-constant-costs-manufactured-item.md)

[Konfigurowanie produktów, które mogą być produkowane lub zamawiane](manufactured-items-treated-as-purchased-items.md)

