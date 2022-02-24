---
title: Tworzenie zamówienia zakupu dla dostawcy jednorazowego
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c4885547cdf2f8496446761e27ce39e67e670f15
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016409"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego. Dostawca jest tworzony automatycznie razem z zamówieniem zakupu, a nie ręcznie. W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Warunkiem wstępnym jest wcześniejsze utworzenie konta dostawcy jednorazowego na stronie Parametry modułu rozrachunków z dostawcami.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Tworzenie zamówienia zakupu dla dostawcy jednorazowego
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Dostawca jednorazowy zaznacz opcję Tak.
    * Konto dostawcy jest automatycznie tworzone i przypisywane do zamówienia zakupu. Konto dostawcy jest tworzone na podstawie szablonu określonego na karcie Ogólne na stronie Parametry modułu rozrachunków z dostawcami.  
4. W polu Nazwa nadaj nazwę dostawcy.
5. Kliknij przycisk OK.
    * Zamówienie zakupu można teraz sfinalizować i przetwarzać jak każde inne zamówienie. Nie istnieją żadne specjalne cechy w tym procesie. Faktura uwzględni planowaną transakcję na koncie dostawcy utworzonym razem z zamówieniem, po czym zostanie przetworzona płatność.

