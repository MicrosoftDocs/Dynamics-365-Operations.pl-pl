---
title: Nie można utworzyć wiersza ładunku z powodu nieprawidłowych wymiarów magazynowych
description: Podczas próby zwolnienia zamówienia zwrotu sprzedaży do magazynu może zostać wyświetlony błąd o nieprawidłowych wymiarach magazynowych. Usuń je z wiersza zamówienia.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119219"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Nie można utworzyć wiersza ładunku dla zamówienia sprzedaży zwrotu z powodu nieprawidłowych wymiarów magazynowych

## <a name="symptoms"></a>Objawy

Podczas próby zwolnienia zwrotu zamówienia sprzedaży do magazynu może zostać wyświetlony następujący komunikat o błędzie:

> Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe. Nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru lokalizacji w hierarchii rezerwacji. Usuń nieprawidłowe wymiary z wiersza zamówienia.

## <a name="resolution"></a>Rozwiązanie

Niestety, produkt nie obsługuje przetwarzania ładunku dla procesu zwrotu sprzedaży. Nie można więc zwolnić zwrotu zamówienia sprzedaży do magazynu.

W transakcjach zamówienia sprzedaży nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru **Lokalizacji** w hierarchii rezerwacji. Rozwiązanie polega na usunięciu nieprawidłowych wymiarów z wiersza zamówienia.
