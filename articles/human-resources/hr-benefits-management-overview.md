---
title: Omówienie zarządzania świadczeniami
description: Omówienie funkcji Zarządzanie świadczeniami w Dynamics 365 Human Resources. Zaoferuj pracownikom rozszerzone opcje zarządzania świadczeniami w przyjaznym internetowym środowisku.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1043fb18c33e5ec0cde13008b168fd317c7c7be6
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599387"
---
# <a name="benefits-management-overview"></a>Omówienie obszaru roboczego Zarządzanie świadczeniami

Aby zachować konkurencyjność, należy oferować bogaty zestaw świadczeń, który pomoże przyciągnąć i utrzymać najlepszych pracowników. Oprócz standardowych świadczeń, takich jak opieka medyczna i dentystyczna, można również zaoferować rozszerzone usługi, takie jak pomoc we wdrożeniu do pracy, programy rekreacyjne i dodatki na odzież roboczą. Funkcja Zarządzanie świadczeniami dostępna w Microsoft Dynamics 365 Human Resources stanowi elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń. Moduł Human Resources zawiera również przyjazne środowisko obsługi pracownika, które eksponuje oferty pracodawcy.

- Rozszerzona funkcjonalność planów świadczeń umożliwia tworzenie unikatowych planów świadczeń i zarządzanie nimi oraz obsługę skomplikowanych tabel stawek i zagnieżdżonych warstw. Istnieje możliwość łatwego tworzenia programów świadczeń, pakietów i reguł automatycznego rejestrowania, aby ułatwić pracownikom obsługę.

- Programy kredytu elastycznego umożliwiają obliczanie proporcjonalne w celu uwzględnienia przejścia na emeryturę i innych zmian sytuacji życiowej.

- Rozbudowane reguły uprawnień pomagają udostępniać odpowiednie świadczenia odpowiednim pracownikom.

- Internetowa rejestracja na świadczenia ułatwia pracownikom korzystanie z systemu.

- Przetwarzanie kwalifikowanych zdarzeń życiowych obsługuje przyszłe zdarzenia życiowe.

Jeśli chcesz przejść do danych demonstracyjnych, musisz ponownie wdrożyć środowisko piaskownicy.

## <a name="benefits-management-known-issues"></a>Znane problemy związane z zarządzaniem korzyściami

### <a name="flex-credit-programs"></a>Programy kredytów elastycznych

Łączna wartość kredytu zdefiniowana dla programu kredytu elastycznego nie jest wyświetlana w formularzu **Plany świadczeń pracowniczych**. Ponadto, jeśli ustawisz program elastycznych kredytów w celu uwzględnienia reguły **Brak**, podczas wybierania i zatwierdzania planów pojawi się komunikat o błędzie w formularzu **Plan świadczeń pracowniczych**.

## <a name="enable-benefits-management"></a>Włączanie obszaru roboczego Zarządzanie świadczeniami

Ten artykuł opisuje sposób włączania funkcji w wersji zapoznawczej w module Human Resources. Informuje również, które z istniejących funkcji w module Human Resources są zastępowane lub wyłączane przez obszar roboczy Zarządzanie świadczeniami po jego włączeniu.

> [!IMPORTANT]
> Po włączeniu Zarządzania świadczeniami w środowisku **Produkcyjnym** nie można go wyłączyć. Zaleca się włączanie i testowanie Zarządzania świadczeniami w środowisku **Piaskownicy** przed włączeniem go w środowisku **Produkcyjnym**. Istnieją znaczne różnice między funkcjami starszego świadczenia i nowymi funkcjami zarządzania świadczeniami, które wymagają dodatkowej konfiguracji i powinny być testowane przed wprowadzeniem do produkcji.

