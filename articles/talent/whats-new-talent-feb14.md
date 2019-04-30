---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (14 lutego 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1db7d032eade3f996e0554e64d6ea0704a347ed8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "859397"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (14 lutego 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Inne niewielkie poprawki są dołączone do tej wersji.

## <a name="changes-in-onboarding"></a>Zmiany we wdrażaniu do pracy
Inne niewielkie poprawki są dołączone do tej wersji.
 
## <a name="changes-in-core-hr"></a>Zmiany w Core HR 
**Kompilacja 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>Jednostki stałego wynagrodzenia pracownika nie eksportują wszystkich rekordów
Z tą zmianą jednostka **stałe wynagrodzenie pracownika** będzie teraz eksportować wszystkie rekordy. Jednostka może służyć do tworzenia i aktualizowania istniejących rekordów stałego wynagrodzenia dla pracowników. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>Data zakończenia zatrudnienia nie uwzględnia ustawienia preferowanej strefy czasowej pracownika
Daty zakończenia zatrudnienia uwzględniają teraz strefę czasową preferowaną przez użytkownika podczas tworzenia lub zakończenia zatrudnienia w firmie.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Brytyjskie adresy są wyświetlane w Analytics jako adresy we wschodniej Szwajcarii
W tej wersji została wprowadzona zmiana, aby naprawić niespójność w adresach w raporcie "stan osobowy według lokalizacji" **zarządzania personelem**.
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>Kod zwolnienia nie jest wypełniony dla rekordu przypisania stanowiska pracownika przy wygaśnięciu zatrudnienia na stanowisku
Wprowadzono zmianę w domyślnym kodzie "Powód rozwiązania umowy" przy dodawaniu przypisania stanowiska do pracownika.

### <a name="new-entity-created-for-job-compensation-levels"></a>Utworzono nową jednostkę dla poziomów wynagrodzenia
Utworzono nową jednostkę DMF. Jednostka zapewnia tworzenie i aktualizacje poziomów wynagrodzeń, wartości rynkowej i informacji dotyczących badania dla każdego stanowiska zdefiniowanego w systemie.
