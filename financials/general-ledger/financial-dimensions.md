---
title: Wymiary finansowe
description: "W tym artykule omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 01f189b8de3f0cc707dcc54f4cde75aed95b8e3f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="financial-dimensions"></a>Wymiary finansowe

[!include[banner](../includes/banner.md)]


W tym artykule omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania.

Strona Wymiary finansowe umożliwia utworzenie wymiarów finansowych, które mogą być używane jako segmenty obrachunkowe dla udostępnionych planów kont. Istnieją dwa typy wymiarów finansowych: wymiary niestandardowe i wymiary oparte na jednostce. Niestandardowe wymiary są współużytkowane przez podmioty prawne i wartości są wprowadzane i obsługiwane przez użytkownika. Wymiary oparte na jednostce to wymiary, których wartości są zdefiniowane w innych miejscach w systemie, takich jak Odbiorcy lub Sklepy. Niektóre wymiary oparte na jednostce są współużytkowane przez podmioty prawne, a niektóre są przypisane do określonej firmy. 

Po utworzeniu wymiarów finansowych, na stronie Wartości wymiarów finansowych przypisz dodatkowe właściwości do każdego wymiaru finansowego. 

Wprawdzie można używać wymiarów finansowych do reprezentowania firmy bez tworzenia firm w programie Microsoft Dynamics 365 for Operations, ale wymiary finansowe nie są przeznaczone do zaspokajania operacyjnych lub biznesowych potrzeb firmy. Funkcję księgowania międzyjednostkowego w programie Microsoft Dynamics 365 for Operations zaprojektowano tylko z myślą o zapisach księgowych, które są tworzone przy każdej transakcji. 

Przed skonfigurowaniem wymiarów finansowych jako firmy, oceń swoje procesy biznesowe w następujących obszarach, aby ustalić, czy ta konfiguracja będzie działać w danej organizacji:

-   Zapasy
-   Sprzedaż i zakupy między wymiarami finansowymi i firmami
-   Obliczanie i raportowanie podatku
-   Raportowanie operacyjne

Kilka przykładów ograniczeń:

-   Można używać funkcji podatkowych tylko z firmami, a nie z wymiarami finansowymi.
-   Niektóre raporty nie zawierają wymiarów finansowych, dlatego nie można zawsze raportować wg wymiaru finansowego, chyba że te raporty są modyfikowane.

**Wymiary niestandardowe** 

Aby utworzyć zdefiniowany przez użytkownika typ wymiaru finansowego, w kolumnie Użyj wartości z pola wybierz opcję &lt; Wymiar niestandardowy &gt;. Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,. Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik. Można także wprowadzić znaki cyfr (\#) oraz handlowego „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (\#) służy jako symbol zastępczy dla cyfr, a znak handlowe „i” jako symbol zastępczy dla liter. 

**Przykład** 

Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-\#\#\# jako maskę formatu. To pole jest dostępne tylko w przypadku zaznaczenia opcji &lt; Wymiar niestandardowy &gt; w polu Użyj wartości z. 

**Wymiary oparte na jednostce** 

Aby utworzyć wymiary oparte na jednostce, w polu Użyj wartości z wybierz podmiot zdefiniowany przez system, który będzie podstawą wymiaru finansowego. Wartości wymiaru finansowego są tworzone na podstawie tego zaznaczenia. Na przykład aby utworzyć wartości wymiarów dla projektów, wybierz opcję Projekty. Wartość wymiaru zostanie utworzona dla każdej nazwy projektu. Strona Wartości wymiarów pokazuje wartości dla firmy, a jeśli są to wartości charakterystyczne dla danego podmiotu, także firmę. 

**Aktywowanie wymiaru** 

Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany. Na przykład, nie można dodać wymiaru finansowego do struktury konta przed aktywowaniem wymiaru finansowego. Należy kliknąć przycisk Aktywuj, aby zaktualizować wszystkie wymiary ze zmianą stanu. 

**Tłumaczenia** 

Strona Tłumaczenie tekstu pozwala wprowadzać tekst, który będzie wyświetlany w różnych językach dla wybranego wymiaru finansowego. Strona tłumaczenia konta głównego pozwala wprowadzać tekst wyświetlany w różnych językach dla konta głównego. 

**Firma zastępuje** 

Nie wszystkie wymiary są prawidłowe dla wszystkich firm, a niektóre mogą być dostępne tylko w określonym przedziale czasu. W tym scenariuszu sekcja Firma zastępuje może służyć do identyfikowania firm, dla wymiar powinien być zawieszony, właściciela oraz okresu aktywności wymiaru.






