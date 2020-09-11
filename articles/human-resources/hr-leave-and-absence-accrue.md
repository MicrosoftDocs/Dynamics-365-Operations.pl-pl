---
title: Nalicz plany urlopów i nieobecności
description: W programie Dynamics 365 Human Resources urlopy i nieobecności można naliczać dla wielu pracowników lub dla jednej osoby.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 43c16c5d0de91bf1f433f4fde36e7d13775f44a0
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712178"
---
# <a name="accrue-leave-and-absence-plans"></a>Nalicz plany urlopów i nieobecności

W programie Dynamics 365 Human Resources urlopy i nieobecności można naliczać dla wielu pracowników lub dla jednej osoby.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Naliczanie urlopów i nieobecności dla wielu pracowników etatowych

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Zarządzaj urlopami** wybierz opcję **Nalicz do planów urlopów i nieobecności**.

3. Zostanie wyświetlone okno dialogowe **Naliczanie planów urlopu i nieobecności**. W polu **Naliczanie na dzień** wybierz **Datę dzisiejszą** lub wybierz **Datę niestandardową** i wprowadź datę niestandardową.

4. Aby uruchomić naliczenia dla wszystkich firm, należy wybrać opcję **Wszystkie firmy**. Jeśli chcesz przetwarzać naliczenia dla planu jednego urlopu, wybierz opcję **Nie** dla **Wszystkich planów**, a następnie wybierz **Plan urlopu**. W przypadku wybrania wszystkich firm nie można wybrać jednego planu urlopu. 

5. Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Wprowadź informacje o procesie naliczania.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Naliczanie urlopów i nieobecności dla pracownika etatowego

1. W rekordzie pracownika wybierz pozycję **Urlop**.

2. Wybierz opcję **Nalicz do planów urlopów i nieobecności**.

3. Zostanie wyświetlone okno dialogowe **Naliczanie planów urlopu i nieobecności**. W polu **Naliczanie na dzień** wybierz **Datę dzisiejszą** lub wybierz **Datę niestandardową** i wprowadź datę niestandardową.

4. Aby uruchomić naliczenia dla wszystkich firm, należy wybrać opcję **Wszystkie firmy**. Jeśli chcesz przetwarzać naliczenia dla planu jednego urlopu, wybierz opcję **Nie** dla **Wszystkich planów**, a następnie wybierz **Plan urlopu**. W przypadku wybrania wszystkich firm nie można wybrać jednego planu urlopu. 

5. Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Wprowadź informacje o procesie naliczania.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Usuwanie naliczeń urlopów i nieobecności dla wielu pracowników etatowych

Usuwanie rekordów naliczeń dla określonego planu i zakresu dat. Daty naliczania muszą przypadać w dniu dzisiejszym lub w przyszłości.

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Zarządzaj urlopami** wybierz opcję **Usuń naliczanie planów urlopów i nieobecności**.

3. W oknie dialogowym **Usuń naliczanie planów urlopów i nieobecności** wybierz **Plan urlopów**. 

4. W razie potrzeby wybierz polecenie **Usuń korekty salda**.

5. Wprowadź lub wybierz **Datę naliczania urlopu**. Ta data musi być datą dzisiejszą lub w przyszłości. 

6. Kliknij przycisk **OK**. Proces naliczania usunie naliczenia z parametrami określonymi przez Ciebie. 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Usuwanie naliczeń urlopów i nieobecności dla jednego pracownika etatowego

1. W rekordzie pracownika wybierz pozycję **Urlop**.

2. Wybierz **Usuń naliczenia planów urlopów i nieobecności**.

3. W oknie dialogowym **Usuń naliczanie planów urlopów i nieobecności** wybierz **Plan urlopów**. 

4. W razie potrzeby wybierz polecenie **Usuń korekty salda**.

5. Wprowadź lub wybierz **Datę naliczania urlopu**. Ta data musi być datą dzisiejszą lub w przyszłości. 

6. Kliknij przycisk **OK**. Proces naliczania usunie naliczenia z parametrami określonymi przez Ciebie. 

## <a name="review-leave-accrual-and-deletion-processes"></a>Przeglądanie procesów naliczania i usuwania urlopu

**Inspekcja naliczania urlopów** wyświetla się przy każdym uruchomieniu lub usunięciu naliczenia dla jednego lub wszystkich pracowników. Zostanie wyświetlona data i osoba, która wykonała akcję.

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Zarządzaj urlopami** wybierz opcję **Usuń inspekcję naliczania planów**.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)</br>
[Tworzenie planu urlopu i nieobecności](hr-leave-and-absence-plans.md)
