---
title: Tworzenie budżetu konserwacji
description: W tym temacie wyjaśniono, jak utworzyć budżet konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 99f76c684150f154404cbb241daacb7a8d05f7f9
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571767"
---
# <a name="create-maintenance-budgets"></a>Tworzenie budżetu konserwacji

[!include [banner](../../includes/banner.md)]

 



Budżety konserwacji są używane w celu uzyskania przeglądu oczekiwanych kosztów konserwacji profilaktycznej. Wiersze budżetu są obliczane na podstawie wierszy harmonogramu konserwacji, w których oczekiwana jest data rozpoczęcia w okresie budżetowym.

Budżety obsługi są oparte na typach kosztów używanych w module Zarządzanie środkami trwałymi: **Zapobiegawcze**, **Korygujące** i **Inwestycyjne**. Koszty budżetowe związane z obsługą inwestycji są uwzględniane w aktywnych składnikach majątku, które mają datę wymiany w okresie budżetu oraz powiązaną wartość zamienną. Koszty budżetowe dotyczące konserwacji są uwzględniane, jeśli w obliczeniu budżetu jest uwzględniona wcześniejsza data korekty. W takim przypadku koszty korygujące z wcześniejszego okresu są obliczane dla tego samego przyszłego okresu, dla którego jest obliczany budżet konserwacji.

## <a name="create-a-maintenance-budget"></a>Stwórz budżet konserwacji

1. Wybierz **Zarządzanie składnikami majątku** \> **Zapytania** \> **Budżet konserwacji** \> **Budżet**.
2. Wybierz **Utwórz budżet**.
3. W polu **Budżet konserwacji** wprowadź identyfikator budżetu.
4. W polu **Opis wprowadź** opis.
4. Na skróconej karcie **Okres** w polach **Od dnia** i **Do dnia**, wprowadź datę początkową i końcową okresu budżetu.
5. Aby uwzględnić koszty z budżetu korygującego obliczone na podstawie kosztów rzeczywistych z poprzedniego okresu, w polu **Popraw od dnia** wprowadź datę początkową okresu, z którego mają być uwzględniane te koszty.
6. W zależności od poziomu szczegółowości wymaganego w budżecie należy określić odpowiednie opcje na pięciu kartach skróconych **Grupuj wg**.
7. Kliknij przycisk **OK**.
8. Wybierz **Wiersze budżetu**, aby otworzyć stronę **Wiersze budżetu konserwacji**, na której możesz przejrzeć wszystkie wiersze budżetu, które zostały utworzone dla okresu.
9. Aby zatwierdzić budżet, wybierz go na stronie **Budżety konserwacji**, a następnie wybierz pozycję **Zatwierdź**. Następnie w oknie dialogowym **Zatwierdź budżet** budżetu przycisk **OK**. Twoja nazwa użytkownika jest wprowadzana w polu **Zatwierdzone przez** na stronie **Budżety konserwacji**.

    > [!NOTE]
    > Po zatwierdzeniu budżetu konserwacji nie można ponownie obliczyć ani skorygować powiązanych wierszy na stronie **Wiersze budżetu konserwacji**, dopóki nie zostanie wcześniej usunięte zatwierdzenie. Aby usunąć potwierdzenie budżetu konserwacji, wybierz go na stronie **Budżety konserwacji**, a następnie wybierz pozycję **Zatwierdź**. Następnie w oknie dialogowym **Zatwierdź budżet** budżetu przycisk **OK**.

![Budżety konserwacji](media/01-maintenance-budgets.png)

Kopiując istniejący budżet można również utworzyć nowy budżet konserwacji. Na stronie **Budżety konserwacji** wybierz budżet do skopiowania, a następnie wybierz pozycję **Kopiuj**. Ta metoda jest przydatna na przykład wtedy, gdy użytkownik utworzył budżet na jeden miesiąc i chce skopiować go do innych miesięcy.

> [!NOTE]
> Budżet konserwacji oblicza tylko koszty budżetowe na podstawie wierszy harmonogramu konserwacji. Aby obliczyć koszty rzeczywiste za ten sam okres, można wykonać obliczenia na stronie kontrola **Formant kosztów składników majątku**. 
