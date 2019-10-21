---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (14 grudnia 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
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
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 36eb5722a7bd98c404fb6c8f5bde407ab38ec28d
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024029"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-december-14-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent: Core HR (14 grudnia 2018 r.)

[!include [banner](includes/banner.md)]

**Kompilacja 8.1.2085**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="changes"></a>Zmiany

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>USA - obsługa ACA (Affordable Care Act) dla formularzy podatkowych 1095-B i 1095-C za rok 2018

Każdego roku pracodawcy ALE (Applicable Large Employer) muszą wystawiać pełnoetatowym pracownikom formularz 1095-C. Ponadto jeśli pracodawca zapewnia opcję samodzielnego ubezpieczenia, musi przedstawić formularz 1095-C (jeśli jest ALE) lub 1095-B (jeśli jest małym pracodawcą) wszystkim pracownikom (pełnoetatowym lub niepełnoetatowym) objętym jednym z oferowanych planów ubezpieczeń zdrowotnych. Ta funkcja zapewnia formularze 1095-C i 1095-B do wydrukowania.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Podczas importowania SubmittedByPersonId pole w HcmPerfJournalEntity jest ignorowane

Podczas importowania/eksportowania wpisów dziennika wydajności, pole **Przesłano przez** jest ignorowane. Dzięki tej zmianie wartość **zaimportowane/wyeksportowane** odpowiada bieżącej wartości w tabeli podczas eksportowania; podczas importowania system zostanie zaktualizowany o wartość podaną w pliku importu.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>Karta analizy w obszarze roboczym „Urlopy i nieobecności” zawiera błąd „OpenConnectionError” dla niesystemowych ról Administrator

Ta aktualizacja sprawi, że żadne błędy nie będą wyświetlane podczas otwierania na karcie **Analizy** w obszarze roboczym **Urlopy i nieobecności**.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Samoobsługa pracownika, wyświetlanie Hierarchii stanowisk z kafelka nie wyświetla węzła nadrzędnego

Wprowadzono zmianę w celu skorygowania błędu „Uzyskanie informacji o węźle nadrzędnym nie powiodło się” po dokonaniu personalizacji hierarchii stanowisk aby pojawiała się w istniejącym obszarze roboczym i wybraniu stanowiska w hierarchii.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>Musi być administratorem systemu, aby zobaczyć kartę Lista płac na stronie Stanowisko

Wprowadzono zmianę w celu objęcia prawidłowych elementów zabezpieczeń istniejącym uprawnieniem: „Obsługa szczegółów listy płac pracownika i stanowiska”. Po wprowadzeniu tej zmiany domyślnie administrator listy płac będzie miał dostęp do pól Lista płac na stronie Stanowisko.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Błąd podczas przesyłania przeglądu wydajności do menedżera i symbol zastępczy %Reviews.PerfPeriod% jest używany w instrukcji przesyłania

Zmiana została dokonana korygującą błąd „Odwołanie o wartości Null”, używając symbol zastępczy %Reviews.PerfPeriod% w instrukcji przesyłania.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>Raport Power BI siły roboczej zawiera błąd gdy data stażu pracownika jest dniem przestępnym

Po wprowadzeniu tej zmiany dni przestępne są teraz obsługiwane w Power BI.

### <a name="integration-between-core-hr-and-attract"></a>Integracja między Core HR i Attract

Wprowadzono zmianę w celu aktualizacji integracji między Core HR and Attract w związku z kandydatami do zatrudnienia. Aby kandydaci do zatrudnienia byli widoczni w przestrzeni roboczej **Zarządzanie personelem**, używane są następujące obiekty Common Data Service:

Podanie o pracę
- Przyczyna stanu musi być ustawiona do Oferta zaakceptowana
-   Zawiera informacje o kandydacie i wakacie

Kandydat
-   Zawiera informacje o kandydacie

Wakat
-   Zawiera identyfikator wakatu i uczestników wakatu

Uczestnicy wakatu
-   Zawiera informacje i menedżerze zatrudniającym

Po dodaniu kandydata w zarządzaniu personelem kandydat może również być zwolniony przy użyciu nowej opcji dostępnej na karcie kandydata.

## <a name="coming-soon"></a>Wkrótce

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Urlopy i nieobecności: przyszłe i urlopy i prognozowane saldo urlopów

Zmiany dotyczą opcji zezwalania pracownikom na przewidywanie czasu wolnego i przyszłych wniosków o czas wolny bez wpływu na aktualne saldo czasu wolnego, dlatego zmienia się również sposób wyświetlania czasu wolnego. 

Dostępne saldo aktualnie wyświetlana jest ilością czasu wolnego od pracy dostępną na żądania w tym naliczenia do dnia dzisiejszego oraz wszelkie zatwierdzone wnioski urlopowe do końca czasu. 

Po zwolnieniu zdolność do prognozy wyświetlane saldo zmienia się na bieżące saldo czasu wolnego wraz z naliczeniami i wnioskami do dnia dzisiejszego. Pracownicy i menedżerowie zobaczą te zaktualizowane salda w panelach samoobsługowych dla pracowników i menedżerów na karcie **Czas wolny** w oknie **Sala czasu wolnego**. Menedżerów HR będzie widział te zaktualizowane salda w przestrzeni roboczej **Osoby** i w oknie pracownika **Przypisane plany urlopów**.

## <a name="known-issue"></a>Znany problem

### <a name="mapping-errors-in-the-integration-with-finance"></a>Błędy mapowania w integracji z Finance

Zidentyfikowano następujące problemy w bieżącym szablonie odnośnie do integracji rozwiązania Talent z rozwiązaniem Dynamics 365 Finance. Nowy szablon zostanie wkrótce opublikowany i będzie stosowany do wszystkich nowych projektów integracji, które zostały utworzone. Dla istniejących projektów integracji mapowania zadań mogą być zaktualizowane. Zaktualizowane mapowania można znaleźć w poniższej tabeli. 

>[!NOTE]
> Zadanie Stanowiska do Przypisania pracy nadrzędnej do stanowisk nie integruje danych. Występuje problem, który jest aktualnie badany. Obecnie nie ma rozwiązania problemu mapowania. 

Zadanie Działy do Jednostka operacyjna musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła          | Pole nowego źródła |
| -------------------------------|------------------|
| cdm_description (Opis)  | cdm_name (nazwa)  |

Dodatkowe mapowanie również musi zostać dodane. Wybierz ostatnie pole **Brak**, aby dodać następujące mapowanie.

| Pole źródłowe                   | Pole docelowe    |
| -------------------------------|----------------------|
| cdm_description (Opis)  | NAMEALIAS (NAMEALIAS)|

Zaktualizowane mapowanie powinno wyglądać jak na poniższej ilustracji.

![Zadanie Działy na jednostki operacyjne](./media/DepartmentMapping.png)


Zadanie Prace na szczegóły pracy musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła          | Pole nowego źródła                   |
| -------------------------------|------------------------------------|
| cdm_name (nazwa)                | cdm_description (Opis)      |
| cdm_name (opis)         | cdm_jobdescription(opis zadania)|


Zaktualizowane mapowanie powinno wyglądać jak na poniższej ilustracji.

![Zadanie Praca na szczegóły pracy](./media/JobMapping.png)

Zadanie Pracownicy na pracownika musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła                 | Pole nowego źródła                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (adres e-mail 1)   | cdm_primaryemailaddress (główny adres e-mail) |
| cdm_telephone1 (telefon 1)          | cdm_primarytelephone (główny numer telefonu)       |

Przekształcenie pola płci również musi zostać zaktualizowane. Wybierz typ mapy **fn** (funkcja) dla płci i zaktualizuj następujące mapowania wartości.

| wartość Common Data Service                   | Wartość Finance and Operations                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Mężczyzna                                             |
| 75440001                    | Kobieta                                           |
| 75440002                    | Brak                                             | 
| 75440003                    | NonSpecific                                      |

Zaktualizowane mapowanie powinno wyglądać jak na poniższych ilustracjach.

![Zadanie Pracownicy na pracownika](./media/WorkerMapping.png)

![Przekształcenie pola płci](./media/WorkerTransform.png)
