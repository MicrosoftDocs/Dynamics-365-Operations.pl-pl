---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (16 lipiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
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
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6dce39bc529bf6dd6079ed900af12510c0773f9a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899089"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (16 lipiec 2019)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Common Data Service jednostki obecnie wspierające pola niestandardowe

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OmDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Nie można zobaczyć celów i przeglądów w module samoobsługi przez kierowników

Obecnie zmiany w tym tygodniu umożliwiają wyświetlanie i edytowanie celów i przeglądów dla menedżerów poziomu pomijania w module samoobsługi przez kierowników

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>Nie można zamknąć formularza celu, gdy użytkownik edytuje dowolne pole celu

Ta wersja koryguje ten błąd, gdy formularz cel nie jest zamykany po wybraniu przycisku **Zamknij**.

### <a name="creating-new-goals-and-saving-displays-error"></a>Tworzenie nowych celów i zapisywanie powoduje wyświetlenie błędu

Ta wersja koryguje ten błąd podczas zapisywania celów w module samoobsługi pracowników i kierowników

### <a name="unable-to-add-a-field-to-position-details"></a>Nie można dodać pola do szczegółów stanowiska 

W tej wersji pola niestandardowe są teraz obsługiwane w szczegółach stanowiska.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Nie można ustawić daty ważności dla kodu zarobków w module zarządzanie danymi

Zmiany umożliwiają określenie dat wygaśnięcia w kodach zarobków w zarządzaniu danymi.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Nowe pola niestandardowe nie synchronizują wystarczająco szybko

Wydajność synchronizacji pola niestandardowego na Common Data Service wlepszono z wersją wydaną w tym tygodniu.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>Eksportowanie jednostek do zadań bazy danych nie powiodło się. komunikat o błędzie: „format ciągu inicjującego nie odpowiada specyfikacji rozpoczynającej się od indeksu 0.”

Ta wersja koryguje błąd, w którym zadania wsadowe bazy danych kończą się niepowodzeniem. Aby aktualizować manualnie:

1. Otwórz **Zarządzanie danymi**.
2. Wybierz **Konfiguruj eksport jednostek do bazy danych**.
3. Wprowadź ponownie ciąg połączenia do docelowej bazy danych i wybierz opcję **Zapisz**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>Konfiguracja poczty e-mail SMTP nagle nie powiodła się, komunikat o błędzie: „serwer SMTP wymaga bezpiecznego połączenia lub klient nie został uwierzytelniony”.

Ta wersja poprawia konfigurację wiadomości e-mail SMTP, która nagle nie powiedzie się. Aby aktualizować manualnie:

1. Otwórz **Administrowanie systemem**.
2. Wybierz **Parametry poczty e-mail**.
3. Wubierz **Ustawienia SMTP**. 
4. Wprowadź ponownie nazwę użytkownika i hasło używane przez serwer SMTP i wybierz **Zapisz**.

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**. Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Wyświetlanie informacji o wydajności dla bezpośrednich i rozszerzonych raportów w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.
