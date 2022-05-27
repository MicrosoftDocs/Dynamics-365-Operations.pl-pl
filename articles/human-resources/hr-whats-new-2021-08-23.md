---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources z dnia 23 sierpnia 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 23 sierpnia 2021 roku.
author: marcelbf
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c3448c373600ffebca82be41fb5849b952dfe1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686835"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources z dnia 23 sierpnia 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4419.

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem | opis |
| --- | --- | --- |
| 594066 | Nie można usunąć informacji kontaktowych | W przypadku wybrania opcji usunięcia rekordu informacji kontaktowych dla pracownika, usuwany jest rekord informacji kontaktowych inny niż wybrany rekord. |
| 611339 | Dodanie personalizacji powoduje, że konto bankowe ignoruje filtr i pobiera pierwszy rekord | Dodanie personalizacji powoduje, że na liście kont bankowych jest uruchamiane zapytanie personalizacji po uruchomieniu zapytania o źródło danych, w wyniku czego zapytanie pobiera pierwszy rekord, niezależnie od pracownika, dla którego szczegóły są przeglądane. |
| 591806 | Niepoprawnie obliczone zadania terminu dołączania | Terminy są niepoprawnie obliczane, jeśli istnieją następujące warunki: tworzone listy kontrolne używają kalendarza, w którym jest używany rozszerzony zakres czasu (na przykład od 2005 do 2050), a preferencje użytkownika wykorzystują strefę czasową inną niż środkowy czas standardowy. |   
| 592749 | Saldo urlopu jest niepoprawne w module **Samoobsługa pracownika etatowego** | Jeśli pracownik jest zatrudniony w więcej niż jednej firmie i jest włączony widok urlopu między firmami, saldo urlopu może być niepoprawne. |
| 603133 | Nieoczekiwane ostrzeżenie podczas składania wniosku o czas wolny | W przypadku składania wniosku o czas wolny wypełnianie pola **Pół dnia** przed polem **Kwota** spowoduje nieoczekiwane ostrzeżenie. |
| 606546 | Pole wybierania niewidoczne po zatwierdzeniu czasu wolnego | Pole wyboru do zaznaczania wielu zatwierdzonych wniosków urlopowych było niewidoczne. |
| 597059 | Pracownik etatowy niewidoczny w **firmowym kalendarzu nieobecności i urlopów** | Pracownik nie jest widoczny w **firmowym kalendarzu firmy nieobecności i urlopów**, jeśli zastosowany zakres dat obejmuje dzień, w którym odmówiono mu wniosku urlopowego. |


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
