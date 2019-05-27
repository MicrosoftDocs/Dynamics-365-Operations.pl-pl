---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (2 kwietnia 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8f488b0bf844fc04f07fedfa447073cdeabacc15
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518811"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-2-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (2 kwietnia 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="approval-emails-in-attract"></a>Wiadomości e-mail dotyczące zatwierdzeń w Attract
Nowe wiadomości e-mail dotyczące zatwierdzeń poprawiają widoczność w procesie zatwierdzania. Wiadomości e-mail są wysyłane do osób zatwierdzających w następujących sytuacjach:

- Wnioskodawca przesyła zadanie do zatwierdzenia.
- Zadanie zostaje odrzucone albo zatwierdzone.
- Osoba zatwierdzająca nie zareagowała na żądania zatwierdzenia w ciągu 24 godzin.

Można dostosować zawartość wiadomości e-mail dotyczącej zatwierdzenia, używając nowych szablonów.

### <a name="application-and-profile-attachments"></a>Załączniki aplikacji i profilu
Usprawnienia na karcie **Dokumenty** w profilach puli talentów i aplikacji pokazują teraz zarówno typ, jak i nazwę dokumentu.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Wkrótce (Attract i Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integracja lifecycle Services (LCS) z funkcją zgłaszania problemu
W Attract i Onboard problemy zarejestrowane przez użytkowników końcowych za pośrednictwem zgłaszania problemu teraz automatycznie tworzą problemy pomocy technicznej w projekcie LCS odbiorcy. Administratorzy mogą następnie sklasyfikować problemy i przesłać je do firmy Microsoft, w razie potrzeby. Jest to zgodne ze sposobem obsługi problemów użytkownika końcowego w Core HR.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2216.

### <a name="platform-update-25"></a>Aktualizacja platformy Update 25
Aby uzyskać więcej informacji dotyczących aktualizacji platformy 25, zobacz [Podgląd funkcji w aktualizacji platformy 25 Dynamics 365 for Finance and Operations (kwiecień 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)
W wielu organizacjach menedżerowie ds. wynagrodzenia i świadczeń mogą mieć dostęp tylko do konkretnych rekordów wynagrodzeń. Może to obejmować rekordy kierowników lub pracowników regionalnych. W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Role zabezpieczeń można przypisać do planów stałych i zmiennych. Te role zabezpieczeń określają dostęp do planów i powiązanych danych pracownika, takich jak wynagrodzenia i dodatki, więc tylko te role mogą przetwarzać wynagrodzenia dla grup pracowników.

### <a name="upgrade-to-common-data-service"></a>Uaktualnianie do rozwiązania Common Data Service
Zbliżają się terminy uaktualniania do Common Data Service dla aplikacji. Zaloguj się do Centrum administracyjnego usługi PowerApps, aby określić, czy baza danych wymaga uaktualnienia. Aby uzyskać więcej informacji dotyczących terminów i niezbędne kroki w celu uaktualnienia, zobacz [uaktualnienia do Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>Wersja próbna

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu
Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.
Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. Może to być spowodowane wymaganiami prawnymi lub polityką firmy. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

## <a name="coming-soon"></a>Wkrótce

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Ulepszona funkcja interfejsu użytkownika do sprawdzania zduplikowanych pracowników
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.

###  <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
Aktualizacja platformy 25 pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie. 
