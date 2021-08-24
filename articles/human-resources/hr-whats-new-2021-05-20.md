---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 20 maja 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 20 maja 2021 roku.
author: marcelbf
ms.date: 05/20/2021
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
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4519e90e19d0652f855999d1a73ca64777b53b53465d6065987afc1cf2494187
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731944"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 20 maja 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4189.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aktualizacja Platform Update 10.0.18 (42) | -- | [Aktualizacje platformy dla wersji 10.0.18 aplikacji Finance and Operations (Maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| Aplikacja Human Resources w Microsoft Teams teraz obsługuje definicje pół dnia i możliwości dzielenia dnia | -- | [Zarządzanie wnioskami o urlop w Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem |  opis |
| --- | --- | --- |
| 583776 | Masowe zapisy pracowników do planów urlopowych powodują błąd zduplikowanego rekordu | Ten błąd został naprawiony w najnowszej wersji, a zapisy do planu urlopów masowych powinny być przetwarzane z powodzeniem. |
| 582263 | Nie można uruchomić przetwarzania zdarzeń życiowych dla wszystkich pracowników jednocześnie | Gdy pole **Pracownik** pozostaje puste w przetwarzaniu zdarzeń na żywo, wszyscy pracownicy zostaną przetworzeni. |
| 558383 | Beneficjent główny nie jest zaznaczony jako 100%, jeśli nie wybrano osoby wyznaczonej domyślnie | Błąd został naprawiony tak, że użytkownik musi tylko wybrać przełącznik beneficjenta głównego.|
| 509404 | Analityka zatrudnienia w departamentach nie uwzględniająca przepływu pracowników pomiędzy departamentami |Analityka została zaktualizowana w celu uwzględnienia przesunięć pracowników pomiędzy działami|
| 579420 | Funkcja zamrażania kolumn w siatkach nie powinna być jeszcze dostępna | Funkcja **Zamrażania kolumn w siatkach**, która nie jest dostępna w Human Resources, została wymieniona jako dostępna w Zarządzaniu funkcjami. Ta funkcja została usunięta z listy funkcji, które można włączyć. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obsługa pól niestandardowych w regułach uprawnień zarządzania świadczeniami | [Obsługa pól niestandardowych na potrzeby przetwarzania uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Konfigurowanie reguł uprawnienia](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Rozszerzenia środowiska przepływu pracy urlopów i nieobecności | [Rozszerzenia środowiska przepływu pracy urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2147528) | [Złóż wniosek o czas wolny](hr-employee-self-service-request-time-off.md)|
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|
| Przeprowadzanie inspekcji transakcji naliczania urlopów | - | [Przeprowadzanie inspekcji transakcji naliczania urlopów](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
|  Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
