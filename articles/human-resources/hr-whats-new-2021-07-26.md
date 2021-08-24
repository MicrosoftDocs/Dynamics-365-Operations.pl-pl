---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 26 lipca 2021
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 26 lipca 2021 roku.
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
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 810511c42cd690579d8c8b6ebcc17b0cf7fcb9eb2b999822dc2226fabd127cc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771522"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 26 lipca 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4384.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aktualizacja platformy Update 10.0.20 | -- | [Aktualizacje platformy dla wersji 10.0.20 aplikacji Finance and Operations (sierpień 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem |  opis |
| --- | --- | --- |
| 600422 | Błąd walidacji adresu listy płac dla programu Ready to Pay. | Sprawdzanie poprawności zostało zaktualizowane, aby wymagać tylko jednego adresu typu „Lokalizacja zamieszkania listy płac” i tylko jednego adresu typu „Lokalizacja pracy listy płac”. |
| 601226 | Problem integracji danych: Projekt eksportu integracji listy płac nie ma możliwości pełnego wypychania | Integracja listy płac z Ceridian DayForce tworzyła przyrostowe wypychanie zamiast pełnego wypychania. Ceridian wymaga, aby zawsze było pełne odświeżanie. Ten problem został naprawiony, encje w projekcie eksportu danych nie będą już przerzucane do pchania przyrostowego. |
| 602272 | Kafelki, które zostały dodane do obszaru roboczego samoobsługi pracownika, są teraz niedostępne i nie można już dodawać do niego kafelków. | Naprawiliśmy problem z personalizacją dla samoobsługi pracownika. Nowe kafelki mogą być dodawane do widoku, a każda istniejąca personalizacja będzie widoczna dla użytkowników |
| 600711 | Pole wyboru definicji połowy dnia włączone dla wniosków o urlop całodniowy | Ten problem został naprawiony i pole definicji pół dnia będzie aktywne tylko wtedy, gdy pracownicy wybiorą typ urlopu z włączoną definicją pół dnia i wybraną wartością pół dnia. |
| 602208 | Jednostki stawki narastającej wyświetlające godziny zamiast dni | Ten problem został rozwiązany. Formularz **Czas wolny** będzie wyświetlał prawidłową jednostkę urlopu (godziny lub dni) dla kolumny **Stawka narastająca**. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|
|  Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | W tej wersji aktualizujemy widok obszaru roboczego menedżera nieobecności. Aby uzyskać więcej informacji, zobacz [konfiguracja ról menedżera urlopów](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu | [Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Konfigurowanie jednostek urlopu według typu urlopu | [Konfigurowanie jednostek urlopu według typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Gotowe do wypłaty](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
