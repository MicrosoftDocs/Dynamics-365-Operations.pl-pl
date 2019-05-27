---
title: Przetwarzanie arkusza alokacji księgi
description: Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2046e25719c9023bee99736488a4ee6f22723fe
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550828"
---
# <a name="process-ledger-allocation-journal"></a>Przetwarzanie arkusza alokacji księgi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej. Przed utworzeniem arkusza alokacji musi istnieć co najmniej jedna aktywna reguła alokacji księgi. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Księga główna > Alokacje > Przetwarzanie żądania alokacji.
2. W polu Reguła kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Na dzień wprowadź datę.
    * Wartość Na dzień jest bardzo ważna, jeżeli jest źródłem danych reguły jest księga. Ta data określa, które salda księgi mają być uwzględnione w alokacji.     W polu Źródło zerowe wybierz opcję Zatrzymaj. Spowoduje to zatrzymanie procesu alokacji i wyświetlenie komunikatu o wybraniu kwoty źródłowej równej 0 (zero).  
6. W polu Opcje propozycji wybierz opcję "Tylko propozycja".
    * Wybierz opcję Tylko propozycja, aby przejrzeć i opcjonalnie zatwierdzić wynik w arkuszach alokacji przed księgowaniem alokacji w księdze głównej.  
7. W polu Data księgowania w księdze głównej wprowadź datę.
8. Kliknij przycisk OK.
9. Wybierz kolejno opcje Księga główna > Alokacje > Arkusze alokacji.
10. Kliknij przycisk Wiersze.
11. Kliknij przycisk Księguj.
12. Kliknij przycisk Księguj.

