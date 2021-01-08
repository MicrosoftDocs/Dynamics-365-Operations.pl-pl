---
title: Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu
description: Można umożliwić pracownikom kupowanie i sprzedawanie urlopu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55d29c42cc1b2d69517e2fcd458ee6a1bdf5277f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420121"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Zarządzaj zasadami Kupowania i Sprzedawania urlopu

Można umożliwić pracownikom kupowanie i sprzedawanie urlopu, tworząc zasadę kupowania i sprzedawania urlopu. Te zasady można skonfigurować do używania przepływu pracy dla zatwierdzeń, określania maksymalnych kwot i stawek oraz ustalania stawek kupowania i sprzedawania. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Umożliwienie pracownikom kupowania i sprzedawania urlopu

1. Na stronie **Parametry urlopów i nieobecności** wybierz opcję **Tak** dla **Pozwól pracownikom kupić urlop** oraz **Pozwól pracownikom sprzedać urlop**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Tworzenie zasad dot. zakupów i sprzedaży urlopów

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**. 

2. Wybierz **Zasady kupowania i sprzzedawania urlopu**.

3. Wybierz pozycję **Nowy**.

4. Wprowadź **Nazwę** i **Opis** zasady w obszarze **Zasady kupowania i sprzedawania urlopu**. 

5. Wybierz **Typ zasad**. 

   Dostępne typy zasad to **Ilość** i **Godziny na tydzień**. Wybierz opcję **Ilość**, aby wprowadzić **Stałą ilość** dla maksymalnych ilości, które pracownicy mogą kupować i sprzedawać. W przypadku wybrania **Godziny w tygodniu** czas pracy określony w kalendarzu czasu pracy pracownika jest używany do określenia maksymalnej ilości zasady. 

6. Wybierz **Datę początkową** i **Datę końcową** dla zasady. Żądania kupna lub sprzedaży urlopu będą dostępne tylko do przesyłania w tym przedziale czasowym. 

7. Wybierz **Identyfikator przepływu pracy** dla zasady. Wszystkie żądania zakupu i sprzedaży używają tego przepływu pracy do przeglądu i zatwierdzenia. 

8. W obszarze **Kup zasadę** wybierz opcję **Odpowiednik pełnego etatu**, aby ustalić maksymalną kwotę na podstawie pełnego etatu zdefiniowanego dla stanowiska pracownika. Jeśli typem zasady jest **Ilość**, wprowadź **Maksymalną stałą ilość**. 

9. Wybierz przycisk **Dodaj**, aby dodać typy urlopów dla pracowników, którzy będą kupować urlop. Do zasady można dodać wiele typów urlopów. 

10. Wprowadź **Miesiące usługi** dla typu urlop, aby umożliwić różnym miesiącom usługi określenie maksymalnej kwoty, jaką może zakupić pracownik. 

11. Wprowadź **Maksymalną ilość** dla typu urlopu. 

12. Umożliwia wprowadzenie **Stawki**, za którą pracownik będzie kupować urlop. 

13. Opcjonalnie można wprowadzić **Kod zarobków**, który ma być używany przy zakupie urlopu. 

14. Opcjonalnie określ, czy ma być używany ekwiwalent pełnego wymiaru czasu, aby określić maksymalną ilość dla typu urlopu. 

15. Aby utworzyć zasadę sprzedaży, wykonaj czynności opisane w punktach 8 – 14 w ramach **Zasad sprzedaży**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Dodaj zasadę Kup i Sprzedaj urlop do planu urlopu i nieobecności

1. Na stronie **Urlopy i nieobecności** wybierz plan urlopu i nieobecności.

2. W **Reguły** wybierz **Zasady kupowania i sprzzedawania urlopu**.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)</br>
[Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)</br>
[Naliczanie planów urlopów i nieobecności](hr-leave-and-absence-accrue.md)</br>
[Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

