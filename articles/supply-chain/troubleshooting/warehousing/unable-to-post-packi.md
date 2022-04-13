---
title: Nie można zaksięgować dokumentu dostawy dla zatrzymanego wiersza zamówienia sprzedaży
description: Nie możesz zaksięgować dokumentu dostawy dla wiersza zatrzymanego zamówienia sprzedaży
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462856"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Nie można zaksięgować dokumentu dostawy dla zatrzymanego wiersza zamówienia sprzedaży

Kod błędu: SYS13203

## <a name="symptoms"></a>Objawy

Podczas próby zaksięgowania dokumentu dostawy dla ładunku system wyświetla następujący komunikat o błędzie:

> Nie można zaksięgować dokumentu dostawy podczas zatrzymywania wiersza zamówienia sprzedaży po potwierdzeniu wysyłki wychodzącej Nie można pobrać ilości.

## <a name="cause"></a>Powód

Jeden lub więcej powiązanych wierszy zamówienia sprzedaży może zostać zatrzymanych, co oznacza, że system uniemożliwi dalsze przetwarzanie tego zamówienia sprzedaży. Oznacza to między innymi, że system nie będzie księgował dokumentu dostawy dla zamówienia.

Użytkownik może na przykład zdecydować o zatrzymaniu co najmniej jednego wiersza zamówienia, ponieważ odbiorca odwołał się i anulował swoje zamówienie. Jeśli jednak wysyłka wychodząca została już potwierdzona, to wysyłka zawierająca zamówienie sprzedaży już fizycznie opuściła magazyn, co oznacza, że zatrzymywanie wierszy zamówienia sprzedaży nie będzie mieć żadnego wpływu. Ponieważ fizyczne zatrzymanie przesyłki nie jest już możliwe, możesz równie dobrze odblokować linie, aby opublikować dokument dostawy. Następnie trzeba będzie obsłużyć anulowane zamówienie jako zwrot.

## <a name="resolution"></a>Rozwiązanie

Aby było możliwe zaksięgowanie dokumentu dostawy, należy się upewnić, że żaden z odpowiednich wierszy zamówienia sprzedaży nie został zatrzymany przez wykonanie poniższych kroków.

1. Wybierz kolejno opcje **Wszystkie zamówienia sprzedaży \> Sprzedaż i marketing \> Wszystkie zamówienia sprzedaży**.
1. Znajdź i otwórz zamówienie sprzedaży, z które masz problemy.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży.
1. Na skróconej karcie **Szczegóły wiersza** otwórz kartę **Ogólne** i upewnij się, że pole **Zatrzymane** ma wartość *Nie*.
1. Kontynuuj pracę, dopóki nie zostaną zatrzymane wszystkie odpowiednie wiersze sprzedaży.
1. Spróbuj ponownie zaksięgować dokument dostawy dla ładunku lub zamówienia sprzedaży.
