---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można definiować parametry urlopów i nieobecności.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712383"
---
# <a name="configure-leave-and-absence-parameters"></a>Konfigurowanie parametrów urlopów i nieobecności

Przed skonfigurowaniem urlopów i nieobecności w module Dynamics 365 Human Resources dobrze jest sprawdzić ustawienia wszystkich powiązanych parametrów tego modułu, w tym takich jak:

- Numeracja wniosków urlopowych
- Ustawienia rozporządzenia dotyczącego zwolnień chorobowych i rodzinnych (FMLA)
- Ustawienia obszaru Samoobsługa pracownika etatowego dla wniosków urlopowych
- Parametry urlopów i nieobecności

## <a name="view-and-change-human-resources-parameters"></a>Wyświetlanie i zmiana parametrów modułu Human Resources

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.

3. Na karcie **Numery kolejne** sprawdź wartość **Kod sekwencji numerów** dla wartości **Identyfikator wniosku urlopowego** i w razie potrzeby zmień. To ustawienie określa numerację używaną do automatycznego przypisywania identyfikatorów do wniosków urlopowych.

4. Na karcie **FMLA** sprawdź ustawienia dotyczące rozporządzenia FMLA i w razie potrzeby zmień.

5. Na karcie **Samoobsługa pracownika etatowego** wskaż, czy kierownicy mogą wprowadzać wnioski urlopowe w imieniu swoich pracowników.

7. Wybierz opcję **Zapisz**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Zobacz i zmień parametry urlopu i nieobecności

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.

3. Na karcie **Ogólne** ustaw następujące parametry:
 
    - Określ **Jednostkę dla urlopu i nieobecności** na godziny lub dni. Jeśli wybrano dni, można wybrać opcję **Włącz definicję połowy dnia**, aby umożliwić pracownikom wybranie pierwszej lub drugiej połowy dnia w swoich żądaniach czasu wolnego. 

    - Wybierz **Data rozpoczęcia miesięcy pracy**, aby określić, kiedy mają obowiązywać stawki naliczania dla planów urlopów za pomocą miesięcy pracy.

    - Umożliwia wybranie opcji **Obliczanie salda** w celu wyświetlenia widoku sald na dzień dzisiejszy lub w okresie naliczania. Wybranie **Saldo na dzień dzisiejszy** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i wniosków na dzień dzisiejszy. Wybranie **Saldo na okres naliczania** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i żądań podczas okresu naliczania zdefiniowanego przez częstotliwość w planie urlopu. 

    - Umożliwia ustawienie godziny rozpoczęcia zadania wsadowego przeniesienia na następny okres.  
    
    - Wybierz **Tak** w polu **Umożliw pracownikom zakup urlopu** oraz **Umożliw pracownikom sprzedaż urlopu**. Jeśli wybierzesz opcję **Tak** dla tych opcji, możesz utworzyć zasady kupna i sprzedaży, a następnie umożliwić pracownikom przesyłanie próśb dot. kupna i sprzedaży urlopu.

## <a name="configure-calendar-parameters"></a>Konfigurowanie parametrów kalendarza

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.

3. Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.

4. Wybierz opcję **Zapisz**.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
