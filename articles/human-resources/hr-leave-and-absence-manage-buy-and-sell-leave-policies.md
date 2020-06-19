---
title: Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu
description: Można umożliwić pracownikom kupowanie i sprzedawanie urlopu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429020"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu

[!include [banner](includes/preview-feature.md)]

Można umożliwić pracownikom kupowanie urlopu, tworząc zasadę kupowania urlopu.  

## <a name="enable-employees-to-buy-and-sell-leave"></a>Umożliwienie pracownikom kupowania i sprzedawania urlopu

1. Na stronie **Parametry urlopów i nieobecności** wybierz opcję **Tak** dla **Pozwól pracownikom kupić urlop**. 

## <a name="create-a-buy-leave-policy"></a>Tworzenie zasady kupowania urlopu

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**. 

2. Wybierz **Zasady kupowania i sprzzedawania urlopu**.

3. Wybierz pozycję **Nowy**.

4. Wprowadź **Nazwę** i **Opis** zasady w obszarze **Zasady kupowania i sprzedawania urlopu**. 

5. Wybierz **Typ zasad**. 

   Dostępne typy zasad to **Ilość** i **Godziny na tydzień**. Wybierz opcję **Ilość**, aby wprowadzić **Stałą ilość** dla maksymalnych ilości, które pracownicy mogą kupować i sprzedawać. W przypadku wybrania **Godziny w tygodniu** czas pracy określony w kalendarzu czasu pracy pracownika jest używany do określenia maksymalnej ilości zasady. 

6. Wybierz **Datę początkową** i **Datę końcową** dla zasady. Żądania kupna lub sprzedaży urlopu będą dostępne tylko do przesyłania w tym przedziale czasowym. 

7. W obszarze **Kup zasadę** wybierz opcję **Odpowiednik pełnego etatu**, aby ustalić maksymalną kwotę na podstawie pełnego etatu zdefiniowanego dla stanowiska pracownika. Jeśli typem zasady jest **Ilość**, wprowadź **Maksymalną stałą ilość**. 

8. Wybierz przycisk **Dodaj**, aby dodać typy urlopów dla pracowników, którzy będą kupować urlop. Do zasady można dodać wiele typów urlopów. 

9. Wprowadź **Miesiące usługi** dla typu urlop, aby umożliwić różnym miesiącom usługi określenie maksymalnej kwoty, jaką może zakupić pracownik. 

10. Wprowadź **Maksymalną ilość** dla typu urlopu. 

11. Umożliwia wprowadzenie **Stawki**, za którą pracownik będzie kupować urlop. 

12. Opcjonalnie można wprowadzić **Kod zarobków**, który ma być używany przy zakupie urlopu. 

13. Opcjonalnie określ, czy ma być używany ekwiwalent pełnego wymiaru czasu, aby określić maksymalną ilość dla typu urlopu. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Dodaj zasadę Kup i Sprzedaj urlop do planu urlopu i nieobecności

1. Na stronie **Urlopy i nieobecności** wybierz plan urlopu i nieobecności.

2. W **Reguły** wybierz **Zasady kupowania i sprzzedawania urlopu**.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)</br>
[Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)</br>
[Naliczanie planów urlopów i nieobecności](hr-leave-and-absence-accrue.md)</br>
[Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

