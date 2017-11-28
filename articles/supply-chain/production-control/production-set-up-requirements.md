---
title: Wymagania konfiguracji produkcji
description: "Ten artykuł zawiera informacje o konfiguracji, jaką należy zapewnić przed rozpoczęciem używania modułu Kontrola produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47fe11168ad2ddea2a7033eda8d8bd8220efea32
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="production-setup-requirements"></a>Wymagania konfiguracji produkcji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o konfiguracji, jaką należy zapewnić przed rozpoczęciem używania modułu Kontrola produkcji. 

Kontrola produkcji współpracuje z funkcjami w innych modułach. Dzięki możliwości łączenia się z innymi aplikacjami można zmieniać zlecenia produkcyjne i mieć pewność, że są automatycznie aktualizowane w innych pokrewnych procesach i obliczeniach wykonywanych w systemie. Poniżej znajduje się wykaz procedur konfiguracji w kolejności, w jakiej należy je wykonać.

## <a name="required-baseline-setup-in-other-modules"></a>Wymagana konfiguracja podstawowa w innych modułach
Aby używać modułu Kontrola produkcji, trzeba skonfigurować informacje w innych modułach. Podzielono je na następujące zadania:

-   Wprowadzić podstawowe informacje o firmie.
-   Skonfigurować księgę główną.
-   Zdefiniować grupy towarów.
-   Skonfigurować konta księgowa grup towarów.
-   Utworzyć tabelę pozycji magazynowych w module Zarządzanie zapasami.
-   Utworzyć Listy składowe (BOM) i ich wersje w module Zarządzanie zapasami.

## <a name="required-calendar-and-resource-setup"></a>Wymagana konfiguracja kalendarza i zasobu
Aby używać modułu Kontrola produkcji, otwórz moduł Administrowanie organizacją i utwórz oraz zdefiniuj kalendarz i zasoby operacyjne w następującej kolejności:

1.  **Szablony czasu pracy** — skonfiguruj szablony czasu pracy, aby zdefiniować czas na planowanie produkcji.
2.  **Kalendarze** — skonfiguruj kalendarze czasu pracy w celu określenia dni w roku na planowanie produkcji.
3.  **Grupy zasobów** — skonfiguruj grupy zasobów, aby pogrupować zasoby operacyjne. Dzięki temu można uzyskać przegląd wszelkich wolnych zdolności produkcyjnych po uruchomieniu planowania. Nie masz ustawiać grup zasobów przed ustawieniem zasobów operacyjnych. Warto jednak znać sposób grupowania zasobów, kiedy ustawia się Kontrolę produkcji.
4.  **Zasoby** — skonfiguruj zasoby operacyjne w celu zdefiniowania zasobów stosowanych do ukończenia procesu produkcyjnego i planowania zdolności produkcyjnych.

## <a name="required-production-parameters-setup"></a>Konfiguracja wymaganych parametrów produkcyjnych
**Parametry kontroli produkcji** — skonfiguruj podstawowe parametry produkcji w celu zdefiniowania sposobu, w jaki system obsługuje i przetwarza zlecenia produkcyjne. Zdefiniuj sposób tworzenia, szacowania, planowania i stosowania zleceń produkcyjnych. Można także wybrać rodzaj informacji zwrotnych i sposób rozliczania kosztów.

## <a name="required-journal-name-identification"></a>Określanie nazwy wymaganego arkusza
**Nazwy arkuszy produkcji** — określ nazwy arkusza produkcji, które są używane do rejestrowania i księgowania transakcji.

## <a name="setup-if-you-use-operations"></a>Skonfiguruj operacje (jeśli są używane)
Operacje to określone działania, wykonywane w celu wykonania gotowego produktu. **Uwaga:** należy znać rodzaje działań, które są wymagane w celu wyprodukowania towaru, oraz kolejność i priorytety tych działań. Należy również ustalić, rodzaj i ilość potrzebnych zasobów.

1.  **Operacje** — skonfiguruj operacje odpowiadające zadaniom, które trzeba wykonać w celu wyprodukowania gotowego towaru.
2.  **Relacje** — skonfiguruj powiązania między operacjami, aby zdefiniować szczegółowe właściwości. Aby zdefiniować relacje operacji, kliknij przycisk **Relacje** na stronie **Operacje**.

## <a name="setup-if-you-use-routes"></a>Skonfiguruj marszruty (jeśli są używane)
W wypadku stosowania marszrut operacje muszą zostać zdefiniowane dla każdej skonfigurowanej marszruty produkcji. Marszruta to ścieżka towaru między kolejnymi operacjami, od początku do końca procesu produkcyjnego.

1.  **Kategorie kosztów** — skonfiguruj kategorie kosztów w celu zdefiniowania kosztu odpowiednich procesów na godzinę. Skonfiguruj czasy.
2.  **Grupy kosztów** — skonfiguruj grupy kosztów w celu utworzenia i obsługiwania różnych typów wyceny.
3.  **Grupy marszrut** — skonfiguruj grupy marszrut w celu zdefiniowania parametrów dotyczących grup marszrut. Grupy marszrut trzeba skonfigurować przed utworzeniem marszrut produkcyjnych.
4.  **Marszruty** — skonfiguruj marszruty produkcyjne i zdefiniuj ustawienia domyślne kontroli planowania, wyznaczania kosztów i cen operacji marszrut, a także raportowania postępów.
5.  **Grupy marszrut** — skonfiguruj wersje marszruty, aby pozwolić na odchylenia produkcyjne towaru.

## <a name="optional-advanced-settings"></a>Opcjonalne ustawienia zaawansowane
1.  **Grupy produkcji** — skonfiguruj grupy produkcji w celu utworzenia relacji między zleceniem produkcyjnym i kontami księgowymi. Konta księgowe są używane do księgowania lub grupowania zleceń do raportowania.
2.  **Grupy produkcji** — utwórz pule produkcji w celu pogrupowania zleceń produkcyjnych do przetwarzania pilnych zleceń produkcyjnych lub usunięcia i księgowania grup zleceń.
3.  **Właściwości** — zdefiniuj właściwości, aby utworzyć atrybuty specjalne, które można przypisać do zasobów w celu kontrolowania kolejnością produkcji. Te atrybuty są powiązane z szablonem czasu pracy.





