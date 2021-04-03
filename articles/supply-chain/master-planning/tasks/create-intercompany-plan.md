---
title: Tworzenie planu międzyfirmowego
description: Ta procedura pokazuje, jak utworzyć plan międzyfirmowy.
author: ShylaThompson
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b64ababa618d58feb6095704e5978295060c96f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261124"
---
# <a name="create-an-intercompany-plan"></a>Tworzenie planu międzyfirmowego

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak utworzyć plan międzyfirmowy. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Konfigurowanie grupy planowania międzyfirmowego 
1. W **okienku nawigacji** przejdź do **Moduły > Planowanie główne > Konfiguracja > Grupy planowania międzyfirmowego**. 
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „10”.
3. Na liście oznacz wybrany wiersz.
4. Kliknij przycisk **Usuń**. Ten krok jest konieczny w celu przyspieszenia planowania międzyfirmowego.   Planowanie międzyfirmowe spowoduje wykonanie planowania głównego we wszystkich firmach w grupie planowania, zaczynając od planowania o najniższym numerze.  
5. Kliknij przycisk **Tak**.
6. Zamknij stronę.

## <a name="create-an-intercompany-plan"></a>Tworzenie planu międzyfirmowego
1. W **okienku nawigacji** przejdź do **Moduły > Planowanie główne > Obszary robocze > Planowanie główne**.
2. Kliknij opcję **Międzyfirmowe planowanie główne**.  
3. W polu **IGrupa planowania międzyfirmowego** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu. Wybierz grupę planowania międzyfirmowego 10.  
5. W polu **Liczba iteracji planowania międzyfirmowego** wpisz „2”. Grupa planowania międzyfirmowego 10 ma dwa elementy członkowskie. W celu rozpowszechnienia opóźnień z firmy źródłowej (USMF) do firmy odbiorcy (DEMF) należy wykonać planowanie międzyfirmowe dwa razy w obu firmach. Pierwsza iteracja spowoduje rozpowszechnienie informacji o zapotrzebowaniu i zidentyfikowanie opóźnień w firmie źródłowej (USMF). Druga iteracja rozpowszechni opóźnienia z firmy USMF do firmy DEMF.  
6. W polu **Pierwsza iteracja** wybierz opcję „Ponowne generowanie”.
7. W polu **Kolejne iteracje** wybierz opcję „Ponowne generowanie”.
8. W polu **Liczba wątków** wprowadź liczbę. Reprezentuje liczbę równoległych wątków używanych w planowaniu.  
9. Kliknij przycisk **OK**.

## <a name="view-the-result-of-the-plan"></a>Wyświetlanie wyniku planowania
1. W polu **Plan** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
2. Na liście kliknij łącze w wybranym wierszu. Kliknij łącze do planu statycznego. Musisz być w firmie USMF.  
3. Kliknij opcję **Zamówienia planowane**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]