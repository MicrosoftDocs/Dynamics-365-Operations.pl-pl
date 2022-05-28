---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 20 września 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 20 września 2021 roku.
author: marcelbf
ms.date: 09/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a3fd8705c7735cb3c0945f71651fafa767a7addf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691590"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 20 września 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4464.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md) |
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Gotowe do wypłaty](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem | Opis |
|---|---|---|
| 619774 | Edytowanie opisu adresu nie jest synchronizowane Dataverse z obiektem w czasie rzeczywistym. | Podczas edytowania opisu adresu pracownika zaktualizowany opis nie jest synchronizowany w czasie rzeczywistym do Dataverse. Subskrypcja w tabeli **Lokalizacja logistyki** została zaktualizowana w celu wysłania aktualizacji. |
| 614603| Błąd na **stronie Pracownik**, gdy nie **wybrano parametru akcji** dotyczącej pracowników. | Podczas zatrudniania nowego pracownika lub przechodzenia do strony **Pracownik** wyświetlany jest następujący błąd: „Pole **Typ akcji dotyczącej pracowników** musi być wypełnione”, nawet jeśli akcje dotyczące pracowników są **wyłączone**. |
| 615367 | **Na karcie zatwierdzonego czasu wolnego** od czasu jest wyświetlane ostrzeżenie i wyświetlane niepoprawnie. | Jeśli jednostka urlopu ma wartość **Dni** przed włączeniem funkcji **Konfiguruj jednostki urlopu** według typu urlopu, na karcie **Zatwierdzony czas** wyłączenia jest wyświetlane nieprawidłowe ostrzeżenie i niepoprawne kolumny. |


## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub wyłączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Pola niestandardowe w aplikacji Eligibility |[Wsparcie pól niestandardowych w przetwarzaniu uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Korzystanie z pól niestandardowych w przetwarzaniu uprawnień](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Oświadczenie o korzyściach |[Oświadczenie o świadczeniach](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Oświadczenie o korzyściach](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Oświadczenie o korzyściach znane problemy

| Problem | Opis |
|---|---|
| **Strona parametrów** raportu w **samoobsługi pracownika etatowego** dla zestawienia świadczeń jest niepoprawna. | Po przejściu do **Oświadczenia świadczeń** w funkcji **samoobsługi pracownika e-pracy** na stronie **Parametry raportu** są wyświetlane **rekordy do dołączenia** i **uruchomić w tle** skróconych kart.  Należy je usunąć. |
| Zamknięte i przyszłe okresy są wyświetlane na stronie **Parametr raportu** dla zestawienia świadczeń. | Po przejściu do strony docelowej raportu **Sprawozdania o świadczeniach** użytkownik może wybrać okresy planów świadczeń, które są zamknięte lub mają datę przyszłą, co skutkuje pustą stroną. Na liście powinien być wyświetlany tylko okres bieżącego planu świadczeń. |
|Błąd podczas wysyłanie raportu pocztą e-mail przy użyciu lokalizacji docelowej raportu GER. | Zestawienie świadczeń można skonfigurować w celu używania parametrów poczty e-mail na stronie **Miejsca docelowe raportu GER**. Podczas konfigurowania i drukowania raportu użytkownik otrzyma błąd formatowania i wyciąg świadczeń nie zostanie wysłany.|


## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkcja | Szczegóły |
|---|---|
| Aktualizacja Platform Update 10.0.21 (45) | Publikacja aktualizacji platformy 10.0.21 ma się rozpocząć w następnym wydaniu serwisowym w dniu 4 października 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.21 aplikacji finansowych i operacyjnych (październik 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
|Widok rozszerzonych raportów arkuszy wydajności | Ta funkcja zostanie domyślnie włączona w następnym wydaniu. |


## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
