---
title: Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5f3a9ab907c3cb0e6b99c414a78b6878bd5353274472c54e1f5eaf1d167f046a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773112"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.

Aby uzyskać tematy związane z rejestracją numerów partii i numerów seryjnych, zobacz [Rozwiązywanie problemów z hierarchiami rezerwacji partii i numerów seryjnych w magazynie](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Otrzymuje następujący komunikat o błędzie: „Nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”.

### <a name="issue-description"></a>Opis problemu

Nie można usunąć rezerwacji zapasów w wierszu sprzedaży, ponieważ w wierszu istnieje otwarta praca.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Sprawdź, czy istnieje otwarta grupa załadunkowa, aby przenieść pozycję z stacji pakowania do innej lokalizacji (np. *Brama dokowa*). Przejrzyj rekordy w **Dzienniku historii tworzenia pracy** i **Szczegóły pracy**, aby określić, co fizycznie rezerwuje zapasy, a następnie ukończyć lub usunąć pracę, aby zwolnić rezerwację.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Zgłaszany jest następujący komunikat o błędzie: „Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2”...

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach. Oto pełen tekst całego komunikatu o błędzie:

> Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2 o wymiarze Wymiar=%3, Kolor=%4, Dodatki=%5, Oddział=%6, Magazyn=%7, Lokalizacja=%8, Stan zapasów=dostępny, Numer identyfikacyjny=%9, Numer partii=%10 dla identyfikatora odwołania %11 w identyfikatorze partii %12.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie. Na przykład te transakcje mogą otwierać zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Zgłaszany jest następujący komunikat o błędzie: „Fizycznie dostępne zapasy... nie mogą być zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00”.

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach. Oto pełen tekst całego komunikatu o błędzie:

> Fizycznie dostępne w oddziale=%1, Magazyn=%2, Stan zapasów=dostępne, Numer partii=%3, Właściciel=%4: %5 nie może zostać zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem jest prawdopodobnie spowodowany otwarta pracą. Ukończ pracę lub odbierz bez tworzenia pracy. Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie. Na przykład tymi transakcjami mogą być otwarte zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
