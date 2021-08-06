---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 12 lipca 2021
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 12 lipca 2021 roku.
author: marcelbf
ms.date: 07/12/2021
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
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2851c36594384dd62f4bb95263cfd4407aec104
ms.sourcegitcommit: 71952e97774547230285026c6a3a6caea2512920
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2021
ms.locfileid: "6614840"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 12 lipca 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4353.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
|  Przełącznik wyświetlania lat usługi | |Funkcja ta daje możliwość wykorzystania różnych dat do obliczania lat pracy wyświetlanych na formularzu **Przyspieszone wprowadzanie pracownika** oraz na stronie **Osoby**.  Będzie on dostępny w [parametrach Human Resources](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem |  opis |
| --- | --- | --- |
| 595871 | Okienko „Informacje” w dziale Zasoby ludzkie zawiera nieprawidłową terminologię Dataverse | Wraz ze zmianą nazwy Common Data Service na Dataverse terminologia została zaktualizowana w okienku informacyjnym Microsoft Dynamics 365 Human Resources (**Pomoc i wsparcie > Informacje**). |
| 598676 | Uproszczony formularz wprowadzania pracownika zastępuje zadanie może powodować błąd, gdy jest używany z Zapisanym widokiem| Jeśli na stronie **Pracownik** jest włączona funkcja „Usprawniony wpis pracownika”, aplikacja może się nie powieść, jeśli w zapisanym widoku ustawiono **Zawsze otwieraj do edycji**. |
| 592344 |Sekcja dotycząca pracowników na stanowisku powinna być odczytywana tylko wtedy, gdy włączone jest zarządzanie świadczeniami | Informacje o zestawieniu pracowników są tworzone przy użyciu starszych funkcji świadczeń.  Gdy zarządzanie świadczeniami jest włączone, pola będą tylko do odczytu. Gdy zarządzanie świadczeniami jest włączone, a opcja **Ukryj starsze formularze świadczeń** jest ustawiona na **Tak** we wspólnych parametrach HR, karta **Wynagrodzenie pracowników** zostanie ukryta. |
| 598617 | Zakładka aktywująca formularz **HcmDiscussion** powoduje nieskończoną pętlę podczas stosowania personalizacji | Gdy zarówno widok siatki, jak i widok szczegółów są włączone **Zawsze otwarte do edycji**, kod aktywujący kartę w zastąpionej metodzie zadania koliduje z personalizacją dotyczącą tego, jaka kontrolka powinna mieć fokus i tworzy nieskończoną pętlę. |
| 593553 | Pole Data dziennika w dzienniku wyników jest wyświetlane w czasie UTC | Pole **Data arkusza** dla dzienników wydajności jest wyświetlane w strefie czasowej UTC, a nie w strefie czasowej zdefiniowanej w ustawieniach daty systemowej, co powoduje, że w niektórych strefach czasowych data jest niepoprawna. |
| 586930 | Działania otwierające dla celów wydajnościowych otwierają zupełnie inny rekord | Gdy funkcja „Widok rozszerzonych raportów dzienników wydajności” jest włączona w Zarządzaniu funkcjami, wybranie celów wydajności dla raportów rozszerzonych na karcie **Mój zespół** w **Samoobsługa pracownicza** otwiera cele dla pracownika zamiast wybranego pracownika. |
| 569959 |  Jednostka HcmPositionWorkerAssignmentV2 nie przypisuje pracownika do stanowiska | Użytkownicy otrzymali błąd podczas dodawania rekordu przypisania stanowiska za pośrednictwem encji i publikowanie nie powiodło się. |
| 582259 | Raport VETS 4212 wykorzystuje formularz z 2017 r. zamiast formularza z 2020 r. | Zaktualizowano do formatu 2020.  Aby załadować nowy format, przejdź do **Konfiguracje raportów** i usuń raport VETS-4212 w lewej kolumnie. Przejdź do **Raportowanie elektroniczne - Repozytoria - Zasoby kadrowe** i wybierz pozycję **Otwórz**.  Wybierz **wydruk VETS-4212 PDF**, a następnie wybierz pozycję **Importuj**.|


## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|
|  Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Konfigurowanie roli menedżera nieobecności](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu | [Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Konfigurowanie jednostek urlopu według typu urlopu | [Konfigurowanie jednostek urlopu według typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Gotowe do wypłaty](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Aktualizacja Platform Update 10.0.20 (44) | Aktualizacja platformy z 10.0.20 ma się rozpocząć w następnym wydaniu serwisowym w dniu 26 lipca 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.20 aplikacji Finance and Operations (sierpień 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
