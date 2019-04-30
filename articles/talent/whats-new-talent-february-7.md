---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (7 lutego 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "858935"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (7 lutego 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="interview-scheduling-enhancements"></a>Rozszerzenia do Planowania rozmów kwalifikacyjnych
Wprowadzono udoskonalenia całego procesu planowania rozmowy kwalifikacyjnej. Teraz można wyświetlić informacje o dostępności w kalendarzu kandydata wewnętrznego i użyć kalendarza wewnętrznego kandydata, aby zaproponować harmonogram. Aby uzyskać więcej informacji, zobacz [Planowanie rozmów kwalifikacyjnych i informacji zwrotnych](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Publikowanie ofert pracy na LinkedIn — naprawiony problem niezgodności firmy
Został rozwiązany problem polegający na tym, że oferty pracy na LinkedIn wysyłane z Attract były publikowane z nieprawidłową nazwą firmy. Aby uzyskać więcej informacji, zobacz [tworzenie, zatwierdzanie i publikowanie ofert pracy w Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>Adres URL witryny kariery zawodowej wyświetlany w ustawieniach administratora
Adres URL strony głównej kariery jest teraz wyświetlany w **ustawieniach administratora** w obszarze **Zarządzanie witryną kariery zawodowej**.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

**Kompilacja 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Obsługa wielu poziomów wynagrodzeń na stanowisku
Ta zmiana zezwala na zdefiniowanie dla stanowiska więcej niż jednego poziomu wynagrodzenia, co pozwala stosować zakresy stałych wynagrodzeń pracownika, które mogą się różnić między planami na tym samym stanowisku. 

Na przykład:    
*Stanowisko* - Kierownik ds. klienta *Skojarzone poziomy wynagrodzenia:* B1 i B2 - każdy poziom ma określony zakres wartości. B1 = minimum 50 000, środkowy 60 000, Maks 75 000 i B2 = Min 65 000, środkowy 74 000, maksymalna liczba 85 000. Podczas tworzenia stałych wynagrodzeń dla pracowników, zgodnie ze zdefiniowanymi regułami uprawnienia, każdy plan stałych wynagrodzeń może wskazywać to samo stanowisko i różne poziomy stanowiska. Pozwala to na różnicowanie planów dla różnych regionów/firm na tym samym stanowisku z różnymi zakresami płac, ale bez konieczności duplikowania stanowisk, tak aby odzwierciedlały te różnice.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>Pole poziom wynagrodzeń zostało dodane wpisu stałego wynagrodzenia pracownika 
Dzięki tej aktualizacji wpis stałego wynagrodzenia pracownika zawiera teraz pole **poziomu wynagrodzenia**. Ten dodatek pozwala łatwiej aktualizować plany stałych wynagrodzeń pracowników. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Aktualizowanie rodziny stanowisk przy aktualizowaniu i tworzeniu nowych stanowisk
Podczas zmieniania zadania na stanowisku **rodzina zadań** będzie teraz domyślna na podstawie wybranego zadania.

### <a name="performance-improvements-when-rendering-workspaces"></a>Poprawa wydajności podczas renderowania obszarów roboczych
Karty analityczne w obszarze roboczym będą teraz wczytywane tylko w przypadku otwierania tych stron. Podczas początkowego renderowania strony w lewym górnym rogu będzie widoczny wskaźnik.
