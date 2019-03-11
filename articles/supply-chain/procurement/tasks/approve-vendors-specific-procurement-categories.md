---
title: Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia
description: Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b783d1ce8f02ad119dc6768e6d9cd3c61ae07e70
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "308398"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia

[!include [task guide banner](../../includes/task-guide-banner.md)]

Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów. W tej procedurze pokazano sposób określania, że dostawca jest zatwierdzony lub preferowany dla określonej kategorii zaopatrzenia. To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.
2. Zaznacz dostawcę, którego chcesz ustawić jako preferowanego lub zatwierdzonego dla kategorii.
3. W okienku akcji kliknij pozycję Ogólne.
4. Kliknij opcję Kategorie.
5. Kliknij opcję Dodaj kategorię.
6. W polu Kategoria wybierz pozycję AKCESORIA BIUROWE I TECHNICZNE (AKCESORIA BIUROWE I TECHNICZNE).
7. W polu Stan kategorii dostawcy wybierz wartość „Preferowany”.
    * Istnieje możliwość określenia więcej niż jednego preferowanego dostawcy dla kategorii.  
8. Kliknij przycisk Zapisz.
9. Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.
10. W drzewie zaznacz element „KATEGORIE ZAOPATRZENIA W FIRMIE\AKCESORIA BIUROWE I TECHNICZNE”.
11. Rozwiń sekcję Dostawcy.
    * Sprawdź, czy wybrany dostawca jest wyświetlany jako preferowany dostawca dla kategorii Akcesoria biurowe i techniczne. Jeżeli wykonujesz procedurę jako przewodnik po zadaniu, może być konieczne kliknięcie przycisku Odblokuj, aby przewinąć w dół do listy dostawców.  Na tej stronie można również dodawać preferowanych i zatwierdzonych dostawców.  
12. W drzewie rozwiń węzeł „AKCESORIA BIUROWE I TECHNICZNE”.
13. W drzewie zaznacz element „Nożyczki”.
14. W polu Dziedzicz dostawców po kategorii nadrzędnej: zaznacz wartość Nie.
15. W polu Dziedzicz dostawców po kategorii nadrzędnej: zaznacz wartość Tak.

