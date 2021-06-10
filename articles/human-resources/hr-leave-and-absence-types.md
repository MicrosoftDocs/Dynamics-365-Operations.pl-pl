---
title: Konfigurowanie typów urlopów i nieobecności
description: Tu opisano konfigurowanie typów urlopów, jakie mogą brać pracownicy w module Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 098f614da80a1e7e3e31b30cea707ecfbd5b0a70
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056619"
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

2. Ustaw dla typu urlopu wartość w polu **Korekta świąt**. Po wybraniu tej opcji moduł Human Resources będzie wykorzystywał liczbę dni świątecznych przypadających w dniach roboczych do określenia sposobu naliczania czasu wolnego dla typu urlopu. Jeśli na przykład Boże Narodzenie przypada w poniedziałek, moduł Human Resources odejmie jeden dzień od typu urlopu podczas przetwarzania naliczeń.

   Święta ustawia się w kalendarzu czasu pracy. Aby uzyskać więcej informacji, zobacz [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
   
 3. Określ **Typ urlopu przeniesiony na późniejszy okres** na następny okres dla typu urlopu. Po wybraniu tej opcji wszelkie salda przeniesione zostaną przeniesione do określonego rodzaju urlopu. Typ urlopu do przodu musi być również uwzględniony w planie urlopu i nieobecności. 
 
 4. Określ **Reguły wygasania** dla typu urlopu. Po skonfigurowaniu tej opcji możesz wybrać jednostkę dni lub miesięcy i ustawić czas wygaśnięcia. Można również określić datę wejścia w życie reguły wygasania. Data wejścia w życie służy do określenia, kiedy należy rozpocząć uruchamianie zadania wsadowego przetwarzającego wygaśnięcie urlopu, a kiedy reguła zaczyna obowiązywać. Samo wygaśnięcie zawsze nastąpi w dniu rozpoczęcia planu urlopu, gdy zadanie wsadowe jest ustawione na przetwarzanie. Na przykład datą rozpoczęcia planu może być 01.01.2020, ale reguła została utworzona dopiero 01.06.2020. Ustawiając datę wejścia w życie na 01.06.2020, reguła będzie przetwarzana na granicy następnego roku, czyli 01.01.2021. Salda urlopu, które istnieją w momencie wygaśnięcia, zostaną odjęte od typu urlopu i zostaną odzwierciedlone w saldzie urlopu. 
 
## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie planu urlopu i nieobecności](hr-leave-and-absence-plans.md)
- [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
- [Wstrzymywanie urlopu](hr-leave-and-absence-suspend-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
