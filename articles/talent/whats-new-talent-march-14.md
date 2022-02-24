---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (14 marca 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a3bb5792e6395e6fe593691f050cae03362cf659
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528628"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-14-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (14 marca 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Inne niewielkie poprawki są dołączone do tej wersji.

## <a name="changes-in-onboarding"></a>Zmiany we wdrażaniu do pracy
Inne niewielkie poprawki są dołączone do tej wersji.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
**Kompilacja 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>Zarządzanie wydajnością nie działa we wszystkich scenariuszach podczas korzystania z ról zabezpieczeń duplikatów
Zmiany wprowadzone w tym wydaniu umożliwiają korzystanie ze scenariuszy zarządzania wydajnością przy użyciu gotowych lub zduplikowanych ról.

### <a name="mass-assign-checklists-to-workers"></a>Przypisanie grupowe listy kontrolnej do pracowników
Dzięki tej zmianie można teraz wybrać wielu pracowników i zbiorczo przypisać im jedną lub kilka list kontrolnych. 

### <a name="platform-update-24-for-finance-and-operations"></a>Aktualizacja 24 platformy dla Finance and Operations
Aby uzyskać dodatkowe szczegółowe informacje dotyczące Platform update 24 dla Finance and Operations, zobacz [Nowe lub zmienione funkcje w Platform update 24 Finance and Operations (2019 marca)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). Istotne zmiany w Platformie 24 obejmują: 

- W aplikacji Talent są włączone alerty.
- Zaktualizowany pasek nawigacyjny jest teraz dopasowany do nagłówka Biuro.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>Zmiana lokalizacji biura przełącza kontekst na górę listy pracowników
W obecnej wersji zmiana lokalizacji biura nie przełącza już kontekstu pracownika, który jest wyświetlony podczas przypisywania lokalizacji biura.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>Data końcowa przypisania stanowiska nie jest wyświetlana prawidłowo w akcjach zatrudnienia i przeniesienia pracownika.
Daty zakończenia przypisania stanowiska są teraz wyświetlane poprawnie na podstawie preferowanej przez użytkownika strefy czasowej podczas korzystania z akcji.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>Jednostka stanowiska w Common Data Service nie zezwala na aktualizowanie pól Typ stanowiska i Funkcja stanowiska
Jednostki w Common Data Service są teraz poprawnie synchronizowane po aktualizacji przy użyciu Common Data Service.

## <a name="coming-soon"></a>Wkrótce

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)
W wielu organizacjach menedżerowie ds. wynagrodzenia i świadczeń mogą mieć dostęp tylko do konkretnych rekordów wynagrodzeń. Te rekordy mogą dotyczyć kierowników lub pracowników regionalnych. W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Stałe i zmienne plany mogą mieć przypisane role zabezpieczeń, które będą określały dostęp do planów i danych pracowników związanych z planami, takich jak rekordy płac i premii. Tylko role z przyznanym dostępem mogą przetwarzać wynagrodzenia tych pracowników.

###  <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
Aktualizacja platformy 24 dla Finance and Operations pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie.

### <a name="duplicate-employee-check-interface-changes"></a>Sprawdzanie zduplikowanych pracowników: zmiany w interfejsie
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.
