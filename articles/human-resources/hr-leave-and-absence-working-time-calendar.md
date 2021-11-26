---
title: Tworzenie kalendarza czasu pracy
description: Tu opisano definiowanie kalendarza czasu pracy, świąt i czasu wolnego od pracy w module Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09449b832c403b0f711c3827ad20fc5aa618fbc4
ms.sourcegitcommit: 1cc56643160bd3ad4e344d8926cd298012f3e024
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731500"
---
# <a name="create-a-working-time-calendar"></a>Tworzenie kalendarza czasu pracy

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Kalendarz czasu pracy w programie Dynamics 365 Human Resources zawiera dni i godziny, kiedy pracownicy pracują w organizacji. Gdy pracownik prześle wniosek urlopowy, nie musi martwić się o święta ani dni zamknięcia zakładu.

Aby usprawnić obsługę wniosków urlopowych, skonfiguruj te elementy w swojej organizacji:

- Kalendarz czasu pracy
- Święta i dni wolne od pracy
- Czas wolny od pracy

Dwa ostatnie elementy można dodać podczas konfigurowania kalendarza czasu pracy. Można je również konfigurować lub aktualizować osobno.

## <a name="set-up-a-working-time-calendar"></a>Konfigurowanie kalendarza czasu pracy

Skonfiguruj co najmniej jeden kalendarz czasu pracy, który pokazuje dni i godziny działania zakładu/biura. Jeśli istnieją lokalizacje w wielu krajach i regionach, może być konieczne skonfigurowanie kalendarza czasu pracy niezależnie dla każdego obszaru.

1. Na stronie **Administrowanie organizacją** wybierz opcję **Kalendarze**.

2. Kliknij przycisk **Nowy** i nadaj kalendarzowi nazwę oraz wprowadź opis.

3. W obszarze **Opcje generowania** wybierz dni robocze w organizacji i wprowadź czas pracy. 
   - Aby dodać święto lub dzień zamknięcia zakładu, kliknij przycisk **Dodaj** obok pozycji **Święta i dni wolne od pracy**.
   - Aby dodać czas wolny od pracy, np. obiady lub przerwy, w obszarze **CZAS WOLNY OD PRACY** kliknij przycisk **Dodaj**, a następnie wprowadź nazwę i przedział czasu.

4. Na karcie **Dni** wybierz opcję **Generuj**, aby wygenerować dni w kalendarzu. Wprowadź zakres dat w kalendarzu, a następnie wybierz opcję **Generuj dni**.

5. Aby dodać harmonogramy pracy, w obszarze **Harmonogram pracy** wybierz opcję **Dodaj**, a następnie wprowadź godziny dla każdego harmonogramu pracy.

## <a name="configure-holidays-and-closures"></a>Konfigurowanie świąt i dni wolnych od pracy

Święta i dni wolne można dodawać lub zmieniać niezależnie od kalendarza czasu pracy.

1. Na stronie **Administrowanie organizacją** wybierz opcję **Święta i dni wolne od pracy**.

2. Wybierz opcję **Nowy**, a następnie wprowadź nazwę i datę święta lub dnia wolnego od pracy.

## <a name="configure-non-work-time"></a>Konfigurowanie czasu wolnego od pracy

Czas wolny od pracy można dodawać lub zmieniać niezależnie od kalendarza czasu pracy.

1. Na stronie **Administrowanie organizacją** wybierz opcję **NON-WORK TIME**.

2. Kliknij opcję **Nowy**, a następnie wprowadź nazwę i przedział czasu dla czasu wolnego od pracy.

Jeśli włączono funkcję w wersji zapoznawczej o nazwie Korekty urlopów i nieobecności o dni wolne, moduł Human Resources wykorzystuje informacje o świętach i dniach wolnych od pracy do określania liczby dni, o jaką należy skorygować pule urlopów dla pracowników zarejestrowanych w kalendarzu.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
