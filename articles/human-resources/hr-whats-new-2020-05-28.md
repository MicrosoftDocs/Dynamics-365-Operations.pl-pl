---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (28 maja 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 28 maja 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8e8d7f87f30286eefa1b3b53925702f4735132e6
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465277"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (28 maja 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3287. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>Jednostka LeaveRequest nie działa w przypadku włączenia wielu typów dla każdego planu urlopu (447498)

Po wprowadzeniu tej zmiany **LeaveEnrollmentV2Entity** jest teraz dostępny, aby poprawić błąd występujący po włączeniu wielu typów urlopów.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Funkcja redukcji rywalizacji partii (wersja zapoznawcza) (446619)

Po włączeniu tej funkcji można oczekiwać zmniejszenia blokowania w tabelach struktury przetwarzania wsadowego podczas wybierania zadań i kończenia zadań.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict podczas zapisywania pracownika uniemożliwia edytowanie rekordu w osobach (427915)

Ta zmiana poprawia błąd podczas dodawania nowego pracownika, aktualizowania informacji adresowych i zmiany preferencji językowych. W tym unikatowym scenariuszu wyświetlany jest błąd wskazujący, że nie można zaktualizować rekordu. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Nie można dodać załącznika do zatwierdzonego wniosku o urlop, aby ponownie go złożyć (425407)

Ta zmiana umożliwia teraz załączniki do zatwierdzonych wniosków o urlop.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>Użytkownik może wprowadzić wynagrodzenie dla pracownika w formularzu innej firmy (409529)

Ta zmiana wyłącza opcje kompensacji zapobiegające przypadkowemu wprowadzeniu rekordów wynagrodzenia dla niewłaściwej firmy.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Błąd podczas przenoszenia pracownika, a data przypisania stanowiska pracownika jest wcześniejsza niż czas trwania stanowiska (429402)

Komunikaty o błędach podczas przenoszenia pracownika w tym scenariuszu zostały zaktualizowane w celu lepszego opisywania niezbędnych zmian w celu rozwiązania problemu.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Możliwości załączników w rejestracji świadczeń samoobsługowych dla pracowników
 
Teraz możesz dodawać załączniki podczas procesu rejestracji świadczeń dla każdego planu, w którym pracownik się rejestruje. Następnie można wyświetlić te załączniki w formularzu **Zarejestrowane świadczenia pracownika**.

## <a name="in-preview"></a>Wersja próbna

## <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="leave-suspension"></a>Zawieszenie urlopu

Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego. Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów. Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika. Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Zaktualizowano środowisko użytkownika, aby umożliwić wskazanie, że naliczanie zostało zawieszone (429550)

Środowisko użytkownika wskazuje teraz, że naliczanie dla planu zostało zawieszone.

## <a name="coming-soon"></a>Wkrótce

## <a name="database-logging-in-preview-in-june"></a>Rejestrowanie w bazie danych (w wersji zapoznawczej w czerwcu)

Funkcja rejestrowania bazy danych umożliwia określenie, która tabela i które pola mają być monitorowane. Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian. Dostępne są możliwości zapytania, aby zmiany były widoczne w czasie.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Kupuj i sprzedawaj urlop (w wersji zapoznawczej 1 czerwca)

Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy. Ten proces jest często zarządzany ręcznie. Ta funkcja zapewnia bardziej zautomatyzowany sposób zarządzania zasadami i wnioskami dotyczącymi działu kadr, a także eliminuje pomyłki przy jednoczesnym usprawnieniu procesu zarządzania urlopami. Aby uzyskać więcej informacji, zobacz:

- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami
 
Jednostki zarządzania świadczeniami są zwalniane. Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami. Dostępny jest również szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych. Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Dodano kod przyczyny do wstrzymań naliczania (1 czerwca)

Kody przyczyn zostały dodane do wstrzymania naliczania.

## <a name="carry-forward-rules-june-1"></a>Zasady przenoszenia na następny okres (1 czerwca)

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Wstrzymanie naliczania urlopu dla określonych typów urlopów (1 czerwca)

W tym wydaniu dział zasobów ludzkich może utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny. Urlop bezpłatny może być typem, ale nie musi. Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>Jednostka DMF dostępna dla wstrzymań naliczania (1 czerwca)

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]