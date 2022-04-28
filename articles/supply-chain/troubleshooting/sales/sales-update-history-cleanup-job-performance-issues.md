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
ms.openlocfilehash: 124fb90ecafd4f4cccbd8a8bb443694c95365732
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570349"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Zadanie oczyszczania historii aktualizacji sprzedaży nie powiodło się lub istnieją problemy z wydajnością

## <a name="symptoms"></a>Objawy

Zadanie wsadowe **oczyszczania historii aktualizacji sprzedaży** nie powiodło się lub istnieją problemy z wydajnością.  

## <a name="cause"></a>Powód

Może to wystąpić, gdy system zawiera wiele aktualizacji sprzedaży, w wyniku czego istnieje duża ilość danych aktualizacji sprzedaży. Zadanie oczyszczania próbuje wyczyścić wszystkie dane w jednej transakcji. W związku z tym zadanie może potrwać bardzo długo, a nawet zakończyć się niepowodzeniem.

## <a name="resolution"></a>Rozwiązanie

Nowa wersja zadania wsadowego **Czyszczenia historii aktualizacji sprzedaży** jest dostępna dla usługi Supply Chain Management w wersji 10.0.19 i nowszej. Domyślnie ta opcja nie jest włączona. Aby uzyskać szczegółowe informacje o jej działaniu oraz sposobie włączania jej w obszarze zarządzania funkcjami, zobacz [Zaplanuj czyszczenie danych historii sprzedaży](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

