---
title: Przetwarzanie arkusza alokacji księgi
description: W tym artykule wyjaśniono, jak przetwarzać żądania alokacji w aplikacji Dynamics 365 Finance.
author: aprilolson
ms.date: 07/26/2019
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
ms.openlocfilehash: b86f8f5d090d624e812d9e7e6c0bc0212e5e9716
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902437"
---
# <a name="process-ledger-allocation-journal"></a>Przetwarzanie arkusza alokacji księgi

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak przetwarzać żądania alokacji. Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej. Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. W okienku nawigacji przejdź do **Księga główna > Alokacja > Przetwarzanie żądania alokacji**.
2. W polu **Reguła** wybierz odpowiedni rekord z menu rozwijanego.
3. W polu **Na dzień** wprowadź datę.

    - Wartość **Na dzień** jest bardzo ważna, jeżeli źródłem danych reguły jest księga. Ta data określa, które salda księgi mają być uwzględnione w alokacji.  
    - W polu **Źródło zerowe** wybierz opcję **Zatrzymaj**. Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej zero.  

4. W polu **Opcje propozycji** wybierz opcję **Tylko propozycja**. Wybierz opcję **Tylko propozycja**, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.  
5. W polu Data księgowania w księdze głównej wprowadź datę.
6. Kliknij przycisk **OK**.
7. W okienku nawigacji przejdź do **Moduły > Księga główna > Alokacja > Arkusze alokacji**.
8. Wybierz **Linie**.
9. Wybierz opcję **Zaksięguj**.
10. Wybierz opcję **Zaksięguj**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
