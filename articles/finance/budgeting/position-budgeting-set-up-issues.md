---
title: Rozwiązywanie problemów z budżetowaniem stanowisk
description: Ten artykuł zawiera odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania budżetowania stanowisk. Odpowiada na często zadawane pytania na temat tworzenia składników kosztu budżetowego, grup wynagrodzeń i siatek wynagrodzeń.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8211c5bd4514bffbd001f9930859f777dac7f0e1
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017624"
---
# <a name="position-budgeting-troubleshooting"></a>Rozwiązywanie problemów z budżetowaniem stanowisk

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania budżetowania stanowisk. Odpowiada na często zadawane pytania na temat tworzenia składników kosztu budżetowego, grup wynagrodzeń i siatek wynagrodzeń. 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Dlaczego nie można odnaleźć strony stanowiska podlegającego prognozie w module Zasoby ludzkie?
---------------------------------------------------------------

Stanowiska podlegające prognozie zostały przeniesione do moduł Budżetowanie.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Dlaczego nie można usunąć składnika kosztu budżetowego?
Nie można usunąć składnika kosztu budżetowego, który jest przypisany do stanowiska podlegającego prognozie. Aby można było usunąć składnik kosztu budżetowego, należy go wykasować ze wszystkich stanowisk podlegających prognozie. **Porada:** Aby znaleźć wszystkie stanowiska, do których przypisano składnik kosztu budżetowego, zaznacz składnik kosztu na stronie **Składniki kosztu budżetowego** , a następnie kliknij przycisk **Aktualizuj stanowiska**. Stanowiska, które używają składnika kosztu, znajdują się w górnej siatce.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Jak można usunąć składnik kosztu z wielu stanowisk podlegających prognozie bez konieczności otwierania każdego z nich?
Nie można usunąć składnika kosztu. Jednak jeśli zmienisz daty rozpoczęcia i zakończenia, tak aby przypadały poza datami cyklu planowania budżetu, składnik kosztu nie będzie już przypisany do stanowisk podlegających prognozie w tym cyklu planowania budżetu. Aby wprowadzić tę zmianę, otwórz składnik kosztu budżetowego, a następnie na skróconej karcie **Obliczanie kosztów** kliknij przycisk **Zmień daty** i zmień datę wejścia w życie lub datę ważności. Następnie kliknij przycisk **OK**, co spowoduje automatyczną aktualizację wszystkich stanowisk podlegających prognozie, do których jest przypisany ten składnik kosztu. **Porada:** Korzystając z tej metody, należy pamiętać, że usunie ona składnik kosztu budżetowego ze **wszystkich** stanowisk podlegających prognozie, w których daty rozpoczęcia i zakończenia nie przypadają już w odpowiednim przedziale. Jeśli ten efekt jest niepożądany, trzeba otworzyć każde stanowisko podlegające prognozie, z którego chcesz usunąć składnik kosztu budżetowego, i ręcznie wprowadzić zmianę.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Dlaczego nie można wprowadzić kwoty rocznej na skróconej karcie Obliczanie kosztów dla składnika kosztu budżetowego?
Nie można wprowadzić kwoty rocznej, jeśli na skróconej karcie **Podstawa obliczania** istnieją składniki kosztu budżetowego, ponieważ system wymaga wartości procentowej do obliczenia wartości kwotowej. Aby zmienić tę wartość, usuń wszystkie składniki kosztu budżetowego ze skróconej karty **Podstawa obliczania**.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Dlaczego nie można zmienić typu kosztu budżetowego z „zarobki” na inny typ kosztu budżetowego?
Niektóre składniki kosztu budżetowego używają składnika kosztu „zarobki” jako podstawy obliczeń. Aby zmienić wartość w polu **Typ kosztu budżetowego**, usuń składnik kosztu „zarobki” ze skróconej karty **Podstawa obliczania** we wszystkich składnikach kosztów budżetowych.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Dlaczego nie można zmienić daty w wierszach składnika kosztu budżegowego dla składnika kosztu budżetowego?
Nie można zmienić daty w wierszu składnika kosztu budżetowego, gdy składnik kosztu budżetowego jest używany przez stanowisko podlegające prognozie. To ograniczenie pomaga zagwarantować, że stanowiska podlegające prognozie są zawsze zgodne z wytycznymi dla składnika kosztu budżetowego. Aby zmienić tę datę, na skróconej karcie **Obliczanie kosztów** kliknij przycisk **Zmień daty** i wprowadź nowe daty. Następnie kliknij przycisk **OK**, co spowoduje aktualizację stanowisk, do których jest przypisany ten składnik kosztu.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Dlaczego nie można zmienić kosztów dla składnika kosztu budżetowego na stronie Grupa wynagrodzeń?
Składniki kosztu budżetowego można tworzyć i modyfikować tylko na stronie **Składniki kosztu budżetowego**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Dlaczego widzę komunikat o błędzie po zmianie dat w składniku kosztu dla stanowiska podlegającego prognozie?
Daty w wierszu składnika kosztu stanowiska podlegającego prognozie muszą się zawierać w następujących zakresach:

-   Daty aktywacji i przejścia na emeryturę stanowiska.
-   Daty aktywacji i ważności składnika kosztu budżetowego.
-   Daty początkowa i końcowa cyklu budżetu skojarzonego z procesem planowania budżetu dla stanowiska podlegającego prognozie.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]