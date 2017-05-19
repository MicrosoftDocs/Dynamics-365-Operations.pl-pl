---
title: "Elementy przepływu pracy"
description: "Ten artykuł zawiera opis różnych elementów składających się na przepływ pracy."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 05a35e91d3e502309c42c85960b5b1e2025f0e6e
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="workflow-elements"></a>Elementy przepływu pracy

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera opis różnych elementów składających się na przepływ pracy.

Przepływ pracy składa się z elementów. Sekcje poniżej opisują poszczególne typy elementów.

## <a name="tasks"></a>Zadania
*Zadanie* jest jednostką pracy, która musi zostać wykonana. Do przepływu pracy można dodawać dwa typy zadań: zadania ręczne i zadania automatyczne.

### <a name="manual-task"></a>Zadanie wykonywane ręcznie

*Zadanie ręczne* jest jednostką pracy, która musi zostać wykonana przez użytkownika. Na przykład przepływu pracy raportu z wydatków może mieć ręczne zadania, które wymagają, by przypisani użytkownicy wykonali następujące akcje:

-   przejrzeć przyjęcia, które są przesyłane wraz z raportem z wydatków;
-   wezwać przełożonego pracownika.

### <a name="automated-task"></a>Zadanie wykonywane automatycznie

*Zadanie automatyczne* jest jednostką pracy, która musi zostać wykonana przez system. Nie są wymagane żadne czynności wykonywane przez człowieka. Na przykład przepływ pracy zamówienia sprzedaży może mieć zadania automatyczne, które wymagają, aby system wykonał następujące akcje:

-   sprawdzić kartę kredytową;
-   utworzyć rekord odbiorcy dla odbiorcy, jeśli rekord jeszcze nie istnieje.

## <a name="approval-processes"></a>Procesy zatwierdzania
*Proces zatwierdzania* składa się z oddzielnych kroków. Na każdym kroku użytkownik może wykonać następujące akcje:

-   zatwierdzić dokument;
-   odrzucić dokument;
-   zażądać wprowadzenia zmian w dokumencie;
-   przypisać dokument innemu użytkownikowi w celu zatwierdzenia.

## <a name="lineitem-workflow-elements"></a>Elementy przepływu pracy dla wiersza
Przepływ pracy można tworzyć w celu przetwarzania dokumentów lub pozycji w dokumencie. Na przykład utworzono przepływ pracy zatwierdzania dla kart czasu pracy. (Nazwiemy go *przepływem pracy dokumentu*). Do tego przepływu pracy dokumentu można dodać element *przepływu pracy dla wiersza*. Po uruchomieniu tego element wszystkie pozycje wiersza w dokumencie są przesyłane do przetworzenia. Czasami wszystkie elementy wiersza muszą być przetworzone przez ten sam przepływ pracy lub każdy element musi być przetwarzany przez różne przepływy pracy dla wierszy. Załóżmy, że pracownik przesłał kartę czasu pracy podobną do tej na obrazku poniżej. ![Przepływ pracy z pozycjami wiersza](./media/workflow_lineitemworkflow.gif) W tym scenariuszu może być konieczne utworzenie następujących przepływów pracy dla wiersza:

-   **Przepływ pracy utworzony dla pozycji w wierszu 1** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 1111.
-   **Przepływ pracy utworzony dla pozycji w wierszu 2** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 2222.
-   **Przepływ pracy utworzony dla pozycji w wierszu 3** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 3333.

## <a name="flowcontrol-elements"></a>Elementy kontroli przepływu
Poniższe elementy pozwalają projektować przepływy pracy z alternatywnymi oddziałami lub oddziałami działającymi jednocześnie.

### <a name="manual-decision"></a>Decyzja ręczna

*Ręczna decyzja* to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Użytkownik musi podjąć decyzję, która wskazuje odział używany do przetwarzania przesłanego dokumentu.

### <a name="conditional-decision"></a>Decyzja warunkowa

*Decyzja warunkowa* to również punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Jednak w tym przypadku to system decyduje, który oddział użyty do przetwarzania przesłanego dokumentu. Aby podjąć tę decyzję system ocenia dokument, aby ocenić, czy spełnia on określone warunki.

### <a name="parallel-activity"></a>Działanie równoległe

*Działanie równoległe* to element przepływu pracy, który zawiera dwie lub więcej gałęzi przepływu pracy, które są wykonywane w tym samym czasie

### <a name="subworkflow"></a>Podrzędny przepływ pracy

*Podrzędny przepływ pracy* jest przepływem pracy, który działa w kontekście innego przepływu pracy.




