---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 19 kwietnia 2021
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 19 kwietnia 2021 roku.
author: marcelbf
ms.date: 04/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d0a908a6c1c8d8e08be61b684d29e9b37468ef80
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019257"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 19 kwietnia 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4113.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aktualizacja Platform Update 10.0.17 (41) | -- | [Aktualizacje platformy dla wersji 10.0.17 aplikacji Finance and Operations (kwiecień 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Obsługa pól niestandardowych w formularzach zarządzania świadczeniami | [Obsługa pól niestandardowych w zarządzaniu świadczeniami](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Omówienie zarządzania świadczeniami](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 552164 | **Zapisany widok** na **ekranie Samoobsługa pracownika > Otwarte kursy** nie działa dla kursów zawierających terminarz | Jeśli zapisany widok jest używany w otwartych kursach (ESS), a do jednego z kursów jest dołączony terminarz, w widoku przestaną być wyświetlane wiersze tego kursu |
| 560614 | Ekran **Świadczenia > Opcje zdarzenia zmiany sytuacji życiowej** wykazuje rozbieżności między dokumentacją etykietki narzędzia i zachowaniem kodu. | Zaktualizowano etykietki narzędzia na ekranie **Opcje zdarzenia zmiany sytuacji życiowej**, aby ich zachowanie było poprawne. |
| 560616 | Ekran **Świadczenia > Opcje zdarzenia zmiany sytuacji życiowej** można edytować w planie świadczeń pracownika, ale zmiany nie są uwzględniane. | Zaktualizowano zachowanie przełączników opcji zdarzenia zmiany sytuacji życiowej, aby były włączane lub wyłączane, na podstawie opcji osoby na utrzymaniu, zgodnie z dokumentacją etykietki narzędzia. |
| 565054 | Nie można wyświetlić listy **Pracownicy bez zatrudnienia**, gdy jest włączony **Dostęp zaawansowany**. | W tej wersji rozwiązano problem, w którym po włączeniu **dostępu zaawansowanego** tylko administratorzy systemu mogli wyświetlać zawartość listy **Pracownicy bez zatrudnienia**. Ponieważ ta poprawka jest zmianą zabezpieczeń, musi zostać włączona w zarządzaniu funkcjami. Gdy ta funkcja zostanie włączona, te role, które mają dostęp do formularza, będą widzieć zawartość, nawet jeśli jest w trybie dostępu zaawansowanego. Aby uzyskać więcej informacji, zobacz temat [Pracownicy bez zatrudnienia](hr-personnel-workers-without-employment.md). |
| 570586 | Sprawdzanie poprawności wniosku urlopowego jest odrzucane, gdy zatrudnienie kończy się przed najnowszą transakcją dla tego pracownika we wszystkich planach urlopów. | Po zakończeniu zatrudnienia sprawdzanie poprawności wniosku urlopowego nie jest odrzucane na podstawie transakcji urlopu pracownika.|
| 570783 | Włączenie i wyłączenie urlopów między firmami we wspólnych parametrach Human Resources zmienia to, co pracownicy zatrudnieni w jednej firmie widzą we wnioskach urlopowych. | Jeśli ten parametr jest włączony lub wyłączony, pracownicy zatrudnieni w jednej firmie nie widzą zmian we wniosku o czas wolny od pracy. |
| 572343 | Wymagany kod przyczyny nie jest wyświetlany, gdy jest włączona funkcja widoku urlopów między firmami. | Gdy jest włączona funkcja widoku urlopów między firmami, kod przyczyny jest teraz wyświetlany zgodnie z oczekiwaniami. |
| 573676 | Nie można dodać **okresu** na stronie **Zarządzanie świadczeniami > Łącza > Plany świadczeń**. | Usunięto błędy powodujące, że nie można było dodać lub zaktualizować **okresu** w istniejącym formularzu **Plan świadczeń**. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Rozszerzenia środowiska przepływu pracy urlopów i nieobecności | [Rozszerzenia środowiska przepływu pracy urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2147528) | [Złóż wniosek o czas wolny](hr-employee-self-service-request-time-off.md)|
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |
| Aktualizacja Platform Update 10.0.18 (42) | Aktualizacja platformy z 10.0.18 ma się rozpocząć w następnym wydaniu serwisowym w dniu 17 maja 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.18 aplikacji Finance and Operations (maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Obsługa pól niestandardowych w regułach uprawnień zarządzania świadczeniami  | [Obsługa pól niestandardowych na potrzeby przetwarzania uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
