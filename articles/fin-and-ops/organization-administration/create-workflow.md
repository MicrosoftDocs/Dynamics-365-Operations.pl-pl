---
title: "Tworzenie przepływu pracy"
description: "W tym temacie wyjaśniono, jak utworzyć przepływ pracy."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ee3f60575d0eaaf56ce08adb1936728a76488dac
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-workflow"></a>Tworzenie przepływu pracy

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak utworzyć przepływ pracy.

<a name="open-the-workflow-editor"></a>Otwórz edytor przepływu pracy
------------------------

Moduł programu Microsoft Dynamics 365 for Finance and Operations, w którym pracujesz, określa typy przepływów pracy, jakie można tworzyć. Wykonaj następujące kroki, aby wybrać typ tworzonego przepływu pracy i otworzyć edytora przepływu pracy.

1.  Otwórz moduł, dla którego chcesz utworzyć nowy przepływ pracy. Aby na przykład utworzyć przepływ pracy dla zapotrzebowań na zakup, kliknij opcję **Zaopatrzenie i sourcing**.
2.  Kliknij kolejno opcje **Ustawienia** &gt; **Przepływy pracy modułu \[nazwa modułu\]**.
3.  Na wyświetlonej stronie listy w okienku akcji kliknij przycisk **Nowy**.
4.  Na stronie **Utwórz przepływ pracy** wybierz typ przepływu pracy, który ma zostać utworzony, i kliknij przycisk **Utwórz przepływ pracy**. Zostanie wyświetlony edytor przepływu pracy. Teraz można użyć poniższych procedur w celu zaprojektowania przepływu pracy.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Przeciągnij elementy przepływu pracy na kanwę
Obszar **Elementy przepływu pracy** w edytorze przepływu pracy zawiera elementy, które można dodawać do przepływu pracy. Aby dodać elementy do przepływu pracy, przeciągnij na kanwę.

## <a name="connect-the-elements"></a>Połącz elementy
Aby połączyć jeden element przepływu pracy z innym, przytrzymaj wskaźnik nad elementem, aż punkty połączeń zostaną wyświetlone. Kliknij punkt połączenia i przeciągnij go do innego elementu. Należy pamiętać, aby łączyć wszystkie elementy.

## <a name="configure-the-properties-of-the-workflow"></a>Konfigurowanie właściwości przepływu pracy
Wykonaj poniższe czynności, aby skonfigurować właściwości przepływu pracy.

1.  Kliknij kanwę, aby upewnić się, że nie został wybrany żaden element przepływu pracy.
2.  Kliknij przycisk **Właściwości**. a zostanie otwarta strona **Właściwości** dotycząca przepływu pracy.
3.  Wykonaj procedury opisane w temacie [Konfigurowanie właściwości przepływu pracy](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Konfigurowanie elementów przepływu pracy
Skonfiguruj każdy element przeciągnięty na kanwę. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania każdego elementu przepływu pracy, zobacz następujące tematy.

-   [Konfigurowanie zadania ręcznego](configure-manual-task-workflow.md)
-   [Konfigurowanie zadania wykonywanego automatycznie](configure-automated-task-workflow.md)
-   [Konfigurowanie procesu zatwierdzania](configure-approval-process-workflow.md)
-   [Konfigurowanie kroku zatwierdzania](configure-approval-step-workflow.md)
-   [Konfigurowanie decyzji ręcznej](configure-manual-decision-workflow.md)
-   [Konfigurowanie decyzji warunkowej](configure-conditional-decision-workflow.md)
-   [Konfigurowanie działania równoległego](configure-parallel-activity-workflow.md)
-   [Konfigurowanie odgałęzienia równoległego](configure-parallel-branch-workflow.md)
-   [Konfigurowanie przepływu pracy dla pozycji w wierszu](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Rozwiąż wszelkie błędy lub ostrzeżenia
Okienko **Błędy i ostrzeżenia** w dolnej części edytora przepływu pracy pokazuje komunikaty, które zostały wygenerowane dla przepływu pracy. Aby znaleźć element, w którym wystąpił błąd lub ostrzeżenie, kliknij dwukrotnie błąd lub ostrzeżenie. Wszystkie błędy i ostrzeżenia muszą zostać rozwiązane przed uaktywnieniem przepływu pracy.

## <a name="save-and-activate-the-workflow"></a>Zapisywanie i aktywowanie przepływu pracy
Gdy wszystko jest gotowe do zapisania i aktywacji przepływu pracy, wykonaj następujące kroki.

1.  Kliknij przycisk **Zapisz i zamknij**, aby zamknąć edytor i otworzyć stronę **Zapisz przepływ pracy**.
2.  Wprowadź komentarze dotyczące zmian wprowadzonych w przepływie pracy i kliknij przycisk **OK**.
3.  Jeśli wszystkie błędy i ostrzeżenia zostały rozwiązane, zostanie wyświetlona strona **Aktywacja przepływu pracy**. Umożliwia wybranie jednej z następujących opcji:
    -   Aby uaktywnić tę wersję przepływu pracy, kliknij przycisk **Uruchom nową wersję**. Gdy przepływ pracy jest aktywny, użytkownicy mogą przesyłać do niego dokumenty w celu przetwarzania.
    -   Jeśli nie chcesz uaktywnić tej wersję, kliknij przycisk **Nie aktywuj nowej wersji**. Możesz aktywować przepływ pracy później.






