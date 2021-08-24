---
title: Przetwarzanie zmian sytuacji życiowej
description: W trakcie cyklu życia pracownika w module Microsoft Dynamics 365 Human Resources każdy pracownik może przechodzić różne zmiany sytuacji życiowej.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6bfbb9e31a7d8973c2b993f3792a7216f41924e0ff4c24b08c0dd954ab327c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775024"
---
# <a name="process-life-events"></a>Przetwarzanie zmian sytuacji życiowej

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W trakcie cyklu życia pracownika w module Microsoft Dynamics 365 Human Resources każdy pracownik może przechodzić różne zmiany sytuacji życiowej. Na przykład zawarcie małżeństwa, zmiana w zatrudnieniu lub zmiana osoby na utrzymaniu/beneficjenta. Aby można było wprowadzać zmiany sytuacji życiowej, należy włączyć funkcję zmian sytuacji życiowej w formularzu Parametry świadczeń, skonfigurować typy zmian sytuacji życiowej oraz skonfigurować opcje zmian sytuacji życiowej dla typów planów.

Aby można było przetwarzać zmiany sytuacji życiowej, należy wcześniej uruchomić otwartą rejestrację co najmniej raz w trakcie okresie zatrudniania. W Stanach Zjednoczonych otwarta rejestracja zazwyczaj odbywa się raz na rok. Poza Stanami Zjednoczonymi otwarta rejestracja może być wykonywana w momencie zatrudniania. Pracownik nie musi wybrać planu świadczeń, aby zmiany sytuacji życiowej były przetwarzane, ale musi być uwzględniony w przetwarzaniu otwartej rejestracji. 

Przetwarzanie zmian sytuacji życiowej należy stosować w przypadku, gdy w organizacji istnieją pracownicy ze zmianami sytuacji życiowej przypadającymi w przyszłości. To zdarzenie spowoduje przetwarzanie wszystkich zmian sytuacji życiowej, które nie zostały przetworzone (takich jak przyszłe zmiany sytuacji życiowej czy dodane zmiany sytuacji życiowej, które nie są specyficzne dla żadnego pracownika, takie jak wprowadzenie nowego świadczenia). Zmiany sytuacji życiowej zachodzące w czasie rzeczywistym są ukryte.

Na przykład jeśli dzisiejsza data to 1 lutego, a 14 lutego pracownik Jan Kowalski ma zmienić zatrudniającą go firmę, to po uruchomieniu przetwarzania zmian sytuacji życiowej w dniu 15 lutego system przetworzy wszystkie zmiany do dnia 15 lutego włącznie. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie zdarzenia zmiany sytuacji życiowej**.

2. W oknie dialogowym **Uruchom proces zdarzenia zmiany sytuacji życiowej** określ wartości następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Okres rejestracji** | Okres rejestracji, dla którego mają być przetwarzane zmiany sytuacji życiowej. |
   | **Firma** | Firma, dla której mają być przetwarzane zmiany sytuacji życiowej. |
   | **Data zdarzenia zmiany sytuacji życiowej** | System przetwarza wszystkie zdarzenia w okresie rejestracji, który nastąpiły do tej daty. |
   | **Pracownik** | Pracownik, dla którego mają być przetwarzane zmiany sytuacji życiowej. Jeśli to pole pozostanie puste, zmiany sytuacji życiowej będą przetwarzane dla wszystkich pracowników. |

3. Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Umożliwia wprowadzanie informacji o przetwarzaniu.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces będzie uruchamiany z parametrami określonymi przez użytkownika.

4. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]