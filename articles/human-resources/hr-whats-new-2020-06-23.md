---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 czerwiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 23 czerwca 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 28eecb6289e5e895e860cffa29a55e773c6aadaa
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528724"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (23 czerwiec 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3347. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Po wygaśnięciu rejestracji pracownika, który zakończył pracę, typ urlopu, saldo i kwota są usuwane z formularza Rejestracja urlopu (444867)

Wartości **Typ urlopu**, **Saldo** i **Kwota** są obecnie utrzymywane, a nie wyczyszczone po dokonaniu wyboru.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Nieprawidłowe prognozowane saldo, gdy jest uruchamiana nowa funkcja (Naliczanie urlopów dla jednej firmy lub jednego planu) (456553)

Prawidłowe prognozowane saldo jest wyświetlane, gdy jest uruchamiana nowa funkcja Naliczanie urlopów dla jednej firmy lub jednego planu.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Jednostki z relacjami, które powodują powstanie zduplikowanych właściwości nawigacji (456486)

Ta wersja koryguje kwestię dotyczącą właściwości nawigacji (relacji) wielu jednostek. Wykryto zduplikowane relacje. Te scenariusze zostały poprawione.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Komentarze międzyfirmowe dotyczące przeglądu wydajności (455536)

Komentarze międzyfirmowe są teraz widoczne na monitorach wydajności za pomocą tej poprawki. Ta zmiana umożliwia skorygowanie komentarzy recenzentów wprowadzonych w różnych firmach w związku z tym samym przeglądem wydajności.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Niespójność w wyświetlaniu danych zarządzania wynagrodzeniem (432562)

Spójny widok danych dotyczących wynagrodzenia jest obecnie utrzymywany w usłudze samoobsługowej kierownika. Zależnie od sposobu przechodzenia do **Szczegółów dotyczących wynagrodzenia** pracownika, dane o wynagrodzeniach są teraz poprawnie wyświetlane kierownikom.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>Naprawiono błąd, w którym domyślna Data wprowadzenia w systemie stałych wynagrodzeń była równa dacie dzisiejszej (411994)

Data początkowa wynagrodzenia jest teraz określana na podstawie daty rozpoczęcia pracy na stanowisku przypisanym do pracownika.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>Formularz urlop i nieobecności – opcja Włączanie definicji połowy dnia jest wyłączona po otwarciu formularza (452607)

Ta zmiana powoduje, że **Włączanie definicji połowy dnia** będzie włączona do momentu, aż będą istnieć nowe transakcje urlopowe. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Nie można publikować w HcmDiscussionEntity za pośrednictwem programu Excel; Błąd pola TotalRatingScore (453899)

Teraz można zaktualizować pole **TotalRatingScore** za pomocą **HCMDiscussionEntity** w projektancie skoroszytów programu Excel.

## <a name="in-preview"></a>Wersja próbna

## <a name="database-logging"></a>Logowanie do bazy danych

Rejestrowanie bazy danych umożliwia określenie, która tabele i pola mają być monitorowane. Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian. Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).

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

Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności. Ta możliwość jest dostępna w procesie naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).

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

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurowanie nazwy Samoobsługi pracownika etatowego

Nowa opcja będzie dostępna w parametrach **modułu Human Resources** w celu zaktualizowania nazwy „Samoobsługowy obszar roboczy pracownika” na nazwę „Samoobsługa”.

## <a name="checklist-entities-included-in-common-data-service"></a>Jednostki listy kontrolnej uwzględnione w Common Data Service

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w systemie Common Data Service.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]