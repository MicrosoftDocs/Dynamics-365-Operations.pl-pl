---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W tym artykule opisano sposób definiowania parametrów zasobów ludzkich dla urlopów i nieobecności w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a39c74eef3865c03ccb9dd5aa2fece7f25e639a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891387"
---
# <a name="configure-leave-and-absence-parameters"></a>Konfigurowanie parametrów urlopów i nieobecności

>[!Important]
>Funkcjonalność opisana w tym artykule jest obecnie dostępna dla klientów samodzielnej wersji Dynamics 365 Human Resources. Część lub całość tej funkcjonalności będzie dostępna w ramach przyszłego wydania infrastruktury Finance po wydaniu wersji Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Przed skonfigurowaniem planów urlopów i nieobecności w Dynamics 365 Human Resources, warto zweryfikować ustawienia wszystkich powiązanych **Parametrów zasobów ludzkich**, w tym:

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

>[!IMPORTANT]
>Funkcja wyświetlania urlopów i nieobecności w różnych firmach jest obecnie dostępna w wersji zapoznawczej. Aby wyświetlić opcję dla urlopów i nieobecności, należy włączyć funkcję w środowisku **piaskownicy**. Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Wyświetlanie i zmiana Udostępnianych parametrów zasobów ludzkich

1. Na stronie **Zarządzanie personelem** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Udostępniane parametry zasobów ludzkich**.

3. Na karcie **Zaawansowany dostęp** wybierz **Tak** dla opcji **Włącz międzyfirmowe wyświetlanie urlopu**, aby można było wyświetlać urlopy w różnych firmach.

4. Wybierz opcję **Zapisz**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Zobacz i zmień parametry urlopu i nieobecności

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.

3. Na karcie **Ogólne** ustaw następujące parametry:
 
    - Określ **Jednostkę dla urlopu i nieobecności** na godziny lub dni. Jeśli wybrano dni, można wybrać opcję **Włącz definicję połowy dnia**, aby umożliwić pracownikom wybranie pierwszej lub drugiej połowy dnia w swoich żądaniach czasu wolnego. 

    - Wybierz **Data rozpoczęcia miesięcy pracy**, aby określić, kiedy mają obowiązywać stawki naliczania dla planów urlopów za pomocą miesięcy pracy.

    - Umożliwia wybranie opcji **Obliczanie salda** w celu wyświetlenia widoku sald na dzień dzisiejszy lub w okresie naliczania. Wybranie **Saldo na dzień dzisiejszy** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i wniosków na dzień dzisiejszy. Wybranie **Saldo na okres naliczania** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i żądań podczas okresu naliczania zdefiniowanego przez częstotliwość w planie urlopu. 

    - Umożliwia ustawienie **godziny rozpoczęcia** zadania wsadowego **przeniesienia na następny okres**.  
    
    - Wybierz **Tak** w polu **Umożliw pracownikom zakup urlopu** oraz **Umożliw pracownikom sprzedaż urlopu**. Jeśli wybierzesz opcję **Tak** dla tych opcji, możesz utworzyć zasady kupna i sprzedaży, a następnie umożliwić pracownikom przesyłanie próśb dot. kupna i sprzedaży urlopu.

## <a name="configure-calendar-parameters"></a>Konfigurowanie parametrów kalendarza

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.

3. Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.

4. Wybierz opcję **Zapisz**.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
