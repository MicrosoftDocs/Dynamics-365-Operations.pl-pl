---
title: Przetwarzanie arkusza alokacji księgi
description: W tym artykule wyjaśniono, jak przetwarzać żądania alokacji w aplikacji Dynamics 365 Finance.
author: aprilolson
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f22b5042e0e3726afcb1061852fdbd8de770c61
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779400"
---
# <a name="process-ledger-allocation-journal"></a>Przetwarzanie arkusza alokacji księgi

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak przetwarzać żądania alokacji. Na stronie **Przetwarzanie żądania alokacji** można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej. Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. W okienku nawigacji przejdź do **Księga główna > Alokacja > Przetwarzanie żądania alokacji**.
2. W polu **Reguła** wybierz odpowiedni rekord z menu rozwijanego.
3. W polu **Na dzień** wprowadź datę.

    - Wartość **Na dzień** jest bardzo ważna, jeżeli źródłem danych reguły jest księga. Ta data określa, które salda księgi mają być uwzględnione w alokacji.  
    - W polu **Źródło zerowe** wybierz opcję **Zatrzymaj**. Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej zero.  

4. W polu **Opcje propozycji** wybierz opcję **Tylko propozycja**. Wybierz opcję **Tylko propozycja**, aby przejrzeć i opcjonalnie zatwierdzić wynik w **arkuszach alokacji** przed księgowaniem alokacji w księdze głównej.  
5. W polu **Data księgowania** w księdze głównej wprowadź datę.
6. Kliknij przycisk **OK**.
7. W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Arkusze alokacji**.
8. Wybierz **Linie**.
9. Wybierz opcję **Zaksięguj**.
10. Wybierz opcję **Zaksięguj**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