- [Zarządzanie funkcjami](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Skonfiguruj informacje dotyczące pracowników

Aby można było zarejestrować pracowników w ramach świadczeń, musisz podać wymagane informacje. Należy zarejestrować pracownika w **Planie stałych wynagrodzeń** według daty rozpoczęcia, a następnie wybrać opcję **Częstotliwość wypłat świadczenia** w **Szczegóły zatrudnienia** w formularzu **Pracownik**.

Jeśli użytkownik ma pracownika, który otrzymuje dodatkowe wynagrodzenie, na przykład prowizje, może dodać kwotę **Świadczenia do wynagrodzenia rocznego** z rekordu pracownika etatowego. Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty rocznej dla stałej płacy będzie używana kwota **Świadczenia do wynagrodzenia rocznego**. **Świadczenia do wynagrodzenia rocznego** musi być ważne na dzień rozpoczęcia lub początek okresu świadczenia, w zależności od tego, która z nich jest najpóźniejsza. Jeżeli dla pracownika zostanie odnotowane zarówno stałe wynagrodzenie, jak i kwota rocznego wynagrodzenia za świadczenia, przy określaniu kwot pokrycia będzie się uwzględniać roczne wynagrodzenie za świadczenia.

Podczas tworzenia planu świadczeń, w którym używane są stawki oparte na płci lub wieku, należy wprowadzić datę urodzenia i płeć dla pracownika, aby obliczyć koszty świadczeń.

## <a name="configure-benefits-management"></a>Konfigurowanie zarządzania świadczeniami

Zanim będzie można tworzyć plany świadczeń dla pracowników, należy skonfigurować opcje dla planów.

- [Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami](hr-benefits-setup-parameters.md)
- [Konfigurowanie reguł i opcji uprawnień](hr-benefits-setup-eligibility-rules.md)
- [Konfigurowanie opcji uprawnień do kontaktu osobistego](hr-benefits-setup-contact-eligibility-options.md)
- [Tworzenie opcji zapotrzebowania](hr-benefits-setup-coverage-options.md)
- [Konfigurowanie częstotliwości płatności](hr-benefits-setup-payment-frequencies.md)
- [Konfigurowanie typów zdarzeń zmiany sytuacji życiowej](hr-benefits-setup-life-event-types.md)
- [Tworzenie typów planu](hr-benefits-setup-plan-types.md)
- [Ustawianie kodów przyczyn](hr-benefits-setup-reason-codes.md)
- [Ustawianie kodów warstw](hr-benefits-setup-tier-codes.md)
- [Konfigurowanie stawek](hr-benefits-setup-rates.md)
- [Konfigurowanie potrąceń](hr-benefits-setup-deductions.md)
- [Konfigurowanie dni oczekiwania](hr-benefits-setup-waiting-days.md)
- [Konfigurowanie okresów oczekiwania](hr-benefits-setup-waiting-periods.md)
- [Ustawianie reguł zaokrąglania](hr-benefits-setup-rounding-rules.md)
- [Tworzenie historii zatrudnienia](hr-benefits-setup-employment-categories.md)
- [Konfigurowanie typów zatrudnienia](hr-benefits-setup-employment-types.md)
- [Konfigurowanie samoobsługi pracownika etatowego](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Tworzenie planów świadczeń

W tych artykułach przedstawiono sposób tworzenia programów świadczeń, w tym pakietów i programów kredytu elastycznego.

- [Konfigurowanie planów świadczeń](hr-benefits-plans-setup.md)
- [Konfigurowanie elastycznych programów kredytów](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Przetwarzanie planów świadczeń

Niektóre zmiany trzeba przetworzyć, aby stały się aktywne.

- [Przetwórz uprawnienia do świadczeń](hr-benefits-process-enrollment-eligibility.md)
- [Przetwarzanie zmian sytuacji życiowej](hr-benefits-process-life-events.md)
- [Przetwarzanie wybranych zmian sytuacji życiowej](hr-benefits-process-life-event-changes.md)
- [Przetwórz uprawnienia do świadczeń z powodu zmiany sytuacji życiowej](hr-benefits-process-life-event-eligibility.md)
- [Przetwórz zmiany stawki](hr-benefits-process-rate-changes.md)

