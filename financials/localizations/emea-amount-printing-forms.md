---
title: "Aktualizacja sposobu wyświetlania kwot w raportach i dokumenty"
description: "Ten temat zawiera informacje dotyczące aktualizacji, sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Republiki Czeskiej, Węgier i Rosji."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264254
ms.assetid: 70b32d8d-6fa7-4617-ba74-a74bc6568d6e
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 870341b81e49c9fc677052e9ef87a580892f486f
ms.lasthandoff: 03/31/2017


---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a>Aktualizacja sposobu wyświetlania kwot w raportach i dokumenty

Ten temat zawiera informacje dotyczące aktualizacji, sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Republiki Czeskiej, Węgier i Rosji.

Dla osób prawnych w Estonii, Łotwy, Litwy, Polski, Republiki Czeskiej, Węgier i Rosji można skonfigurować pełne nazwy i krótkie nazwy jednostek walutowych i podjednostek. Tych nazw może służyć do przekształcania, jak kwoty są reprezentowane na dokumenty i raporty. Na przykład: ilość **LTL 100.20** mogą być wyświetlane jako **100 centów 20 lit**.

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a>Ustawianie długich i krótkich nazw jednostek walutowych i podjednostek
Aby skonfigurować długich i krótkich nazw jednostek waluty i podjednostek dla języka, wykonaj następujące kroki:

1.  Otwórz **walut** strony.
2.  Służy do wybrania waluty.
3.  W okienku akcji kliknij polecenie **przypadek**.
4.  Aby dodać pełną nazwę i krótka nazwa dla języka, kliknij przycisk **nowy** i wypełnij następujące pola.
    |                                                           |                                                                                                                                                                                                                    |
    |-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Field**                                                 | **Description**                                                                                                                                                                                                    |
    | **Language**                                              | Wybierz język dla bieżącego tekstu.                                                                                                                                                                          |
    | **Mianownik l. (nazwa grupy pól jednostki)**       | Wprowadź pojedynczej walucie. Na przykład pojedynczej lit jest lit.                                                                                                                         |
    | **Mianownik l. (nazwa grupy pól jednostki)**         | Wprowadź mnogiej waluty. Na przykład Podaj lity. **Uwaga:**: **Dopełniacz liczby pojedynczej** i **dopełniacz** pola są dostępne na podstawie języka wybranego w **języka** pole. |
    | **Pole mianownik liczby pojedynczej (nazwa grupy pól części)** | Wprowadź pojedynczej podjednostki waluty.                                                                                                                                                            |
    | **Mianownik l. (nazwa grupy pól części)**         | Wprowadź mnogiej podjednostki waluty.                                                                                                                                                              |
    | **Nazwa skrótowa jednostek (krótka nazwa grupy pól)**       | Wprowadź kod ISO do identyfikowania waluty. Na przykład wpisz LTL w celu identyfikowania litów.                                                                                                                             |
    | **Nazwa skrótowa części (krótka nazwa grupy pól)**      | Umożliwia wprowadzenie nazwy odmiany podjednostka. Na przykład Podaj centów.                                                                                                                                         |
    | **Conjunction 'and' between units and parts**             | Zaznacz, aby wydrukować razem "i" między jednostkami waluty i części jednostki. Na przykład na fakturach lub w raportach, kwota dla LTL 100.20 pojawi się jako 100 lit a 20 centów.                      |

5.  Click **Save**.



