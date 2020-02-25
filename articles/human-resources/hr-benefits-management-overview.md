---
title: Omówienie obszaru roboczego Zarządzanie świadczeniami
description: Omówienie funkcji w wersji zapoznawczej o nazwie Zarządzanie świadczeniami dostępnej w programie Dynamics 365 Human Resources. Zaoferuj pracownikom rozszerzone opcje zarządzania świadczeniami w przyjaznym internetowym środowisku.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029470"
---
# <a name="benefits-management-overview"></a>Omówienie obszaru roboczego Zarządzanie świadczeniami

[!include [banner](includes/preview-feature.md)]

Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników. Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą. Funkcja w wersji zapoznawczej Zarządzanie świadczeniami dostępna w rozwiązaniu Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń. Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.

- Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw. Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.

- Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.

- Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.

- Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.

- Funkcja przetwarzania kwalifikowanych zmian sytuacji życiowej jest zintegrowana z obszarem Samoobsługa pracownika etatowego i dodatkowo obsługuje przyszłe zmiany sytuacji życiowej.

Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.

Możesz przekazywać bezpośrednie opinie i zgłaszać problemy na adres: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Znane problemy związane z zarządzaniem korzyściami

### <a name="eligibility-processing"></a>Przetwarzanie uprawnień

Podczas używania uprawnień do świadczeń wykorzystujących ustawienia kwoty ubezpieczenia 1-5 X wynagrodzenie, % wynagrodzenia lub Równa kwota, należy w obszarze **Historia zatrudnienia** w ustawieniu **Szczegóły świadczenia** zaznaczyć wartość **Data rozpoczęcia pracownika etatowego**. Należy również wypełnić pola **Przepracowane godziny**, **Częstotliwość płatności** i **Kwota rocznego wynagrodzenia z tytułu świadczenia**. Jeśli pracownik otrzymuje stałe wynagrodzenie, wypełnij pola **Przepracowane godziny** i **Częstotliwość płatności**. Zostanie obliczona roczna kwota wynagrodzenia. Jeśli pracownik otrzymuje wynagrodzenie za etat, nie trzeba wypełniać pola **Przepracowane godziny**. Zaleca się, aby podczas tworzenia nowych pracowników najpierw wprowadzić stałe wynagrodzenie. Aby zaktualizować rekord szczegółów świadczenia, wybierz kolejno opcje **Pracownik > Historia pracownika > Szczegóły zatrudnienia**. Skoryguj datę na datę rozpoczęcia zatrudnienia pracownika.

### <a name="employee-self-service"></a>Samoobsługa pracownika etatowego

Kwota pracownika nie jest obliczana w przypadku aktualizacji kwoty ubezpieczenia na życie. Jeśli na przykład pracownikowi zostanie zaoferowany plan ubezpieczenia na życie, może on wybrać do 50 000 USD w ramach kosztu wynoszącego 0,36 USD za 1000 USD zwrotu.  Gdy pracownik aktualizuje kwotę zapotrzebowania, koszt przypisany do pracownika pozostanie równy zero.

W przypadku planu świadczeń, który zezwala tylko na jednokrotnie wybranie tego typu planu, użytkownik zobaczy błąd, jeśli zechce zrezygnować z planu po jego wybraniu. Na przykład użytkownik wybiera plan medyczny i umieszcza go w swoim koszyku. Następnie użytkownik wybiera **Zrzeczenie się** innego planu medycznego. Zostanie zwrócony błąd użytkownika.

## <a name="enable-benefits-management"></a>Włączanie obszaru roboczego Zarządzanie świadczeniami

Zarządzanie świadczeniami to funkcja w wersji zapoznawczej, która jest dostępna tylko w środowiskach typu **Piaskownica**. Te artykuły opisują sposób włączania funkcji w wersji zapoznawczej w module Human Resources. Informują również, które z istniejących funkcji w module Human Resources są zastępowane lub wyłączane przez obszar roboczy Zarządzanie świadczeniami po jego włączeniu.

- [Zarządzanie funkcjami](hr-admin-manage-features.md)
- [Funkcja w wersji zapoznawczej: Zarządzanie świadczeniami](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>Konfigurowanie obszaru roboczego Zarządzanie świadczeniami

Zanim będzie można tworzyć plany świadczeń dla pracowników, należy skonfigurować opcje dla planów.

- [Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami](hr-benefits-setup-parameters.md)
- [Konfigurowanie reguł i opcji uprawnień](hr-benefits-setup-eligibility-rules.md)
- [Konfigurowanie opcji uprawnień kontaktów osobistych](hr-benefits-setup-contact-eligibility-options.md)
- [Tworzenie opcji objęcia świadczeniami](hr-benefits-setup-coverage-options.md)
- [Konfigurowanie częstotliwości płatności](hr-benefits-setup-payment-frequencies.md)
- [Konfigurowanie typów zmiany sytuacji życiowej](hr-benefits-setup-life-event-types.md)
- [Tworzenie typów planów](hr-benefits-setup-plan-types.md)
- [Ustaw kody przyczyn](hr-benefits-setup-reason-codes.md)
- [Konfigurowanie kodów warstw](hr-benefits-setup-tier-codes.md)
- [Konfigurowanie stawek](hr-benefits-setup-rates.md)
- [Konfigurowanie potrąceń](hr-benefits-setup-deductions.md)
- [Konfigurowanie dni oczekiwania](hr-benefits-setup-waiting-days.md)
- [Konfigurowanie okresów oczekiwania](hr-benefits-setup-waiting-periods.md)
- [Konfigurowanie reguł zaokrąglania](hr-benefits-setup-rounding-rules.md)
- [Tworzenie kategorii zatrudnienia](hr-benefits-setup-employment-categories.md)
- [Konfigurowanie typów zatrudnienia](hr-benefits-setup-employment-types.md)
- [Konfigurowanie samoobsługi pracownika etatowego](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Tworzenie planów świadczeń

W tych artykułach przedstawiono sposób tworzenia programów świadczeń, w tym pakietów i programów kredytu elastycznego.

- [Konfigurowanie planów świadczeń](hr-benefits-plans-setup.md)
- [Tworzenie planów świadczeń pracowniczych](hr-benefits-plans-worker.md)
- [Konfigurowanie programów kredytu elastycznego](hr-benefits-plans-flex-credit-programs.md)
- [Konfigurowanie przyszłych zmian sytuacji życiowej](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Przetwarzanie planów świadczeń

Niektóre zmiany trzeba przetworzyć, aby stały się aktywne.

- [Przetwórz uprawnienia do świadczeń](hr-benefits-process-enrollment-eligibility.md)
- [Przetwarzanie zmian sytuacji życiowej](hr-benefits-process-life-events.md)
- [Przetwarzanie wybranych zmian sytuacji życiowej](hr-benefits-process-life-event-changes.md)
- [Przetwórz uprawnienia do świadczeń z powodu zmiany sytuacji życiowej](hr-benefits-process-life-event-eligibility.md)
- [Przetwórz zmiany stawki](hr-benefits-process-rate-changes.md)

