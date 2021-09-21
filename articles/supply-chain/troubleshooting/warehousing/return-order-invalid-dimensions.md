---
title: Nie można utworzyć wiersza ładunku z powodu nieprawidłowych wymiarów magazynowych
description: Podczas próby zwolnienia zamówienia zwrotu sprzedaży do magazynu może zostać wyświetlony błąd o nieprawidłowych wymiarach magazynowych. Usuń je z wiersza zamówienia.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac58
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cb728f6a989cdac63c91d49baaea094bace59e4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477324"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Nie można utworzyć wiersza ładunku dla zamówienia sprzedaży zwrotu z powodu nieprawidłowych wymiarów magazynowych

## <a name="symptoms"></a>Objawy

Podczas próby zwolnienia zwrotu zamówienia sprzedaży do magazynu może zostać wyświetlony następujący komunikat o błędzie:

> Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe. Nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru lokalizacji w hierarchii rezerwacji. Usuń nieprawidłowe wymiary z wiersza zamówienia.

## <a name="resolution"></a>Rozwiązanie

Niestety, produkt nie obsługuje przetwarzania ładunku dla procesu zwrotu sprzedaży. Nie można więc zwolnić zwrotu zamówienia sprzedaży do magazynu.

W transakcjach zamówienia sprzedaży nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru **Lokalizacji** w hierarchii rezerwacji. Rozwiązanie polega na usunięciu nieprawidłowych wymiarów z wiersza zamówienia.
