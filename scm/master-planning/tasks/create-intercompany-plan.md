--- 
title: "Tworzenie planu międzyfirmowego"
description: "Ta procedura pokazuje, jak utworzyć plan międzyfirmowy."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7c7f466add55fb9a24c3fb8f1f92df712a8622e3
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-an-intercompany-plan"></a>Tworzenie planu międzyfirmowego

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak utworzyć plan międzyfirmowy. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Konfigurowanie grupy planowania międzyfirmowego 
1. Przejdź do okna Grupy planowania międzyfirmowego.
    * Planowanie główne > Ustawienia > Grupy planowania międzyfirmowego  
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „10”.
3. Na liście oznacz wybrany wiersz.
4. Kliknij przycisk Usuń.
    * Ten krok jest konieczny w celu przyspieszenia planowania międzyfirmowego.   Planowanie międzyfirmowe spowoduje wykonanie planowania głównego we wszystkich firmach w grupie planowania, zaczynając od planowania o najniższym numerze.  
5. Kliknij przycisk Tak.
6. Zamknij stronę.

## <a name="create-an-intercompany-plan"></a>Tworzenie planu międzyfirmowego
1. Kliknij opcję Międzyfirmowe planowanie główne.
    * To jest w obszarze roboczym Planowanie główne.  
2. W polu Grupa planowania międzyfirmowego kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz grupę planowania międzyfirmowego 10.  
4. W polu Liczba iteracji planowania międzyfirmowego wpisz „2”.
    * Grupa planowania międzyfirmowego 10 ma dwa elementy członkowskie. W celu rozpowszechnienia opóźnień z firmy źródłowej (USMF) do firmy odbiorcy (DEMF) należy wykonać planowanie międzyfirmowe dwa razy w obu firmach. Pierwsza iteracja spowoduje rozpowszechnienie informacji o zapotrzebowaniu i zidentyfikowanie opóźnień w firmie źródłowej (USMF). Druga iteracja rozpowszechni opóźnienia z firmy USMF do firmy DEMF.  
5. W polu Pierwsza iteracja wybierz opcję.
6. W polu Pierwsza iteracja wybierz opcję „Ponowne generowanie”.
7. W polu Kolejne iteracje wybierz opcję „Ponowne generowanie”.
8. W polu Liczba wątków wprowadź liczbę.
    * Reprezentuje liczbę równoległych wątków używanych w planowaniu.  
9. Kliknij przycisk OK.

## <a name="view-the-result-of-the-plan"></a>Wyświetlanie wyniku planowania
1. W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
2. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij łącze do planu statycznego. Musisz być w firmie USMF.  
3. Kliknij opcję Zamówienia planowane.


