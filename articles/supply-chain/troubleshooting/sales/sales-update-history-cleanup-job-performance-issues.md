---
title: Zadanie oczyszczania historii aktualizacji sprzedaży nie powiodło się lub istnieją problemy z wydajnością
description: Zadanie wsadowe oczyszczania historii sprzedaży może się nie powieść lub potrwać bardzo długo, jeśli istnieje duża ilość danych aktualizacji sprzedaży.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c02273adf90afc67b7c0ae1b82c19d489bfbd3b1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920081"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Zadanie oczyszczania historii aktualizacji sprzedaży nie powiodło się lub istnieją problemy z wydajnością

## <a name="symptoms"></a>Objawy

Zadanie wsadowe **oczyszczania historii aktualizacji sprzedaży** nie powiodło się lub istnieją problemy z wydajnością.  

## <a name="cause"></a>Powód

Może to wystąpić, gdy system zawiera wiele aktualizacji sprzedaży, w wyniku czego istnieje duża ilość danych aktualizacji sprzedaży. Zadanie oczyszczania próbuje wyczyścić wszystkie dane w jednej transakcji. W związku z tym zadanie może potrwać bardzo długo, a nawet zakończyć się niepowodzeniem.

## <a name="resolution"></a>Rozwiązanie

Nowa wersja zadania wsadowego **Czyszczenia historii aktualizacji sprzedaży** jest dostępna dla usługi Supply Chain Management w wersji 10.0.19 i nowszej. Ta funkcja nie jest domyślnie włączona. Aby uzyskać szczegółowe informacje o jej działaniu oraz sposobie włączania jej w obszarze zarządzania funkcjami, zobacz [Poprawa wydajności czyszczenia historii sprzedaży](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

