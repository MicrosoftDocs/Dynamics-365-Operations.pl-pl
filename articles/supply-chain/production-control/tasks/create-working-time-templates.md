---
title: Tworzenie szablonów czasu pracy
description: Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ef913777c8e2aa14af21e28ed56362e31b3d70a1a52e988a90ad94f59b77b70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741268"
---
# <a name="create-working-time-templates"></a>Tworzenie szablonów czasu pracy

[!include [banner](../../includes/banner.md)]

Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach. W tej procedurze pokazano sposób definiowania szablonu czasu pracy za pomocą właściwości planowania czasu pracy w celu kategoryzowania zakresów czasu pracy. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.

1. Wybierz kolejno opcje **Obszary robocze > Zarządzanie cyklem życia zasobu**.
1. Wybierz opcję **Szablony czasu pracy**.

## <a name="create-working-time-template"></a>Tworzenie szablonu czasu pracy

1. Wybierz pozycję **Nowy**.
1. W polu **Szablon czasu pracy** wpisz wartość.
1. W polu **Nazwa** wpisz wartość.
1. Rozwiń sekcję **Poniedziałek**.
1. Wybierz opcję **Dodaj**.
1. W polu **Od** wprowadź godzinę.
    * Określ godzinę rozpoczynania pracy rano.  
1. W polu **Do** wprowadź godzinę.
    * Określ godzinę, kiedy pracownicy zaczynają przerwę na obiad.  
1. Wybierz opcję **Dodaj**.
1. W polu **Od** wprowadź godzinę.
    * Określ godzinę, kiedy pracownicy wznawiają pracę po obiedzie.  
1. W polu **Do** wprowadź godzinę.
    * Określ godzinę zakończenia dnia pracy.  

## <a name="replicate-working-times-to-all-week-days"></a>Replikowanie czasów pracy do wszystkich dni tygodnia

1. Wybierz opcję **Kopiuj dzień**.
    * Skopiuj definicje czasu pracy z poniedziałku do wtorku.  
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Kopiuj dzień**.
    * Skopiuj definicje czasu pracy z poniedziałku do środy.  
1. W polu **Do dnia roboczego** wybierz opcję.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Kopiuj dzień**.
    * Skopiuj definicje czasu pracy z poniedziałku do czwartku.  
1. W polu **Do dnia roboczego** wybierz opcję.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Kopiuj dzień**.
    * Skopiuj definicje czasu pracy z poniedziałku do piątku.  
1. W polu **Do dnia roboczego** wybierz opcję.
1. Kliknij przycisk **OK**.

## <a name="define-time-slots-for-special-operations"></a>Definiowanie przedziałów czasu dla operacji specjalnych

1. Rozwiń sekcję **Piątek**.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. W polu **Właściwość** wprowadź lub wybierz wartość.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. W polu **Właściwość** wprowadź lub wybierz wartość.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Oznaczanie dni weekendowych jako zamkniętych dla pobierania

1. Rozwiń sekcję **Sobota**.
1. W polu **Zamknięte dla pobrania** wybierz opcję *Tak*.
1. Rozwiń sekcję **Niedziela**.
1. W polu **Zamknięte dla pobrania** wybierz opcję *Tak*.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]