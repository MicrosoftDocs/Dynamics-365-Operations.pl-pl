---
title: Przestrzeń dyskowa danych wiekowania odbiorcy
description: W tym temacie opisano proces używania magazynu zewnętrznego do danych wiekowania odbiorcy. Proces przechowywania danych wiekowania odbiorcy można uruchomić, aby udostępnić dane wyjściowe dla eksportu do zewnętrznego systemu.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecd4f5359019e3c4778e21cc4946b9998cd519f
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817429"
---
# <a name="customer-aging-data-storage"></a>Przestrzeń dyskowa danych wiekowania odbiorcy

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano proces używania magazynu zewnętrznego do danych wiekowania odbiorcy. W rozwiązaniu Microsoft Dynamics 365 Finance proces przechowywania danych wiekowania odbiorcy można uruchomić, aby udostępnić dane wyjściowe dla eksportu do zewnętrznego systemu. Po uruchomieniu procesu te same opcje raportu wiekowania, które są dostępne w systemie, są dostępne dla systemów zewnętrznych. Szczegóły są zawsze uwzględniane w eksportowanych danych.

Pomocne może być udostępnić dane wiekowania odbiorcy do zewnętrznego systemu do przechowywania w przypadkach, gdy dane wyjściowe zawierają wielu odbiorców i/lub wiele transakcji. Jeśli istniejący raport **Wiekowania odbiorcy** wygasa z powodu zbyt dużej ilości danych do wydrukowania, ta funkcja stanowi alternatywę dla uzyskania tych samych danych.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Włączanie funkcji przechowywania danych wiekowania odbiorcy

Aby móc używać tej funkcji, musisz ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień zarządzania funkcją, aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** Kredyt i windykacje
- **Nawa funkcji:** Przechowywanie danych wiekowania odbiorcy

## <a name="run-the-customer-aging-data-storage-process"></a>Uruchamianie procesu przechowywania danych wiekowania odbiorcy

1. Wybierz kolejno opcje **Kredyty i windykacja \> Zapytania i raporty \> Odbiorca \> Przechowywanie danych wiekowania odbiorcy**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** nadaj nazwę procesowi.
4. Ustaw pozostałe wymagane parametry.

    > [!NOTE]
    > Szczegóły transakcji są zawsze uwzględniane, a przetwarzanie jest zawsze wykonywane w ramach zadania wsadowego.

5. Kliknij przycisk **OK**.
6. Odśwież stronę **Przechowywania danych wiekowania odbiorcy**, aby wyświetlić wartości **Nazwa partii** i **Czas przetwarzania partii**, które są wyświetlane razem z wartością **Stanu przetwarzania**. Po zakończeniu zadania wsadowego pole **Stan przetwarzania** ma wartość **Zakończone** i ustawiana jest wartość **Liczba wierszy wiekowania**. Jeśli zadanie wsadowe jest cykliczne, w polu **Stan przetwarzania** jest ustawiona wartość **Oczekujące**.
7. Wybierz przycisk **Filtruj** obok pola **Liczba wierszy wiekowania**, aby przejrzeć filtry dodane do zadania wsadowego.

Strona **Przechowywania danych wiekowania odbiorcy** nie zawiera wyników. Jednak jednostka danych **Przechowywania danych wiekowania odbiorcy** umożliwia eksportowanie danych wyjściowych do dowolnego formatu obsługującego funkcję zarządzania danymi.

> [!NOTE]
> Przed eksportem dodaj filtr, aby ograniczyć eksportowane wyniki do ostatniego wiekowania. Na przykład można dodać następujące kryteria, aby zwrócić ostatnie uruchomienie przetwarzania wsadowego:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> Alternatywnie, można dodać następujące kryteria, aby zwrócić ostatnie uruchomienie przetwarzania wsadowego dla bieżącego użytkownika:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
