---
title: Konfigurowanie i realizowanie zadań księgowania zestawień
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów.
author: josaw1
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52baa707c36f3468263782dc8ec735e44af88e38
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804240"
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