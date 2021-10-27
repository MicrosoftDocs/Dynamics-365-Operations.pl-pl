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
ms.openlocfilehash: 4f04dc204c705b40ed25fadc75118feaef4d6b6e
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641477"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Zadanie oczyszczania historii aktualizacji sprzedaży nie powiodło się lub istnieją problemy z wydajnością

## <a name="symptoms"></a>Objawy

Zadanie wsadowe **oczyszczania historii aktualizacji sprzedaży** nie powiodło się lub istnieją problemy z wydajnością.  

## <a name="cause"></a>Powód

Może to wystąpić, gdy system zawiera wiele aktualizacji sprzedaży, w wyniku czego istnieje duża ilość danych aktualizacji sprzedaży. Zadanie oczyszczania próbuje wyczyścić wszystkie dane w jednej transakcji. W związku z tym zadanie może potrwać bardzo długo, a nawet zakończyć się niepowodzeniem.

## <a name="resolution"></a>Rozwiązanie

Nowa wersja zadania wsadowego **Czyszczenia historii aktualizacji sprzedaży** jest dostępna dla usługi Supply Chain Management w wersji 10.0.19 i nowszej. Ta funkcja nie jest domyślnie włączona. Aby uzyskać szczegółowe informacje o jej działaniu i jak ją włączyć w zarządzaniu funkcjami, zobacz temat [Poprawa wydajności czyszczenia historii sprzedaży](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

