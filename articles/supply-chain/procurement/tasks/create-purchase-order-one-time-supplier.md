---
title: Tworzenie zamówienia zakupu dla dostawcy jednorazowego
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży dla dostawcy jednorazowego.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe76a3d481c3bc8dd3a3d45eda031df61ece4aa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812380"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]