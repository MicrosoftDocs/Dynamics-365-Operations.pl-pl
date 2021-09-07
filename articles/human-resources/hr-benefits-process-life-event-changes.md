---
title: Przetwarzanie zmian zdarzeń zmiany sytuacji życiowej
description: W tym temacie opisano sposób przetwarzania zdarzeń zmiany sytuacji życiowej w aplikacji Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 30834b685c535d464dbe016d92579752fac4b7fa
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417540"
---
# <a name="process-life-event-changes"></a>Przetwarzanie zmian zdarzeń zmiany sytuacji życiowej

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W programie Microsoft Dynamics 365 Human Resources można przetwarzać dwa rodzaje zmian sytuacji życiowej:

- Zmiany związane z narodzinami
- Zmiany wygaśnięcia zastąpienia reguły uprawnienia 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie zmian zdarzeń sytuacji życiowej**.

2. W oknie dialogowym **Uruchom proces zmian zdarzenia zmiany sytuacji życiowej** określ wartości następujących pól:

   | Pole | Opis |
   | --- | --- |
   | Okres rejestracji | Okres rejestracji, dla którego mają być przetwarzane zmiany sytuacji życiowej. |
   | Firma | Firma, dla której mają być przetwarzane zmiany sytuacji życiowej. |

3. Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Umożliwia wprowadzanie informacji o przetwarzaniu.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces będzie uruchamiany z parametrami określonymi przez użytkownika.

4. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
