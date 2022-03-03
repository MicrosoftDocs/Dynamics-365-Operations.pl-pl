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
ms.openlocfilehash: 371a8c7178cd7c5091d6dd9a91d0ee03b943a269
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103195"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Zadanie oczyszczania historii aktualizacji sprzedaży nie powiodło się lub istnieją problemy z wydajnością

## <a name="symptoms"></a>Objawy

Zadanie wsadowe **oczyszczania historii aktualizacji sprzedaży** nie powiodło się lub istnieją problemy z wydajnością.  

## <a name="cause"></a>Powód

Może to wystąpić, gdy system zawiera wiele aktualizacji sprzedaży, w wyniku czego istnieje duża ilość danych aktualizacji sprzedaży. Zadanie oczyszczania próbuje wyczyścić wszystkie dane w jednej transakcji. W związku z tym zadanie może potrwać bardzo długo, a nawet zakończyć się niepowodzeniem.

## <a name="resolution"></a>Rozwiązanie

Nowa wersja zadania wsadowego **Czyszczenia historii aktualizacji sprzedaży** jest dostępna dla usługi Supply Chain Management w wersji 10.0.19 i nowszej. Domyślnie ta opcja nie jest włączona. Aby uzyskać szczegółowe informacje o jej działaniu oraz sposobie włączania jej w obszarze zarządzania funkcjami, zobacz [Poprawa wydajności czyszczenia historii sprzedaży](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

