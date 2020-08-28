---
title: Konfigurowanie przepływów pracy dla pozycji w wierszach
description: W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f35676799a625656b6885cbc33d30870cee85e12
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698202"
---
# <a name="configure-line-item-workflows"></a>Konfigurowanie przepływów pracy dla pozycji w wierszach

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.

Aby skonfigurować element przepływu pracy dla pozycji w wierszu, w edytorze przepływu pracy kliknij element prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**. Następnie użyj poniższych procedur, aby skonfigurować właściwości elementu przepływu pracy dla pozycji w wierszu.

## <a name="name-the-line-item-workflow-element"></a>Nazywanie elementu przepływu pracy dla pozycji w wierszu

Należy wykonać następujące kroki, aby nadać nazwę elementowi przepływu pracy dla pozycji w wierszu.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Nazwa** wprowadź unikatową nazwę elementu przepływu pracy dla pozycji w wierszu.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Określanie, czy ten sam przepływ pracy ma być stosowany do przetwarzania wszystkich pozycji w wierszach

Wykonaj następujące kroki, aby określić, czy ten sam przepływ pracy będzie używany do przetwarzania wszystkich pozycji w wierszach w dokumencie.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Jeśli ten sam przepływ pracy ma przetwarzać wszystkie pozycje w wierszach w dokumencie, kliknij opcje **Wywołaj pojedynczy przepływ pracy dla wszystkich elementów wiersza**. Następnie wybierz przepływ pracy, który ma być stosowany do pozycji w wierszach.
3. Jeśli określony przepływ pracy ma przetwarzać pozycje w wierszach spełniające określony zbiór warunków, kliknij opcję **Wywołaj przepływ pracy dla wszystkich elementów wiersza**. Następnie wykonaj następujące czynności, aby zdefiniować zestaw warunków:

    1. Kliknij przycisk **Dodaj**.
    2. Zaznacz warunek w tabeli.
    3. Na karcie **Nazwa warunku** nadaj nazwę zestawowi warunków, który definiujesz.
    4. Kliknij przycisk **Dodaj warunek** i wprowadź warunek.
    5. Wprowadź wszelkie wymagane dodatkowe warunki.
    6. Aby sprawdzić, czy wprowadzony zbiór warunków jest poprawnie skonfigurowany, kliknij przycisk **Testuj**. Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord i kliknij przycisk **Testuj**. System oszacuje rekord i określi, czy rekord spełnia określone warunki. Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.

    Na karcie **Przepływy pracy** wybierz przepływ pracy, który ma być używany do przetwarzania pozycji w wierszach spełniających utworzony zbiór warunków.
