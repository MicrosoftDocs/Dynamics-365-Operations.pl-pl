---
title: Naliczanie do planów urlopów i nieobecności
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 28b7d843d9dd652e45c24af09d0414530c06c4ac
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010187"
---
# <a name="accrue-leave-and-absence-plans"></a>Naliczanie do planów urlopów i nieobecności

W programie Dynamics 365 Human Resources urlopy i nieobecności można naliczać dla wielu pracowników lub dla jednej osoby.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Naliczanie urlopów i nieobecności dla wielu pracowników etatowych

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Zarządzaj urlopami** wybierz opcję **Nalicz do planów urlopów i nieobecności**.

3. W oknie dialogowym **Naliczanie do planów urlopów i nieobecności** w obszarze **Nalicz na dzień** wybierz opcję **Data dzisiejsza** lub opcję **Data niestandardowa** i wprowadź niestandardową datę.

4. Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Wprowadź informacje o procesie naliczania.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Naliczanie urlopów i nieobecności dla pracownika etatowego

1. W rekordzie pracownika wybierz pozycję **Urlop**.

2. Wybierz opcję **Nalicz do planów urlopów i nieobecności**.

3. W oknie dialogowym **Naliczanie do planów urlopów i nieobecności** w obszarze **Nalicz na dzień** wybierz opcję **Data dzisiejsza** lub opcję **Data niestandardowa** i wprowadź niestandardową datę.

4. Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Wprowadź informacje o procesie naliczania.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.

## <a name="preview-features-for-leave-and-absence"></a>Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności

[!include [banner](includes/preview-feature-leave-absence.md)]

Dla urlopów i nieobecności można włączyć następujące funkcje w wersji zapoznawczej:

- **Usuń naliczenia urlopów i nieobecności**. Usuwanie rekordów naliczeń dla określonego planu i zakresu dat. Daty naliczania muszą przypadać w dniu dzisiejszym lub w przyszłości.

- **Inspekcja naliczania urlopów**. Wyświetlanie każdego zdarzenia, gdy ktoś wykona lub usunie naliczenie dla jednego lub wszystkich pracowników, łącznie z datą i osobami, które wykonały akcję.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie planu urlopów i nieobecności](hr-leave-and-absence-plans.md)