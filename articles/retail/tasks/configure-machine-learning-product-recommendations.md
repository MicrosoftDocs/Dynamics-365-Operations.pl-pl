--- 
title: "Konfigurowanie rekomendacji produktów przy użyciu uczenia maszynowego"
description: "Ta procedura odświeża listę danych w magazynie jednostek używanym przez system uczenia maszynowego dostarczający rekomendacji produktów, a następnie umożliwia rekomendowanie produktów na urządzeniach klienckich w punkcie sprzedaży."
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BIMeasurementDeployManagementEntityStore, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 277ffb879b80fe57deeaa2b52c1543baaf820274
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a>Konfigurowanie rekomendacji produktów przy użyciu uczenia maszynowego

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura odświeża listę danych w magazynie jednostek używanym przez system uczenia maszynowego dostarczający rekomendacji produktów, a następnie umożliwia rekomendowanie produktów na urządzeniach klienckich w punkcie sprzedaży. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Administrowanie systemem > Ustawienia > Magazyn jednostek.
2. Na liście znajdź i zaznacz rekord „RetailSales”.
3. Kliknij przycisk Odśwież.
4. Kliknij przycisk OK.
5. Zamknij stronę.
6. Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.
7. Kliknij kartę Uczenie maszynowe.
8. W polu Włącz rekomendacje produktów zaznacz opcję „Tak”.
    * Jeśli zostanie wyświetlony komunikat „Nie można pobrać modeli rekomendacji”, wynika to z faktu, że magazyn jednostek był odświeżany bardzo niedawno i system mógł jeszcze nie ukończyć przyswajania nowych danych. Odczekaj 2-3 godziny i spróbuj ponownie.  
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.


