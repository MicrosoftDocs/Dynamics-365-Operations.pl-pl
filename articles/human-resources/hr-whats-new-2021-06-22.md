---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 czerwca 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 22 czerwca 2021 roku.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 897c25df96017c5be1ae789027d178ca6b3ccc0410b4f65c7d2557b39e840134
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735358"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 czerwca 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4258.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Informowanie użytkowników o funkcji Pracownicy bez zatrudnienia - Gdy włączony jest dostęp zaawansowany, a w zarządzaniu cechami wyłączona jest funkcja **Wyświetl wszystkich pracowników bez zatrudnienia**, w formularzu Pracownicy bez zatrudnienia wyświetlany jest baner. Ten banner poinformuje użytkownika, aby włączył funkcję **Wyświetlanie wszystkich pracowników bez zatrudnienia**. | Nie dotyczy| [Pracownicy bez zatrudnienia](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Obsługa pól niestandardowych w regułach uprawnień zarządzania świadczeniami | [Obsługa pól niestandardowych na potrzeby przetwarzania uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Konfigurowanie reguł uprawnienia](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Przeprowadzanie inspekcji transakcji naliczania urlopów | Nie dotyczy | [Przeprowadzanie inspekcji transakcji naliczania urlopów](hr-leave-and-absence-accrue.md)|
| Rozszerzenia środowiska przepływu pracy urlopów i nieobecności | [Rozszerzenia środowiska przepływu pracy urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2147528) | [Złóż wniosek o czas wolny](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem |  opis |
| --- | --- | --- |
| 583052 | Użytkownik otrzymujący opinię może edytować otrzymaną opinię | Kiedy pracownik otrzymujący informację zwrotną na dzienniku wydajności wybiera **Dodaj link zewnętrzny**, formularz staje się edytowalny, pozwalając pracownikowi na edycję otrzymanej informacji zwrotnej. |
| 522281 | Wybór liczby pracowników na kafelkach struktury wynagrodzeń w Compensation Management prowadzi do nieprawidłowych wyników| Podczas przechodzenia do planów wynagrodzeń z obszaru roboczego Wynagrodzeń jest teraz wyświetlana prawidłowa liczba pracowników. |
| 580683 | Użytkownicy przypisani do ról Pracownik i Kierownik nie mogą dołączać notatek ani aktualizować dziennika wyników | Użytkownicy przypisani do ról Pracownik i Kierownik nie mogą dołączać notatek ani aktualizować dziennika wyników. Użytkownik odbiera komunikat o błędzie: „Nie można utworzyć rekordu we wpisie arkusza Wydajność (HcmPerfJournal). Odmówiono uprawnienia zasad zabezpieczeń”. |
| 583077 | Data urodzenia pracownika w kalendarzu nieobecności firmy jest nieprawidłowa | Użytkownicy będą mogli zobaczyć poprawną datę urodzenia pracowników w firmowym kalendarzu urlopów i nieobecności. |
| 586996 | Funkcja widoku urlopów w różnych firmach powoduje, że salda są puste, gdy dostęp jest ograniczony do jednej firmy | Użytkownicy mogą poprawnie wyświetlać przyszłe salda urlopów pracowników, gdy włączony jest widok urlopów między firmami. |
| 581014 | Włączenie widoku urlopów i nieobecności w różnych firmach powoduje błąd podczas wyświetlania przyszłych sald | Naprawiono błędy występujące, gdy użytkownicy przeglądali przyszłe salda urlopów przy włączonym widoku urlopów między firmami. |
| 509404 | Analityka zatrudnienia w departamentach nie uwzględniająca przepływu pracowników pomiędzy departamentami. | gdy pracownik przechodzi z jednego działu do drugiego, dane dotyczące liczby pracowników w dziale nie odzwierciedlają starego działu, z którego pracownik został przeniesiony, jeśli dane dotyczące stanowiska wygasły w bieżącym roku. |
| 584851 | Zasada prorogacji kredytu dla świadczenia „Brak” nigdy nie udziela kredytu |Reguła proracji kredytu elastycznego czasu pracy „Brak” oznacza, że pracownicy otrzymują zero korzyści za okres świadczeń, niezależnie od czasu zatrudnienia. Zostało to poprawione w taki sposób, że pracownik powinien otrzymać pełne kredyty elastyczne, jeśli został zatrudniony przed rozpoczęciem okresu zasiłkowego i żadne, jeśli został zatrudniony po rozpoczęciu tego okresu. |
| 584897 | Duplikowanie obowiązków „Użyj podstawowych funkcji zewnętrznych” powoduje błąd | Podczas próby zduplikowania obowiązku „Użyj podstawowych funkcji zewnętrznych” użytkownik odebrał błąd”, „Nie można odnaleźć obiektu o identyfikatorze UserDefinedAppHostDialogView” |
| 575692 | Naliczony urlop i nieobecność nie są dostępne dla oczekujących pracowników | Naliczanie urlopów i nieobecności może być uruchomione dla przyszłych pracowników, gdy włączone jest **Uproszczone wprowadzanie pracowników**. |
| 580110 | Dodanie firmy do integracji płacowej resetuje integrację do korzystania ze wszystkich podmiotów, nawet jeśli opcja jest ustawiona na nieodświeżanie projektu | Jeśli klient usunął podmioty lub zmienił projekt danych dla integracji płacowej i ma ustawioną opcję, aby zapobiec automatycznemu odświeżaniu projektu, dodanie nowej firmy do integracji ignoruje ustawienie i odświeża projekt.  |
| 584518 |Problem z wydajnością przetwarzania zapisów na korzyści | Ten błąd dotyczy problemów z wydajnością starszego procesu rejestracji świadczeń. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Aktualizacja Platform Update 10.0.19 (43) | Aktualizacja platformy z 10.0.19 ma się rozpocząć w następnym wydaniu serwisowym w dniu 28 czerwca 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.19 aplikacji Finance and Operations (czerwiec 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Przełącznik wyświetlania lat usługi | Funkcja ta daje możliwość wykorzystania różnych dat do obliczania lat pracy wyświetlanych na formularzu **Przyspieszone wprowadzanie pracownika** oraz na formularzu **Osoby**.  Będzie on dostępny w parametrach Human Resources. |
|  Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Wymagaj załączników dla określonych typów urlopów | Ta funkcja umożliwia administratorom możliwość dodawania zezwoleń na załączniki podczas przesyłania wniosków urlopowych dla określonych typów urlopów. |
|  Konfigurowanie jednostek urlopu według typu urlopu | Funkcja ta umożliwia administratorom konfigurację jednostek urlopowych (godzin lub dni) dla każdego typu urlopu.  |
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
