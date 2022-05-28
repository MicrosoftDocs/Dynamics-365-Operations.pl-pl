---
title: Uwierzytelnianie serwer-serwer dla interfejsu API integracji ATS
description: W tym temacie opisano sposób skonfigurowania uwierzytelniania serwer-serwer na rzecz integracji z interfejsem API integracji Dynamics 365 Human Resources systemu śledzenia kandydatów (ATS).
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 350fb5a00b85f28fa8aef2ca50cf1f277b8f635e
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743549"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Uwierzytelnianie serwer-serwer dla interfejsu API integracji ATS


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano sposób skonfigurowania uwierzytelniania serwer-serwer na rzecz integracji aplikacji z interfejsem API integracji Dynamics 365 Human Resources systemu śledzenia kandydatów (ATS). Istnieje kilka warstw zabezpieczeń, którymi należy zarządzać, aby jednostka usługi mogła uzyskać dostęp do wirtualnej tabeli Microsoft Dataverse i powiązanych danych. Użytkownik musi uzyskać dostęp do tabeli wirtualnej Dataverse w Microsoft Power Platform oraz dostęp do danych w Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Włącz dostęp do tabel wirtualnych Dataverse w Power Platform

Pierwszym krokiem umożliwiającym dostęp do tabel wirtualnych Dataverse w Power Platform jest skonfigurowanie aplikacji w Power Platform do uwierzytelniania względem punktów końcowych tabel wirtualnych Dataverse. Kroki do tego celu opisano w [podręczniku dewelopera Microsoft Dataverse](/powerapps/developer/data-platform).

  - Dla rejestracji aplikacji z jednym dzierżawcą: [Uwierzytelnianie serwer-serwer z jednym dzierżawcą](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Dla rejestracji aplikacji z wieloma dzierżawcami: [Użyj uwierzytelniania między serwerami dla wielu dzierżawców](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Tworzenie roli zabezpieczeń dla integracji ATS

Jednym z kroków po utworzeniu użytkownika aplikacji jest przypisanie użytkownika do roli zabezpieczeń, która definiuje dostęp aplikacji do punktów końcowych. Jest to krok 7 w [tworzeniu użytkownika aplikacji](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) dla rejestracji aplikacji z jedną dzierżawą i [Tworzenie roli zabezpieczeń dla użytkownika aplikacji](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) dla rejestracji z wieloma dzierżawcami. 

Rola, do której przypisujesz użytkownika aplikacji, powinna mieć dostęp do jednostek danych używanych do integracji z ATS. Ta rola nie istnieje, więc musi zostać utworzona nowa rola zabezpieczeń. Nową rolę można utworzyć w następujących krokach, które opisano w [Tworzenie roli zabezpieczeń](/power-platform/admin/create-edit-security-role#create-a-security-role).

W przypadku nowej roli odpowiedni dostęp musi być co najmniej przypisany do następujących jednostek na karcie **Jednostki niestandardowe** nowej roli. Należy pamiętać, że mogą istnieć dodatkowe encje, których dodanie może być konieczne, jeśli integracja wykorzystuje bardziej rozbudowane dane aplikacji. Po utworzeniu nowej roli można ją przypisać użytkownikowi aplikacji.

  - Pracownik podstawowy (mshr)
  - Kandydat do zatrudnienia (mshr)
  - Kwalifikacje certyfikatu (mshr)
  - Typ certyfikatu (mshr)
  - Firma
  - Wynagrodzenie funkcji stanowiska (mshr)
  - Wynagrodzenie typ stanowiska (mshr)
  - Kraj/regiony (mshr)
  - Dział (mshr)
  - Kwalifikacje z wykształceniem (mshr)
  - Stopień wykształcenia (mshr)
  - Dyscypliny edukacyjne (mshr)
  - Wymagania edukacyjne (mshr)
  - Identyfikacja (mshr)
  - Typ identyfikacji (mshr)
  - Instytucja (mshr)
  - Agencja wystawiająca (mshr)
  - Wynagrodzenie stanowiska (mshr)
  - Zadania (mshr)
  - Poziom wykształcenia (mshr)
  - Osoba kontaktowa strony (mshr)
  - Osoby (mshr)
  - Adresy osób (mshr)
  - Kontrola osoby (mshr)
  - Typ stanowiska (mshr)
  - Stanowiska V2 (mshr)
  - Kwalifikacje z doświadczeniem zawodowym (mshr)
  - Poziom oceniania (mshr)
  - Modele oceniania (mshr)
  - Kody przyczyn (mshr)
  - Wniosek o rekrutację (mshr)
  - Lokalizacja wniosku o rekrutację (mshr)
  - Stanowisko wniosku o rekrutację (mshr)
  - Wniosek o rekrutację umiejętności (mshr)
  - Typ kontroli (mshr)
  - Kompetencje umiejętności (mshr)
  - Umiejętności (mshr)
  - Tytuły (mshr)
  - Status kombatanta (mshr)
  - Pracownik (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Przyznawanie uprawnień aplikacji do danych Human Resources

Drugim krokiem jest upewnienie się, że aplikacja ma odpowiednie uprawnienia do danych w Human Resources, łącząc je z użytkownikiem w aplikacji Human Resources. W przypadku użytkownika aplikacji wywołania między serwerami za pośrednictwem tabel wirtualnych Dataverse są wykonywane w kontekście tożsamości użytkownika (aplikacji) w Dataverse, która wywołuje akcję. Usługa adaptera tabel wirtualnych następnie wyszukuje powiązanego użytkownika w dziale Human Resources i uruchamia zapytanie w kontekście tego użytkownika. Oznacza to, że w Human Resources musi zostać utworzony użytkownik z odpowiednimi rolami, aby zapewnić dostęp do danych, których będzie potrzebować integrująca aplikacja.

Użytkownik Human Resources musi mieć również przypisane prawidłowe uprawnienia do danych w Human Resources. Rola **Aplikacji Rekrutacja** (HcmRecruitingIntegrator) jest dostępna z uprawnieniami do podstawowych jednostek wymaganych do integracji z danymi rekrutacji. Tę rolę można przypisać do użytkownika aplikacji na stronie **Użytkownicy**, aby udzielić odpowiedniego dostępu do danych. Aby uzyskać więcej informacji o rolach zabezpieczeń HcmRecruitingIntegrator, zobacz temat [Zabezpieczenia oparte na rolach](/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Skonfiguruj nowego użytkownika z odpowiednimi uprawnieniami

Aby skonfigurować nowego użytkownika z odpowiednimi uprawnieniami, wykonaj następujące kroki:

  1. Otwórz stronę **Użytkownicy** w menu Human Resources i wybierz pozycję **Nowy**.
  2. Wprowadź **identyfikator użytkownika** i **nazwę użytkownika** nowego użytkownika aplikacji. Na przykład można wprowadzić „RecruitingIntegration”.

      > [!NOTE]
      > Jeśli aplikacja nie ma konta użytkownika lub adresu e-mail Microsoft Azure Active Directory (Azure AD), możesz umieścić coś takiego jak „RecruitingApp” w polach adresu e-mail i dostawcy dla użytkownika.

  3. Na karcie skróconej **Role użytkownika** wybierz akcję **Przypisz role**.
  4. W okienku **Przypisywanie ról do użytkownika** wybierz pozycję **Zgłoszenie rekrutacji** i wybierz przycisk **OK**.
  5. Zapisz nowy rekord użytkownika.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Połącz nowego użytkownika zasoby ludzkie z aplikacją

Po utworzeniu użytkownika musi zostać utworzony rekord dla aplikacji w formularzu Aplikacje, aby połączyć **aplikację Azure Active Directory** z użytkownikiem Human Resources.

  1. Otwórz formularz **Aplikacje Azure Active Directory** i wybierz pozycję **Nowy**.
  2. W polu **Identyfikator klienta** wprowadź identyfikator klienta użytkownika aplikacji utworzonego dla aplikacji.
  3. W polu **Nazwa** wpisz nazwę integrowanej aplikacji.
  4. W polu **Identyfikator użytkownika** wybierz nowego użytkownika grupy Human Resources utworzone dla integracji rekrutacji.
  5. Zapisz nowy rekord.

Aplikacja będzie miała wtedy dostęp do danych Human Resources, ograniczony tylko do danych wymaganych do integracji aplikacji.

## <a name="see-also"></a>Informacje dodatkowe

[Rekrutowanie kandydatów](hr-personnel-recruit.md)<br>
[Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Użyj interfejsu API sieci Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Tworzenie i aktualizowanie zestawów opcji przy użyciu interfejsu API sieci Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
