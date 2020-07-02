---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (11 czerwiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39f18dc92fb01f9a0437f4166c0f08f8d6b1b81b
ms.sourcegitcommit: 218e22014a964b8b52fc0152e355b07b0b84ae2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/16/2020
ms.locfileid: "3456627"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (11 czerwiec 2020)

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3316. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>Uproszczony formularz pracownika czasami powoduje, że przyciski zamykania (X) formularza podrzędnego (442369) powodują zatrzymanie pracy

Po włączeniu nowego formularza **Pracownik** przycisk Zamknij (**X**) czasami nie działał w formularzach podrzędnych. Ten problem był sporadyczny. Można zamknąć formularz po opuszczeniu i przyjściu z powrotem do niego. Można na przykład zaznaczyć element menu po lewej stronie i przejść z powrotem do formularza **Pracownik** i zamknąć go. Wydanie tego tygodnia rozwiązuje ten problem. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>Osobista osoba kontaktowa pracownika nie eksportuje kontaktów osobistych z nadrzędnym typem relacji

W tym wydaniu encja **Osoby kontaktowej dla pracownika** eksportuje wszystkie typy relacji.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity powinna być domyślnie częścią pakietu integracji Ceridian (448506)

Przy tej zmianie **HcmPositionWorkerAssignmentV2Entity** jest uwzględniony w pakiecie integracji Ceridian.

## <a name="in-preview"></a>Wersja próbna

## <a name="database-logging"></a>Logowanie do bazy danych

Funkcja rejestrowania bazy danych umożliwia określenie, która tabele i pola mają być monitorowane. Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian. Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).

## <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami
 
Jednostki zarządzania świadczeniami są zwalniane. Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami. Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych. Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.

## <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop 

Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy. Ten proces jest często zarządzany ręcznie. Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr. Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy. Aby uzyskać więcej informacji, zobacz:

- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Pozostaw naliczenie dla jednej firmy lub pojedynczego planu

Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności. Ta możliwość jest dostępna w procesie naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).

## <a name="add-attachments-to-time-off-requests"></a>Dodawanie załączników do żądań czasu wolnego

Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19. Pracownicy mogą teraz dodawać te załączniki. Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów. Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Dodano kod przyczyny do wstrzymań naliczania 

Kody przyczyn zostały dodane do wstrzymania naliczania.

## <a name="carry-forward-rules"></a>Zasady przenoszenia na następny okres 

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Wstrzymanie naliczania urlopu dla określonych typów urlopów

Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny. Urlop bezpłatny może być typem, ale nie musi. Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Jednostka DMF dostępna dla wstrzymań naliczania 

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="coming-soon"></a>Wkrótce

## <a name="new-platform-capabilities"></a>Nowe możliwości platformy 

Pola można uczynić obowiązkowymi za pomocą personalizacji. Ta funkcja będzie wymagała włączania **Zapisanych widoków**.

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurowanie nazwy Samoobsługi pracownika etatowego

Nowa opcja będzie dostępna w parametrach modułu Human Resources w celu zaktualizowania nazwy Samoobsługowego obszaru roboczego pracownika do Samoobsługi. 
