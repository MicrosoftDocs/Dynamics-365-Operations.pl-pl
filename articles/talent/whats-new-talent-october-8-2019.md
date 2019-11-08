---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (8 października 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
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
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 159320dcbdf257862378b347172ef71832e293dc
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626069"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (8 października 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2542. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Usuwanie otwartej rejestracji świadczeń z podglądu publicznego

W powiązaniu z naszymi oświadczeniami w wpisie na blogu pt. [Strategiczne inwestycje w Core HR zwiększają doskonałość operacyjną](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/), firma Microsoft usuwa funkcję otwartej rejestracji świadczeń z podglądu publicznego 18 października 2019. Zamiast tego nowa funkcjonalność zostanie opublikowana w przyszłości. Korzystanie z funkcji korzystania z otwartej rejestracji świadczeń, która aktualnie znajduje się w podglądzie publicznym, nie będzie obsługiwane. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>Integracja z Common Data Service jest obecnie domyślnie wyłączona w nowych udostępnieniach (343675)
 
Podczas udostępniania nowych środowisk integracja z Common Data Service jest wyłączona. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie narzędzia integracji Common Data Service](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Usprawnione wprowadzanie pracowników i nawigacja

Funkcje dotyczące wprowadzania i nawigacji pracowników są teraz dostępne we wszystkich środowiskach. Aby włączyć tę funkcję, przejdź do **Administrowanie systemem \> Łącza \> Konfiguracja \> Parametry systemowe \> Funkcje w wersji zapoznawczej** i wybierz opcję **Formularz i nawigację rozszerzonego pracownika**. Ta funkcja jest następnie włączana dla wszystkich użytkowników. Opcję tę można wyłączyć w dowolnym momencie.

Aby uzyskać więcej informacji, zajrzyj do [Usprawnione wprowadzanie pracowników i nawigacja](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) w Dynamics 365: plan 2. fali publikacji 2019.

### <a name="issue-attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Błąd: Attract i Onboard tworzą nowych nieaktywnych pracowników w Core HR (380517)

Wydanie z tego tygodnia umożliwia skorygowanie problemu polegającego na tym, że Attract i Onboard tworzą pracowników nieaktywnych w Core HR.

### <a name="issue-the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Błąd: przepływ pracy kończy się niepowodzeniem, gdy menedżer jest zalogowany do innej firmy podczas zwalniania pracownika (346852)

Przepływ pracy przestanie działać w zależności od firmy, do której jest zalogowany menedżer.

### <a name="issue-missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Błąd: brak informacji na HcmOnboardingWorkerChecklistTaskEntity (349591)

Ta wersja zawiera dodatkowe informacje o **HcmOnboardingWorkerChecklistTaskEntity**. Oto kilka przykładów:

- **Nazwa grupy**, gdy typem przypisanym jest **grupa**
- **Nazwa pracownika**, gdy typem przypisanym jest **pracownik**
- **Nazwa menedżera**, gdy typem przypisanym jest **menedżer**

### <a name="issue-entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Błąd: jednostki nie są wymienione w kolejności alfabetycznej w administracji Common Data Service (377414)

Jednostki są wymienione w kolejności alfabetycznej w na stronie **Administracja CDS**.

### <a name="issue-changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>Błąd: zmiana typu zatrudnienia z datą przyszłą nie zezwala na przypisanie stanowiska (339958)

Ta zmiana umożliwia przypisywanie stanowisk w przypadku zmiany typów pracowników (na przykład od pracownika etatowego do zleceniobiorcy).

### <a name="issue-updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>Błąd: Aktualizacja jednostki Common Data Service transakcja banku urlopów tworzy nowy rekord w Talent (352938)

Transakcja dotycząca urlopu jest teraz aktualizowana w przypadku aktualizacji banku transakcji urlopów w Common Data Service.

### <a name="issue-the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>Błąd: tytuł załączników dla elementów informacji zwrotnych zawiera opis opinii (343765)

Opis opinii nie będzie już wyświetlany w tytule załącznika.

### <a name="issue-compensation-workflow-comments-field-shows-incorrect-content-339297"></a>Błąd: w polu Komentarze przepływu pracy wynagrodzenia wyświetlana jest niepoprawna zawartość (339297)

Ta zmiana powoduje wyświetlenie zawartości pola **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="issue-workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>Błąd: WorkCalendarEntity i WorkCalendarDayEntity nie są udostępniane za pośrednictwem protokołu OData (376329)

W tym wydaniu **WorkCalendarEntity** i **WorkCalendarDayEntity** są teraz dostępne za pośrednictwem protokołu OData (Open Data Protocol).

### <a name="issue-hcmworkerentity-is-slow-when-odata-is-used-375221"></a>Błąd: HCMWorkerEntity jest wolniejsza, gdy jest używany protokół OData (375221)

Zmiany zwiększają wydajność **HCMWorkerEntity**, gdy jest używany projektant skoroszytów Microsoft Excel.

### <a name="issue-manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>Błąd: wpis w arkuszu wydajności menedżera powoduje wyświetlenie błędu po usunięciu arkusza wydajności i utworzeniu nowego (336061)

Ta wersja koryguje problem występujący po usunięciu jednego arkusza wydajności i natychmiastowym utworzeniu nowego. Ta korekta zmienia zachowanie w ramach funkcji samoobsługi menedżera.

## <a name="coming-soon"></a>Wkrótce

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.
