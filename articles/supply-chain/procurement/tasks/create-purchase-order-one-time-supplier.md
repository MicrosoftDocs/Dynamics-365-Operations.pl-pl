--- 
title: "Tworzenie zamówienia zakupu dla dostawcy jednorazowego"
description: "W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2d4dabaf6e1d79cbd626294ee4e327f2725a5e43
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego. Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie. W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Dostawca jednorazowy zaznacz opcję Tak.
    * Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu. Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.  
4. W polu Nazwa nadaj nazwę dostawcy.
5. Kliknij przycisk OK.
    * Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie. Nie istnieją żadne specjalne cechy w tym procesie. Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność. Po zakończeniu tej operacji można usunąć konto dostawcy. Zazwyczaj jest to realizowane przez dział rozrachunków z dostawcami.  


