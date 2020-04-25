---
title: Konfigurowanie typów urlopów i nieobecności
description: Tu opisano konfigurowanie typów urlopów, jakie mogą brać pracownicy w module Dynamics 365 Human Resources.
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198057"
---
# <a name="configure-leave-and-absence-types"></a>Konfigurowanie typów urlopów i nieobecności

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

9. Wybierz opcję **Zapisz**.

## <a name="configure-leave-type-rules"></a>Konfiguruj reguły typu urlopu

1. Ustaw opcje zaokrąglania dla typu urlopu. Dostępne opcje to **Brak**, **W górę**, **W dół** i **Do najbliższej**. Można również określić dokładność zaokrąglania dla typu urlopu.

2. Ustaw dla typu urlopu wartość w polu **Korekta świąt**. Po wybraniu tej opcji moduł Human Resources będzie wykorzystywał liczbę dni świątecznych przypadających w dniach roboczych do określenia sposobu naliczania czasu wolnego dla typu urlopu. Jeśli na przykład Boże Narodzenie przypada w poniedziałek, moduł Human Resources odejmie jeden dzień od typu urlopu podczas przetwarzania naliczeń.

   Święta ustawia się w kalendarzu czasu pracy. Aby uzyskać więcej informacji, zobacz [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
   
## <a name="configure-preview-features"></a>Konfigurowanie funkcji w wersji zapoznawczej

Jeśli włączono obsługę funkcji w wersji zapoznawczej dla urlopów i nieobecności, należy skonfigurować również ich ustawienia.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Wybierz typ urlopu dla sald przeniesionych na następny okres do przeniesienia. Można również utworzyć nowy typ urlopu dla przeniesienia do na następny okres. 

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie planu urlopu i nieobecności](hr-leave-and-absence-plans.md)
- [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
