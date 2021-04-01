---
title: Konfigurowanie i realizowanie zadań księgowania zestawień
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b1401d51491205731843abe6e2278f798c5c979
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232744"
---
# <a name="configure-and-run-job-to-post-statements"></a>Konfigurowanie i realizowanie zadań księgowania zestawień

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Wszystkie obszary robocze > .. > Finanse sklepu.
2. Kliknij Zaksięguj zestawienia w partii.
    * Wybierz hierarchię organizacyjną, a następnie w drzewie węzłów organizacji zaznacz jeden sklep lub węzeł. Wybierz węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.  
    * Kliknij strzałkę, aby dodać zaznaczone obiekty.  
3. Kliknij kartę Uruchom w tle. ![Uruchom w tle](../dev-itpro/media/runbackground.png "Uruchom w tle") 
4. Zaznacz pole wyboru Przetwarzanie wsadowe lub usuń jego zaznaczenie.
![Przetwarzanie wsadowe](../dev-itpro/media/batchprocessing.png "Cykl i przetwarzanie wsadowe") 
5. Kliknij przycisk Cykl.
6. W polu Data początkowa wprowadź datę.
7. W polu Godzina rozpoczęcia wprowadź godzinę.
    * Wybierz, czy chcesz zakończyć cykl po określonej liczbie sesji, w określonym dniu czy nigdy. Następnie wybierz różne opcje, aby określić, jak często zadanie ma być wykonywane.  
8. Kliknij przycisk OK.
9. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]