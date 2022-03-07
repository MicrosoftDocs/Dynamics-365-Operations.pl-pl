---
title: Konfigurowanie typów urlopów i nieobecności
description: Tu opisano konfigurowanie typów urlopów, jakie mogą brać pracownicy w module Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/09/2021
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
ms.openlocfilehash: b616d1f2c8b0bc8131045424b01dbfaa82f41f84
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485818"
---
# <a name="configure-leave-and-absence-types"></a>Konfigurowanie typów urlopów i nieobecności

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Typy urlopów w module Dynamics 365 Human Resources określają różne rodzaje nieobecności, które pracownicy mogą zgłaszać. Typy urlopów można dostosować zgodnie z potrzebami swojej organizacji. Przykłady typów urlopów:

- Płatny urlop (PTO)
- Urlop bezpłatny
- Urlop płatny
- Urlop zdrowotny
- Urlop zdrowotny
- Urlop rodziny
- Krótkoterminowa niepełnosprawność
- Urlop okolicznościowy

## <a name="add-a-leave-type"></a>Dodawanie typu urlopu

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Typy urlopów i nieobecności**.

3. Wybierz pozycję **Nowy**.

4. Nadaj nazwę typowi urlopu w polu **Typ**, wybierz przepływ pracy w polu **Identyfikator przepływu pracy** i wprowadź opis w polu **Opis**.

5. W obszarze **Ogólne** z listy rozwijanej **Kategoria** wybierz opcję **Brak**, **Zaplanowano** lub **Nie zaplanowano**.

6. Wybierz kod zarobków z listy rozwijanej **Kod zarobków**.

7. W obszarze **Wymagany kod przyczyny** określ, czy ma być wymagany kod przyczyny. Jeśli kody przyczyn mają być wymagane, może być konieczne ich dodanie. W obszarze **Kody przyczyn** kliknij przycisk **Dodaj**, wybierz kod przyczyny, a następnie obok niego zaznacz pole wyboru **Włączone**.

8. W obszarze **Ogranicz dostęp do wybranych ról** określ, czy chcesz ograniczyć dostęp. Następnie wybierz role zabezpieczeń w obszarze **Role zabezpieczeń dla tego typu urlopów**. Role zabezpieczeń definiuje się w przepływie pracy wybranym w ustawieniu **Identyfikator przepływu pracy** wcześniej w tej procedurze.

9. W obszarze **Kolor kalendarza** określ, jaki kolor ma być wyświetlany w kalendarzach urlopów i nieobecności dla tego typu urlopu. 

10. W obszarze **Relacje zawieszenia** określ, czy chcesz, aby ten typ urlopu miał zawieszać inny typ urlopu, czy był zawieszony przez inny typ urlopu. Gdy zostanie złożony wniosek o urlop dla typu urlopu zawieszonego, automatycznie zostanie utworzone zawieszenie urlopu dla typu urlopu zawieszonego. 

10. Wybierz opcję **Zapisz**.

## <a name="configure-leave-type-rules"></a>Konfiguruj reguły typu urlopu

1. Ustaw opcje zaokrąglania dla typu urlopu. Dostępne opcje to **Brak**, **W górę**, **W dół** i **Do najbliższej**. Można również określić dokładność zaokrąglania dla typu urlopu.

2. Ustaw dla typu urlopu wartość w polu **Korekta świąt**. Po wybraniu tej opcji liczba dni świątecznych przypadających na dzień roboczy zostanie użyta do określenia sposobu naliczania czasu wolnego dla typu urlopu. Jeśli na przykład Boże Narodzenie przypada w poniedziałek, moduł Human Resources odejmie jeden dzień od typu urlopu podczas przetwarzania naliczeń.

   Święta ustawia się w kalendarzu czasu pracy. Aby uzyskać więcej informacji, zobacz [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md).
   
 3. Określ **Typ urlopu przeniesiony na późniejszy okres** na następny okres dla typu urlopu. Po wybraniu tej opcji wszelkie salda przeniesione zostaną przeniesione do określonego rodzaju urlopu. Typ urlopu do przodu musi być również uwzględniony w planie urlopu i nieobecności. 
 
