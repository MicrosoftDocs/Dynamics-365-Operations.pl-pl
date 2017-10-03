--- 
title: "Tworzenie szablonów czasu pracy"
description: "Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ff1978f127a014e75619a4bbbb9b6ff3a3ad7c7a
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-working-time-templates"></a>Tworzenie szablonów czasu pracy

[!include[task guide banner](../../includes/task-guide-banner.md)]

Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach. W tej procedurze pokazano sposób definiowania szablonu czasu pracy za pomocą właściwości planowania czasu pracy w celu kategoryzowania zakresów czasu pracy. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.

1. Wybierz kolejno opcje Wszystkie obszary robocze > Zarządzanie cyklem życia zasobu.
2. Kliknij opcję Szablony czasu pracy.

## <a name="create-working-time-template"></a>Tworzenie szablonu czasu pracy
1. Kliknij przycisk Nowy.
2. W polu Szablon czasu pracy wpisz wartość.
3. W polu Nazwa wpisz wartość.
4. Rozwiń sekcję Poniedziałek.
5. Kliknij przycisk Dodaj.
6. W polu Od wprowadź godzinę.
    * Określ godzinę rozpoczynania pracy rano.  
7. W polu Do wprowadź godzinę.
    * Określ godzinę, kiedy pracownicy zaczynają przerwę na obiad.  
8. Kliknij przycisk Dodaj.
9. W polu Od wprowadź godzinę.
    * Określ godzinę, kiedy pracownicy wznawiają pracę po obiedzie.  
10. W polu Do wprowadź godzinę.
    * Określ godzinę zakończenia dnia pracy.  

## <a name="replicate-working-times-to-all-week-days"></a>Replikowanie czasów pracy do wszystkich dni tygodnia
1. Kliknij opcję Kopiuj dzień.
    * Skopiuj definicje czasu pracy z poniedziałku do wtorku.  
2. Kliknij przycisk OK.
3. Kliknij opcję Kopiuj dzień.
    * Skopiuj definicje czasu pracy z poniedziałku do środy.  
4. W polu Do dnia roboczego wybierz opcję.
5. Kliknij przycisk OK.
6. Kliknij opcję Kopiuj dzień.
    * Skopiuj definicje czasu pracy z poniedziałku do czwartku.  
7. W polu Do dnia roboczego wybierz opcję.
8. Kliknij przycisk OK.
9. Kliknij opcję Kopiuj dzień.
    * Skopiuj definicje czasu pracy z poniedziałku do piątku.  
10. W polu Do dnia roboczego wybierz opcję.
11. Kliknij przycisk OK.

## <a name="define-time-slots-for-special-operations"></a>Definiowanie przedziałów czasu dla operacji specjalnych
1. Rozwiń sekcję Piątek.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. W polu Właściwość wprowadź lub wybierz wartość.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. W polu Właściwość wprowadź lub wybierz wartość.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Oznaczanie dni weekendowych jako zamkniętych dla pobierania
1. Rozwiń sekcję Sobota.
2. W polu Zamknięte dla pobrania wybierz opcję Tak.
3. Rozwiń sekcję Niedziela.
4. W polu Zamknięte dla pobrania wybierz opcję Tak.


