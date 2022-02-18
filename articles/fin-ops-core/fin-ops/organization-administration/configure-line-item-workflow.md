---
title: Konfigurowanie przepływów pracy dla pozycji w wierszach
description: W tym temacie wyjaśniono sposób konfigurowania elementu przepływu pracy dla pozycji w wierszu.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6d9dcb99e00d4ce3f99e525a72421cb12af178
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070128"
---
# <a name="configure-line-item-workflows"></a>Konfigurowanie przepływów pracy dla pozycji w wierszach

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]