---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (21 stycznia 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
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
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e9dee64e94c904cfe07c6a7766f6a60b1d60a2db
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528129"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (21 stycznia 2020 r.)

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract. Dodaliśmy funkcje do aplikacji Attract w celu obsługi naszego najnowszego ogłoszenia, [Budowa wydajniejszej organizacji pracowników z Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Pobierz dane środowiskowe

Administratorzy mogą pobierać dane dotyczące środowiska. Dane są eksportowane w standardowym formacie JSON ze wszystkimi zadaniami, kandydatami i konfiguracją eksportowanymi w pliku zip. Aby uzyskać więcej informacji, zajrzyj do [Eksport danych z aplikacji Attract i Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Ograniczanie dostępu do środowisk dla użytkowników niebędących administratorami

Administratorzy mogą teraz ograniczać dostęp do środowiska dla użytkowników niebędących administratorami. Tej operacji nie można cofnąć. Aby uzyskać więcej informacji, zobacz [Ograniczenie dostępu do aplikacji Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Eksportowanie przewodników wdrażania do pracy

Użytkownicy mogą eksportować wszystkie własne przewodniki wdrożeniowe oraz szablony dołączane w formacie dokumentu programu Word. Aby uzyskać więcej informacji, zajrzyj do [Eksport danych z aplikacji Attract i Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2726. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>Ostatnie pole kompensacja roczna w formularzu Sprawdź zatrudnienie jest niespójne (392092)

Ta wersja zawiera zmianę, która w sposób ciągły wyświetla najnowszą walutę opartą na selektorze firm w formularzu **weryfikacja zatrudnienia**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Znane jako pole dodane do wyszukiwania opinii odbiorcy (407789)

Przy dostarczaniu opinii dotyczących wydajności Wyszukiwanie pracowników nie zapewniło wystarczających informacji, aby określić, czy opinia jest kierowana do właściwej osoby. Dodaliśmy kolumnę **znany jako** ułatwiającą identyfikację unikatowej nazwy pracownika.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>Rekord HcmWorkerPayrollInfo jest tworzony bez skojarzenia z pracownikiem (394526)

Ta wersja zawiera zmianę, która umożliwia niezapisywanie rekordów HCMWorkerPayrollInfo bez odwołania do pracownika.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Możliwość edytowania działu podczas nawigowania z hierarchii stanowisk (341001)

Jeśli zabezpieczenia zostały skonfigurowane w celu odmowy dostępu do działów edycyjnych, Edycja jest wyłączona podczas nawigowania do formularza **działy** we wszystkich scenariuszach.

## <a name="coming-soon"></a>Wkrótce

Nowe rozwiązanie Common Data Service będzie dostępne wkrótce z następującymi zmianami:

| Opis | Zmiana |
| --- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | <ul><li>Dodano **Region wynagrodzenia**</li><li>Dodano **wymiary finansowe**</li></ul> |
| Zmiany jednostki **Pracownik** | <ul><li>Dodano **Kolejność w nazwisku**</li><li>Dodano **Pracuje z domu**</li><li>Dodano **Język**</li><li>Dodano **Data stażu pracy**</li><li>Dodano **Rocznica**</li><li>Dodano **Pierwotna data zatrudnienia**</li></ul> |
| Zmiany jednostki **Zatrudnienie** | <ul><li>Dodano **wymiary finansowe**</li><li>Dodano **Powód rozwiązania umowy**</li><li>**Data zakończenia** zmieniona z **daty przejścia**</li><li>Dodano **Okres próbny**</li></ul> |
| Zmiany jednostki **Adres Pracownika** | <ul><li>Dodano **Ulica**</li><li>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</li></ul> |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | <ul><li>**Typ planu wynagrodzeń o zmiennej wysokości**</li><li>**Plan wynagrodzeń o zmiennej wysokości**</li><li>**Reguły wypłat**</li><li>**Poziom planu wynagrodzeń o zmiennej wysokości**</li></ul> |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | <ul><li>Dodano **jednostkę kalendarza pracy**</li></ul> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]