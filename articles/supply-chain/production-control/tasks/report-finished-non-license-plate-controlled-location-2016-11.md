---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez numer identyfikacyjny (zgłoszenie, maj 2016)
description: Ten przewodnik po zadaniach zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a9010b95cfd0528cd3b532627d19a3b340bdca4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210578"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez numer identyfikacyjny (zgłoszenie, maj 2016)

[!include [banner](../../includes/banner.md)]

Ten przewodnik po zadaniach zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny. Warunkiem wstępnym tego zadania jest istnienie odpowiedniej zasady pracy. Poprzedni przewodnik po zadaniach pokazywał konfigurację zasady pracy. Ten przewodnik po zadaniach wymaga aplikacji Dynamics AX w wersji 7.0.1 lub nowszej.




## <a name="set-up-an-output-location"></a>Konfigurowanie lokalizacji wyjściowej
1. Wybierz kolejno opcje Administrowanie organizacją > Zasoby > Grupy zasobów.
2. Na liście zaznacz grupę zasobów „5102”.
3. Kliknij przycisk Edytuj.
4. W polu Magazyn wyjściowy wpisz „51”.
5. W polu Lokalizacja wyjściowa wpisz „001”.
    * Lokalizacja 001 nie jest lokalizacją kontrolowaną przez numer identyfikacyjny. Można skonfigurować lokalizację wyjściową niekontrolowaną za pomocą numeru identyfikacyjnego, ale tylko wtedy, gdy istnieje odpowiednia zasada pracy dla lokalizacji.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Tworzenie zlecenia produkcyjnego i zgłaszanie go jako gotowego
1. Zamknij stronę.
2. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
3. Kliknij opcję Nowe zlecenie produkcyjne.
4. W polu Numer pozycji wpisz „L0101”.
5. Kliknij Utwórz.
6. W okienku akcji kliknij opcję Zlecenie produkcyjne.
7. Kliknij przycisk Szacuj.
8. Kliknij przycisk OK.
9. Kliknij przycisk Uruchom.
10. Kliknij kartę Ogólne.
11. W polu Automatyczne zużycie BOM zaznacz opcję „Nigdy”.
12. Kliknij przycisk OK.
13. Kliknij opcję Zgłoś jako gotowe.
14. Kliknij kartę Ogólne.
15. W polu Akceptacja błędu wybierz opcję Tak.
16. Kliknij przycisk OK.
17. W okienku akcji kliknij pozycję Magazyn.
18. Kliknij opcję Szczegóły pracy.
    * Po zgłoszeniu zlecenia produkcyjnego jako gotowego nie została wygenerowana żadna praca odłożenia. Dzieje się tak, ponieważ zdefiniowano zasadę pracy, która blokuje generowanie pracy, gdy produkt L0101 jest zgłaszany jako gotowy do lokalizacji 001.  

