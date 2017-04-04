---
title: Wymiary finansowe
description: "W tym artykule omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Wymiary finansowe

W tym artykule omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania.

Strona Wymiary finansowe umożliwia utworzenie wymiarów finansowych, które mogą być używane jako segmenty obrachunkowe dla udostępnionych planów kont. Istnieją dwa typy wymiarów finansowych: wymiary niestandardowe i wymiary oparte na jednostce. Niestandardowe wymiary są współużytkowane przez podmioty prawne i wartości są wprowadzane i obsługiwane przez użytkownika. Wymiary oparte na jednostce to wymiary, których wartości są zdefiniowane w innych miejscach w systemie, takich jak Odbiorcy lub Sklepy. Niektóre wymiary oparte na jednostce są współużytkowane przez podmioty prawne, a niektóre są przypisane do określonej firmy. 

Po utworzeniu wymiarów finansowych, na stronie Wartości wymiarów finansowych przypisz dodatkowe właściwości do każdego wymiaru finansowego. 

Chociaż można używać wymiarów finansowych do reprezentowania firmy bez tworzenia podmiotów prawnych w usłudze Microsoft Dynamics 365 dla operacji, wymiary finansowe nie są przeznaczone do operacyjnych lub potrzeb biznesowych podmiotów prawnych. Wielojednostkowym funkcja obsługi kont w usłudze Microsoft Dynamics 365 dla operacji zaprojektowano z myślą zapisy księgowe, które są tworzone przez każdą transakcję. 

Przed skonfigurowaniem wymiarów finansowych jako firmy, oceń swoje procesy biznesowe w następujących obszarach, aby ustalić, czy ta konfiguracja będzie działać w danej organizacji:

-   Zapasy
-   Sprzedaż i zakupy między wymiarami finansowymi i firmami
-   Obliczanie i raportowanie podatku
-   Raportowanie operacyjne

Kilka przykładów ograniczeń:

-   Można używać funkcji podatkowych tylko z firmami, a nie z wymiarami finansowymi.
-   Niektóre raporty nie zawierają wymiarów finansowych, dlatego nie można zawsze raportować wg wymiaru finansowego, chyba że te raporty są modyfikowane.

**Custom dimensions** 

Aby utworzyć użytkownika wymiaru finansowego, w polu Użyj wartości z pola, zaznacz &lt;wymiaru Custom&gt;. Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,. Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik. Można także wprowadzić znaki numeru (\#) i takie znaki (&) jako symbole zastępcze liter i cyfr, która będzie za każdym razem tworzona jest wartość wymiaru. Użyj znaku krzyżyka (\#) jako symbol zastępczy dla numeru i znakiem handlowego i (&) jako symbol zastępczy dla list. 

**Przykład ** 

Aby ograniczyć wartości wymiaru do liter CC i trzech cyfr, należy wprowadzić CC -\#\#\# jako maskę formatu. To pole jest dostępne tylko po wybraniu &lt;wymiaru Custom &gt;w polu Użyj wartości z pola. 

**Wymiary jednostki kopii** 

Aby utworzyć wymiar finansowy jednostki kopii w polu Użyj wartości z pola, zaznacz element zdefiniowanych przez system do podstawy wymiaru finansowego. Wartości wymiaru finansowego są tworzone na podstawie tego zaznaczenia. Na przykład aby utworzyć wartości wymiarów dla projektów, wybierz opcję Projekty. Wartość wymiaru zostanie utworzona dla każdej nazwy projektu. Strona Wartości wymiarów pokazuje wartości dla firmy, a jeśli są to wartości charakterystyczne dla danego podmiotu, także firmę. 

**Aktywowanie wymiarów** 

Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany. Na przykład, nie można dodać wymiaru finansowego do struktury konta przed aktywowaniem wymiaru finansowego. Należy kliknąć przycisk Aktywuj, aby zaktualizować wszystkie wymiary ze zmianą stanu. 

**Translations** 

Strona tłumaczenia tekstu pozwala wprowadzać tekst ma być wyświetlany w różnych językach dla wybranego wymiaru finansowego. Strona tłumaczenia konta głównego pozwala wprowadzać tekst wyświetlany w różnych językach dla konta głównego. 

**Legal entity overrides** 

Nie wszystkie wymiary są prawidłowe dla wszystkich podmiotów prawnych, a niektóre mogą jedynie być istotne dla określonego okresu. W tym scenariuszu sekcja Firma zastępuje może służyć do identyfikowania firm, dla wymiar powinien być zawieszony, właściciela oraz okresu aktywności wymiaru.




