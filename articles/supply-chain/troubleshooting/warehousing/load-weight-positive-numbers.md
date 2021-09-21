---
title: Waga ładunku może zawierać tylko wartości dodatnie
description: Podczas przetwarzania pracy między lokalizacjami może zostać wyświetlony błąd dotyczący wagi ładunku i anulowania aktualizacji. Wykonaj następujące czynności, aby rozwiązać problem.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477296"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Błąd wagi ładunku i aktualizacja anulowane podczas przetwarzania pracy między lokalizacjami

## <a name="symptoms"></a>Objawy

Jeśli podczas przetwarzania pracy z lokalizacji pakowania do lokalizacji przemieszczania lub z lokalizacji przemieszczania do lokalizacji dokowania jest otwarta praca, może wystąpić następujący błąd:

> Pole „Waga ładunku”(=-%1) może zawierać tylko wartości dodatnie. Aktualizacja została anulowana.

## <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, przejdź do **Administrowanie systemem \> Zadania okresowe \> Baza danych \> Sprawdzanie spójności** i uruchom proces **Sprawdzenie spójności wagi ładunku magazynu**.
