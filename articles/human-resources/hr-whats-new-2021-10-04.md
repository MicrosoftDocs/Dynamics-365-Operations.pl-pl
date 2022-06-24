---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 5 października 2021 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 5 października 2021 roku.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cc8cd8616f1b82258fccbb2b41d5e72a90aaed63
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845120"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 5 października 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4485.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Aktualizacja Platform Update 10.0.21 (45) | -- | [Aktualizacje platformy dla wersji 10.0.21 aplikacji finansowych i operacyjnych (październik 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu | Problem | Opis |
|---|---|---|
| 598896 | Kwota pracownika etatowego nie będzie wyświetlana do momentu, gdy pracownik etatowy zakończy rejestrację | Na stronie **Samoobsługa pracownika etatowego** kwota pracownika etatowego dla świadczenia nie została wyświetlona. Na stronie **Samoobsługa świadczeń** kwota pracownika etatowego jest teraz wyświetlana.  |
| 613440 | Nie można wyeksportować danych z **Zarządzania danymi** | Eksportowanie danych dla projektu w **Zarządzaniu danymi** nieoczekiwanie kończy się niepowodzeniem. |
| 618327 | Zamknięte i przyszłe okresy są wyświetlane na stronie **Parametry raportu** dla zestawienia świadczeń | Po przejściu do **Oświadczenia świadczeń** w funkcji **samoobsługi pracownika e-pracy** na stronie **Parametry raportu** są wyświetlane **rekordy do dołączenia** i **uruchomić w tle** skróconych kart. Te sekcje zostały usunięte.|
| 618326 | Wyświetla się nieprawidłowa strona **Parametry raportu** w opcji **Samoobsługa pracownika etatowego** dla zestawienia świadczeń| Po przejściu do strony docelowej raportu **Sprawozdania o świadczeniach** użytkownik mógł wybrać okresy planów świadczeń, które są zamknięte lub mają datę przyszłą, co skutkuje pustą stroną. Na liście powinien być wyświetlany tylko okres bieżącego planu świadczeń. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub wyłączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Pola niestandardowe w aplikacji Eligibility |[Wsparcie pól niestandardowych w przetwarzaniu uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Korzystanie z pól niestandardowych w przetwarzaniu uprawnień](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Oświadczenie o korzyściach |[Oświadczenie o świadczeniach](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Oświadczenie o świadczeniach](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Oświadczenie o korzyściach znane problemy

| Problem | Opis |
|---|---|
|Błąd podczas wysyłanie raportu pocztą e-mail przy użyciu **lokalizacji docelowej raportu GER** | Zestawienie świadczeń można skonfigurować w celu używania parametrów poczty e-mail na stronie **Miejsca docelowe raportu GER**. Podczas konfigurowania i drukowania raportu użytkownik otrzyma błąd formatowania i wyciąg świadczeń nie zostanie wysłany.|

## <a name="feature-management-changes"></a>Zarządzanie funkcjami — zmiany

| Funkcja | Opis |
|---|---|
|Widok rozszerzonych raportów arkuszy wydajności | Ta funkcja zostanie domyślnie włączona w tym wydaniu. |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkcja | Szczegóły |
|---|---|
| Aktualizacja Platform Update 10.0.22 (46) | Publikacja aktualizacji platformy 10.0.22 ma się rozpocząć w następnym wydaniu serwisowym w dniu 1 listopada 2021 r. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.22 aplikacji finansowych i operacyjnych (listopad 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
