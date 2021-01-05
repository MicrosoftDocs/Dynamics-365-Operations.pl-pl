---
title: Elementy przepływu pracy
description: Ten temat zawiera opis różnych elementów składających się na przepływ pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b681d4da750df502987bd00ab52c1cb6eecdf30e
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694246"
---
# <a name="workflow-elements"></a>Elementy przepływu pracy

[!include [banner](../includes/banner.md)]

Ten temat zawiera opis różnych elementów składających się na przepływ pracy.

Przepływ pracy składa się z elementów. Sekcje poniżej opisują poszczególne typy elementów.

## <a name="tasks"></a>Zadania

*Zadanie* jest jednostką pracy, która musi zostać wykonana. Do przepływu pracy można dodawać dwa typy zadań: zadania ręczne i zadania automatyczne.

### <a name="manual-task"></a>Zadanie wykonywane ręcznie

*Zadanie ręczne* jest jednostką pracy, która musi zostać wykonana przez użytkownika. Na przykład przepływu pracy raportu z wydatków może mieć ręczne zadania, które wymagają, by przypisani użytkownicy wykonali następujące akcje:

- przejrzeć przyjęcia, które są przesyłane wraz z raportem z wydatków;
- wezwać przełożonego pracownika.

### <a name="automated-task"></a>Zadanie wykonywane automatycznie

*Zadanie automatyczne* jest jednostką pracy, która musi zostać wykonana przez system. Nie są wymagane żadne czynności wykonywane przez człowieka. Na przykład przepływ pracy zamówienia sprzedaży może mieć zadania automatyczne, które wymagają, aby system wykonał następujące akcje:

- sprawdzić kartę kredytową;
- utworzyć rekord odbiorcy dla odbiorcy, jeśli rekord jeszcze nie istnieje.

## <a name="approval-processes"></a>Procesy zatwierdzania

*Proces zatwierdzania* składa się z oddzielnych kroków. Na każdym kroku użytkownik może wykonać następujące akcje:

- zatwierdzić dokument;
- odrzucić dokument;
- zażądać wprowadzenia zmian w dokumencie;
- przypisać dokument innemu użytkownikowi w celu zatwierdzenia.

## <a name="line-item-workflow-elements"></a>Elementy przepływu pracy dla wiersza

Przepływ pracy można tworzyć w celu przetwarzania dokumentów lub pozycji w dokumencie. Na przykład utworzono przepływ pracy zatwierdzania dla kart czasu pracy. (Nazwiemy go *przepływem pracy dokumentu*). Do tego przepływu pracy dokumentu można dodać element *przepływu pracy dla wiersza*. Po uruchomieniu tego element wszystkie pozycje wiersza w dokumencie są przesyłane do przetworzenia. Czasami wszystkie elementy wiersza muszą być przetworzone przez ten sam przepływ pracy lub każdy element musi być przetwarzany przez różne przepływy pracy dla wierszy. Załóżmy, że pracownik przesłał kartę czasu pracy podobną do tej na obrazku poniżej.

![Przepływ pracy z pozycjami w wierszu](./media/workflow_lineitemworkflow.gif)

W tym scenariuszu można utworzyć następujące przepływy pracy dla towarów w wierszu:

- **Przepływ pracy utworzony dla pozycji w wierszu 1** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 1111.
- **Przepływ pracy utworzony dla pozycji w wierszu 2** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 2222.
- **Przepływ pracy utworzony dla pozycji w wierszu 3** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 3333.

## <a name="flow-control-elements"></a>Elementy kontroli przepływu

Poniższe elementy pozwalają projektować przepływy pracy z alternatywnymi oddziałami lub oddziałami działającymi jednocześnie.

### <a name="manual-decision"></a>Decyzja ręczna

*Ręczna decyzja* to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Użytkownik musi podjąć decyzję, która wskazuje odział używany do przetwarzania przesłanego dokumentu.

### <a name="conditional-decision"></a>Decyzja warunkowa

*Decyzja warunkowa* to również punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Jednak w tym przypadku to system decyduje, który oddział użyty do przetwarzania przesłanego dokumentu. Aby podjąć tę decyzję system ocenia dokument, aby ocenić, czy spełnia on określone warunki.

### <a name="parallel-activity"></a>Działanie równoległe

*Działanie równoległe* to element przepływu pracy, który zawiera dwie lub więcej gałęzi przepływu pracy, które są wykonywane w tym samym czasie

### <a name="subworkflow"></a>Podrzędny przepływ pracy

*Podrzędny przepływ pracy* jest przepływem pracy, który działa w kontekście innego przepływu pracy.
