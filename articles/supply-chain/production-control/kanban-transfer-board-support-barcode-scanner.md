---
title: Obsługa tablicy przeniesień w systemie Kanban dla skanerów kodów kreskowych
description: Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566818"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>Obsługa tablicy przeniesień w systemie Kanban dla skanerów kodów kreskowych

[!include [banner](../includes/banner.md)]

Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.

## <a name="registration-modes"></a>Tryby rejestracji

Na skróconej karcie **Rejestracja skanera** można wybrać tryb rejestracji kontrolujący działanie, podczas którego użytkownik skanuje numer karty Kanban lub ręcznie wpisuje numer w polu Numer karty Kanban.

| Ustaw tryb rejestracji | Opis                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Uruchom                 | Rejestruje zadanie przeniesienia w systemie Kanban jako zadania w toku.                                                 |
| Zakończono              | Rejestruje zadanie przeniesienia w systemie Kanban jako zakończonego.                                                   |
| Puste                 | Rejestruje magazynową jednostkę obsługi materiału, do której odwołuje się karta Kanban, jako pustą              |
| Wybierz                | Rejestruje numer karty Kanban i automatyczne wybiera z listy zadań w systemie Kanban to zadanie, do którego odwołuje się ta karta |

 
## <a name="registration-mode-select"></a>Wybierz tryb rejestracji

Gdy użyjesz czytnika kodów kreskowych do wybrania zadania, tryb wyświetlania na tablicy Kanban zmieni się. W tym trybie mają zastosowanie następujące warunki:

-   Wyświetlane są tylko zeskanowane zadania Kanban.
-   Szczegóły wybranego zadania są wyświetlane w na skróconej karcie **Szczegóły**.
-   Skrócona karta **Wiadomości** wyświetla komunikaty tylko dla wybranego zadania.
-   Stan zadania można zmienić za pomocą funkcji, które są dostępne w okienku akcji. Tablica Kanban przeniesienia jest nadal wyświetlana w jednym zadaniu w tym czasie.
-   Informacje na liście zadań można aktualizować ręcznie przez kliknięcie przycisku **Odśwież** (Shift + F5) w okienku akcji. Po odświeżeniu informacji pełne wyniki filtru zadania są wyświetlane ponownie.

## <a name="job-status-and-possible-actions"></a>Stan i możliwe akcje zadania
Stan wybranego zadania oraz stan wszelkich niezaplanowanych zadań dla w dla kart Kanban zdarzenia, określają, czy zadanie może być dalej przetwarzane. Poniższa tabela pokazuje informacje dotyczące tych stanów i zadań:
-   Stany, które są dostępne dla zadań lub dla jednostek załadunkowych, do których odwołują się zadania.
-   Każde zadanie, które można wykonać dla zadania.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ zadania</th>
<th>Stan zadania lub stan jednostki załadunkowej</th>
<th>Aktualizuj listę pobrania</th>
<th>Uruchom</th>
<th>Aktualizuj rejestrację</th>
<th>Zakończono</th>
<th>Puste</th>
<th>Utwórz zdarzenia Kanban</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Przenieś</td>
<td><ul>
<li>Niezaplanowane</li>
<li>Brak ustalonych zadań lub żadne ustalone zadanie nie ma stanu Zakończono</li>
</ul></td>
<td>Tak</td>
<td>Tak</td>
<td>Tak</td>
<td>Tak</td>
<td>Nie</td>
<td>Tak</td>
</tr>
<tr class="even">
<td>Przenieś</td>
<td><ul>
<li>Niezaplanowane</li>
<li>Ustalone zadanie nie ma stanu Zakończone</li>
</ul></td>
<td>Tak</td>
<td>Nie</td>
<td>Tak</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="odd">
<td>Przenieś</td>
<td>W toku</td>
<td>Tak</td>
<td>Nie</td>
<td>Tak</td>
<td>Tak</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="even">
<td>Przenieś</td>
<td>Ukończono</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Tak</td>
<td>Nie</td>
</tr>
<tr class="odd">
<td>Przeniesienie lub proces</td>
<td>Puste</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="even">
<td>Przeniesienie lub proces</td>
<td>Nie znaleziono karty Kanban</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="odd">
<td>Przeniesienie lub proces</td>
<td>Znaleziono kartę Kanban, ale nie jest ona przypisana do zadania Kanban</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="even">
<td>Przetwórz</td>
<td><ul>
<li>Niezaplanowane</li>
<li>Przygotowane</li>
<li>W toku</li>
</ul></td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
<tr class="odd">
<td>Przetwórz</td>
<td>Ukończono</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
<td>Nie</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]