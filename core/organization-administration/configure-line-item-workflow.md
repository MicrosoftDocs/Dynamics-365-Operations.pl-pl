---
title: "Konfigurowanie przepływu pracy dla pozycji w wierszu"
description: "W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c2b2c863d0783bd436db57d9fd3c7c5aa8dba5c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-line-item-workflow"></a>Konfigurowanie przepływu pracy dla pozycji w wierszu

W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.

Aby skonfigurować element przepływu pracy dla pozycji w wierszu, w edytorze przepływu pracy kliknij element prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie użyj poniższych procedur, aby skonfigurować właściwości elementu przepływu pracy dla pozycji w wierszu.

## <a name="name-the-lineitem-workflow-element"></a>Nazwa elementu przepływu pracy lineitem
Należy wykonać następujące kroki, aby nadać nazwę elementowi przepływu pracy dla pozycji w wierszu.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Nazwa** wprowadź unikatową nazwę elementu przepływu pracy dla pozycji w wierszu.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Określanie, czy ten sam przepływ pracy ma być stosowany do przetwarzania wszystkich pozycji w wierszach
Wykonaj następujące kroki, aby określić, czy ten sam przepływ pracy będzie używany do przetwarzania wszystkich pozycji w wierszach w dokumencie.

1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  Jeśli ten sam przepływ pracy ma przetwarzać wszystkie pozycje w wierszach w dokumencie, kliknij opcje **Wywołaj pojedynczy przepływ pracy dla wszystkich elementów wiersza**. Następnie wybierz przepływ pracy, który ma być stosowany do pozycji w wierszach.
3.  Jeśli określony przepływ pracy ma przetwarzać pozycje w wierszach spełniające określony zbiór warunków, kliknij opcję **Wywołaj przepływ pracy dla wszystkich elementów wiersza**. Następnie wykonaj następujące czynności, aby zdefiniować zestaw warunków:
    1.  Kliknij przycisk **Dodaj**.
    2.  Zaznacz warunek w tabeli.
    3.  Na karcie **Nazwa warunku** nadaj nazwę zestawowi warunków, który definiujesz.
    4.  Kliknij przycisk **Dodaj warunek** i wprowadź warunek.
    5.  Wprowadź wszelkie wymagane dodatkowe warunki.
    6.  Aby sprawdzić, czy wprowadzony zbiór warunków jest poprawnie skonfigurowany, kliknij przycisk **Testuj**. Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord i kliknij przycisk **Testuj**. System oszacuje rekord i określi, czy rekord spełnia określone warunki. Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.

    Na karcie **Przepływy pracy** wybierz przepływ pracy, który ma być używany do przetwarzania pozycji w wierszach spełniających utworzony zbiór warunków.



