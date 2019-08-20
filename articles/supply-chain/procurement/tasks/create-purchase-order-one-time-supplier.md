---
title: Tworzenie zamówienia zakupu dla dostawcy jednorazowego
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26c62aa72a7919c780bb709b185b48c97066c538
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836319"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego. Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie. W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Dostawca jednorazowy zaznacz opcję Tak.
    * Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu. Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.  
4. W polu Nazwa nadaj nazwę dostawcy.
5. Kliknij przycisk OK.
    * Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie. Nie istnieją żadne specjalne cechy w tym procesie. Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność. Po zakończeniu tej operacji można usunąć konto dostawcy. Zazwyczaj jest to realizowane przez dział rozrachunków z dostawcami.  