4. Określ **Reguły wygasania** dla typu urlopu. Po skonfigurowaniu tej opcji możesz wybrać jednostkę dni lub miesięcy i ustawić czas wygaśnięcia. Data efektywnego wygaśnięcia służy do określenia, kiedy należy rozpocząć uruchamianie zadania wsadowego przetwarzającego wygaśnięcie urlopu, a kiedy reguła zaczyna obowiązywać. Data wygaśnięcia będzie zawsze przypadać w dniu rozpoczęcia okresu naliczania. Na przykład, jeżeli data rozpoczęcia okresu naliczania to 3 sierpnia 2021 r., a reguła wygasania została ustawiona na 6 miesięcy, reguła zostanie przetworzona w oparciu o przesunięcie terminu wygaśnięcia z daty rozpoczęcia okresu naliczania, a więc zostanie wykonana 3 lutego 2022 r. Salda urlopu, które istnieją w momencie wygaśnięcia, zostaną odjęte od typu urlopu i zostaną odzwierciedlone w saldzie urlopu.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Konfigurowanie wymaganego załącznika dla typu urlopu

> [!NOTE]
> Aby użyć pola **Wymagany załącznik**, należy najpierw włączyć funkcję **Konfigurowanie wymaganego załącznika** dla wniosków urlopowych w zarządzaniu funkcjami. Aby uzyskać informacje na temat włączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

1. Na stronie **Urlop i nieobecność**, na karcie **Łącza** w obszarze **Ustawienia** wybierz opcję **Typy urlopów i nieobecności**.

2. Wybierz typ urlopu i nieobecności z listy. Następnie w sekcji **Ogólne** użyj pola **Wymagany załącznik**, aby określić, czy załącznik musi być przesłany, gdy pracownik składa nowy wniosek urlopowy dla wybranego typu urlopu. 

Pracownicy będą mieli obowiązek przekazywania załącznika podczas przesyłania nowego wniosku urlopowego o typie urlopu, w którym jest włączone pole **Wymagany załącznik**. Aby wyświetlić załącznik przekazany jako część wniosku urlopowego, osoby zatwierdzające wnioski urlopowe mogą użyć opcji **Załączniki** dla elementów pracy, które są do nich przypisane. Jeśli dostęp do wniosku urlopowego jest uzyskiwany za pomocą aplikacji Human Resources w Microsoft Teams, opcja **Wyświetl szczegóły** wniosku urlopowego może służyć do przeglądania jego szczegółów i wszelkich załączników.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Skonfiguruj jednostki urlopu (godziny/dni) według typu urlopu

> [!NOTE]
> Aby korzystać z funkcji jednostek urlopu na typ urlopu, należy najpierw włączyć funkcję **Konfiguruj jednostki urlopu na typ urlopu** w Zarządzaniu funkcjami. Aby uzyskać informacje na temat włączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

> [!IMPORTANT]
> Domyślnie typy urlopów w firmie używają jednostek urlopów z konfiguracji parametrów urlopów na poziomie firmy.
> 
> Jednostka urlopu typu urlop i nieobecność może być modyfikowana tylko wtedy, gdy nie ma transakcji urlopowych dla tego typu urlopu.
> 
> Tej funkcji nie można wyłączyć po jej włączeniu.

1. Na stronie **Urlop i nieobecność**, na karcie **Łącza** w obszarze **Ustawienia** wybierz opcję **Typy urlopów i nieobecności**.

2. Wybierz typ urlopu i nieobecności z listy. Następnie w sekcji **Ogólne** w polu **Jednostka** wybierz jednostkę urlopu. Można wybrać opcję **Godziny** lub **Dni**.

3. Opcjonalnie: jeśli wybrano opcję **Godziny** w polu **Jednostka**, można użyć pola **Włącz pół dnia definicji**, aby określić, czy pracownicy mogą wybrać pierwszą półrocze, czy drugą pół dnia wolnego, jeśli wnioskują o pół dnia urlopu.

Pracownicy, którzy składają nowy wniosek urlopowy, mogą wybrać różne rodzaje urlopu, aby skonstruować swój wniosek urlopowy. Jednak wszystkie typy urlopów wybrane w ramach jednego wniosku urlopowego powinny mieć tę samą jednostkę urlopową. Pracownicy mogą wyświetlić jednostki urlopu dla każdego typu urlopu w formularzu **Żądanie urlopu**.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie planu urlopu i nieobecności](hr-leave-and-absence-plans.md)
- [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
- [Wstrzymaj urlop](hr-leave-and-absence-suspend-leave.md)
- [Tworzenie przepływu pracy zakupu i sprzedawania urlopów](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
