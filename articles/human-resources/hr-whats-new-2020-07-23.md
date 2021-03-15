---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 lipiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 23 lipca 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 07/23/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5e10d6d1dedfc251a1a00110b50c9096314d75b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127528"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 lipiec 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3416. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>Usunięcie wymiarów finansowych na stanowisku nie działa zgodnie z oczekiwaniami (445476)

Usunięcie wymiarów z stanowiska powoduje obecnie usunięcie tych samych stanowisk z Dataverse.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Pozycje poza hierarchią pokazują nieaktywne pozycje (397257)

Stanowiska, które są nieaktywne (mają wygasły czas trwania), nie są już wyświetlane w hierarchii stanowisk jako **Pozycje poza hierarchią**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>Walidacja zachodząca między LeaveEnrollmentEntity i HcmWorkerEntity na imporcie Data Management Framework (DMF) powoduje powolne ładowanie danych (442324)

Zmiany w tej wersji zwiększają wydajność **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Nie można spersonalizować w administrowaniu organizacją (447490)

Dzięki tej zmianie można teraz personalizować łącza w **Administrowanie organizacją**.

## <a name="in-preview"></a>Wersja próbna

## <a name="mandatory-fields"></a>Pola obowiązkowe 

Można teraz wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich. Ta funkcja wymaga **Zapisanych widoków**.

## <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami
 
Jednostki zarządzania świadczeniami są zwalniane. Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami. Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych. Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.

## <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop 

Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy. Ten proces jest często zarządzany ręcznie. Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr. Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy. Aby uzyskać więcej informacji, zobacz:

- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Pozostaw naliczenie dla jednej firmy lub pojedynczego planu

Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności. Ta możliwość jest dostępna dla procesu naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopów. Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).

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

## <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

## <a name="platform-changes"></a>Zmiany w platformie

Aktualizacja Platform Update 10.0.12 (36)

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]