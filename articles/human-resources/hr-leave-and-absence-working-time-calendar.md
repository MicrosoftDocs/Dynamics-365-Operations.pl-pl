---
title: Tworzenie kalendarza czasu pracy
description: Tu opisano definiowanie kalendarza czasu pracy, świąt i czasu wolnego od pracy w module Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dc209b62836011b18362f78b63cdd3fcda884dc3
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198034"
---
# <a name="create-a-working-time-calendar"></a>Tworzenie kalendarza czasu pracy

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

1. Na stronie **Administrowanie organizacją** wybierz opcję **Czas wolny od pracy**.

2. Kliknij opcję **Nowy**, a następnie wprowadź nazwę i przedział czasu dla czasu wolnego od pracy.

Jeśli włączono funkcję w wersji zapoznawczej o nazwie Korekty urlopów i nieobecności o dni wolne, moduł Human Resources wykorzystuje informacje o świętach i dniach wolnych od pracy do określania liczby dni, o jaką należy skorygować pule urlopów dla pracowników zarejestrowanych w kalendarzu.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)
