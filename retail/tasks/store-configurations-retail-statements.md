--- 
title: "Konfiguracje sklepu dla zestawień sieci sprzedaży"
description: "Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 2f73bca3bd1699ee1c2e98706a4d69f8b0b25052
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="store-configurations-for-retail-statements"></a>Konfiguracje sklepu dla zestawień sieci sprzedaży

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży. Wymiary finansowe w sklepach sieci sprzedaży są omówione w innej procedurze. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
    * Ustawienia w sekcji Zestawienie/zamknięcie wpływają na tworzenie, sprawdzanie poprawności i księgowanie zestawień dla sklepu.  Otwórz sekcję Zestawienie/zamknięcie.  
    * Wybierz metodę, której chcesz używać do grupowania wierszy zestawienia.  
    * Wybierz opcję „Tak”, jeśli ma być tworzone tylko jedno zestawienie dziennie podczas wykonywania zadania wsadowego tworzenia zestawień.  
    * Pole Obliczenia deklaracji środków płatniczych określa, czy deklaracje środków płatniczych powinny być dodawane razem czy też ma być używana ostatnia deklaracja.  
    * Wybierz konto księgowe do księgowania różnic zaokrągleń.  
    * W polu Maksymalna różnica zaokrągleń można wprowadzić maksymalną dozwoloną różnicę zaokrąglenia.  
    * W polu Księgowanie można wprowadzić maksymalną łączną rozbieżność księgowania dozwoloną dla zestawienia.  
    * W polu Zmiana można wprowadzić maksymalną łączną rozbieżność dozwoloną w granicach zmiany w zestawieniu.  
    * W polu Transakcja można wprowadzić maksymalną łączną rozbieżność dozwoloną w wierszu zestawienia.  
    * W polu Metoda zamknięcia można określić, czy transakcje, które zostaną uwzględnione w zestawieniu, powinny być częścią zamkniętej zmiany czy też mogą być dowolnymi transakcjami o zdefiniowanym zakresie daty/godziny.  
    * W polu Koniec dnia roboczego można wprowadzić godzinę, jeśli transakcje zachodzące po północy mają być księgowane w poprzednim dniu.  
    * Wybierz opcję „Tak”, jeśli transakcje zachodzące po północy mają być księgowane jako część poprzedniego dnia.  
    * Wybierz opcję „Tak”, aby zestawienia były tworzone dla każdej zdefiniowanej metody wykonywania zestawień. Może to być przydatne, jeśli wydajność księgowania wymaga poprawy dla sklepów o dużym wolumenie transakcji, ponieważ spowoduje to utworzenie wielu mniejszych zestawień, które mogą być przetwarzane jednocześnie.  
    * W polu Domyślny odbiorca można wybrać konto odbiorcy na potrzeby sprzedaży klientom przypadkowym.  


