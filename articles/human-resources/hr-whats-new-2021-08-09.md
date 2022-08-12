---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources z dnia 9 sierpnia 2021 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 9 sierpnia 2021 roku.
author: marcelbf
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58926e5a6c1476db84fa41945dc92196eb24f4bf
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068463"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources z dnia 9 sierpnia 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4393.

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu | Problem | Opis |
| --- | --- | --- |
| 558385 | Osoba wyznaczona domyślnie nie jest wybierana, jeśli zostanie włączona opcja **Automatyczny wybór osób wyznaczonych** dla osób wyznaczonych domyślnie. | Ten problem został rozwiązany. Wiele osób wyznaczonych domyślnie jest automatycznie wybieranych w kwalifikujących się planach, jeśli jest włączona opcja **Automatyczny wybór osób wyznaczonych** na stronie **Udostępnione parametry rozwiązania Human Resources**. |
| 589617 | Na stronie **Czas wolny** salda **Dostępne do zakupu** i **Dostępne do sprzedaży** są puste, jeśli dostęp jest ograniczony do określonej firmy. | Ten problem został rozwiązany. Na stronie **Czas wolny** salda **Dostępne do zakupu** i **Dostępne do sprzedaży** są wyświetlane poprawnie, jeśli użytkownik jest ograniczony do określonej firmy. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub wyłączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|
| Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | W tej wersji aktualizujemy widok obszaru roboczego menedżera nieobecności. Aby uzyskać więcej informacji, zobacz [konfiguracja ról menedżera urlopów](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu | [Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Konfigurowanie jednostek urlopu według typu urlopu | [Konfigurowanie jednostek urlopu według typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Gotowe do wypłaty](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkcja | Szczegóły |
| --- | --- |
| Aktualizacja Platform Update 10.0.21 (45) | Publikacja aktualizacji platformy 10.0.21 ma się rozpocząć w następnym wydaniu serwisowym w dniu 4 października 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.21 aplikacji finansowych i operacyjnych (październik 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

