--- 
title: "Przetwarzanie arkusza alokacji księgi"
description: "Na stronie Przetwarzanie żądania alokacji można utworzyć arkusz alokacji, który może być przeglądany i zatwierdzany przed księgowaniem w księdze głównej lub bezpośrednio księgowany w księdze głównej."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1189ffeae052c72542b3b403a6b7a6e415b005c4
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="process-ledger-allocation-journal"></a>Przetwarzanie arkusza alokacji księgi

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


