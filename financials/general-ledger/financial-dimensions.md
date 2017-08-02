---
title: Wymiary finansowe
description: "W tym temacie opisano różne typy wymiarów finansowych oraz sposoby ich konfigurowania."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: e82d53b3f6b4c8d3e2363f26576331e1d03434d9
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# <a name="financial-dimensions"></a>Wymiary finansowe

[!include[banner](../includes/banner.md)]

W tym temacie omówiono różne typy wymiarów finansowych oraz sposoby ich konfigurowania.

Strona **Wymiary finansowe** umożliwia tworzenie wymiarów finansowych, które mogą być używane jako segmenty kont w planach kont. Istnieją dwa typy wymiarów finansowych: wymiary niestandardowe i wymiary oparte na jednostce. Niestandardowe wymiary są współużytkowane przez podmioty prawne i wartości są wprowadzane i obsługiwane przez użytkowników. W wymiarach opartych na jednostce wartości są zdefiniowane w innych miejscach w systemie, takich jak jednostki Odbiorcy lub Sklepy. Niektóre wymiary oparte na jednostce są współużytkowane przez podmioty prawne, podczas gdy inne są przypisane do określonej firmy. 

Po utworzeniu wymiarów finansowych na stronie **Wartości wymiarów finansowych** przypisz dodatkowe właściwości do każdego wymiaru finansowego. 

Wymiary finansowe mogą służyć do reprezentowania firm. Nie ma obowiązku tworzenia firm w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Jednak wymiary finansowe nie są zaprojektowane do zaspokajania wymagań operacyjnych ani biznesowych firmy. Funkcję księgowania międzyjednostkowego w programie Finance and Operations zaprojektowano tylko z myślą o zapisach księgowych, które są tworzone przy każdej transakcji. 

Przed skonfigurowaniem wymiarów finansowych jako firmy oceń swoje procesy biznesowe w następujących obszarach, aby ustalić, czy ta konfiguracja będzie działać w Twojej organizacji:

- Zapasy
- Sprzedaż i zakupy między wymiarami finansowymi i firmami
- Obliczanie i raportowanie podatku
- Raportowanie operacyjne

Poniżej przedstawiono wybrane ograniczenia:

- Można używać funkcji podatkowych tylko z firmami, a nie z wymiarami finansowymi.
- Niektóre raporty nie zawierają wymiarów finansowych. W związku z tym w celu raportowania według wymiarów finansowych może być konieczne modyfikowanie raportów.

## <a name="custom-dimensions"></a>Wymiary niestandardowe

Aby utworzyć zdefiniowany przez użytkownika typ wymiaru finansowego, w polu **Użyj wartości z** wybierz opcję **&lt; Wymiar niestandardowy &gt;**. Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,. Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, na przykład litery lub łącznik (-). Można także wprowadzić znaki cyfr (\#) oraz handlowego „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (\#) służy jako symbol zastępczy dla cyfr, a znak handlowe „i” jako symbol zastępczy dla liter. Pole maski formatu jest dostępne tylko w przypadku zaznaczenia opcji **&lt; Wymiar niestandardowy &gt;** w polu **Użyj wartości z**.

**Przykład**

Aby ograniczyć wartość wymiaru do liter „CC” i trzech cyfr, należy wprowadzić **CC-\#\#\#** jako maskę formatu.

## <a name="entity-backed-dimensions"></a>Wymiary oparte na jednostce

Aby utworzyć wymiary oparte na jednostce, w polu **Użyj wartości z** wybierz jednostkę zdefiniowaną przez system, która będzie podstawą wymiaru finansowego. Wartości wymiarów finansowych będą wtedy tworzone na bazie tej jednostki. Na przykład aby utworzyć wartości wymiarów dla projektów, wybierz opcję **Projekty**. Wartość wymiaru zostanie wtedy utworzona dla każdej nazwy projektu. Strona **Wartości wymiarów finansowych** pokazuje wartości jednostki. Jeśli te wartości są związane z konkretną firmą, na stronie widać również firmę.

## <a name="activating-dimensions"></a>Aktywowanie wymiaru

Po uaktywnieniu wymiaru finansowego tabela zostanie zaktualizowana, tak aby zawierała nazwę wymiaru finansowego. Usunięte wymiary zostaną wykasowane. Wartości wymiaru finansowego można wprowadzić przed jego uaktywnieniem. Jednak wymiar finansowy będzie mógł być zużywany dopiero po uaktywnieniu. Na przykład, nie można dodać wymiaru finansowego do struktury konta przed aktywowaniem wymiaru finansowego. Po kliknięciu przycisku **Uaktywnij** wszystkie wymiary są aktualizowane i pokazują zmianę stanu. 

## <a name="translations"></a>Tłumaczenia

Na stronie **Tłumaczenie tekstu** można wprowadzić tekst dla wybranego wymiaru finansowego w różnych językach. Na stronie **Tłumaczenie konta głównego** można wprowadzić tekst dla konta głównego w różnych językach. 

## <a name="legal-entity-overrides"></a>Firma zastępuje

Nie wszystkie wymiary mogą być używane we wszystkich firmach. Ponadto niektóre wymiary mogą mieć zastosowanie tylko do wybranych okresów. W takich przypadkach można w sekcji **Firma zastępuje** określić firmy, dla których wymiar powinien być zawieszony, właściciela oraz okres aktywności wymiaru.

## <a name="deleting-financial-dimensions"></a>Usuwanie wymiarów finansowych

Aby pomóc utrzymać więzy integralności danych, w wyjątkowych sytuacjach można usuwać wymiary finansowe. Jeśli zostanie podjęta próba usunięcia wymiaru finansowego, sprawdzane są następujące kryteria:

- Czy wymiar finansowy został użyty w jakiejkolwiek zaksięgowanej lub niezaksięgowanej transakcji albo w jakimkolwiek rodzaju kombinacja wartości wymiarów?
- Czy wymiar finansowy jest używany w jakiejkolwiek aktywnej strukturze konta, strukturze reguły zaawansowanej lub zestawie wymiarów finansowych?
- Czy wymiar finansowy wchodzi w skład domyślnego formatu integracji wymiarów finansowych?
- Czy wymiar finansowy ustawiono jako wymiar domyślny?

Jeśli którekolwiek z tych kryteriów jest spełnione, nie można usunąć wymiaru finansowego.

