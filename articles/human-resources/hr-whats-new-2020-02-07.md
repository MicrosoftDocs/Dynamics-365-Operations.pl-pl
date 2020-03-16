---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (7 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6ca9877eb172794c67ac55b8dc54ed28af9576d
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076277"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (7 lutego 2020 r.)

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2835. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>Strona analizy nauki nie pokazuje kursu, jeśli klasa jest puste (388289)

Na stronie analizy nauki jest teraz wyświetlany kurs, jeśli klasa jest pusta.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>Funkcja wyszukiwania stanowisk nie uwzględnia strefy czasowej (405344)

Funkcja wyszukiwania otwartych stanowisk obecnie bierze pod uwagę strefę czasową podczas sprawdzania, czy stanowisko jest otwarte.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>Widok analizy bieżącego salda nie jest aktualizowany o poprawne aktualne saldo urlopu po przesłaniu wniosków urlopowych (409756)

Obecnie bieżące saldo uwzględnia przesłane wnioski urlopowe.

## <a name="in-preview"></a>Wersja próbna

Następujące funkcje w wersji zapoznawczej są dostępne od 3 lutego 2020 r.:

- **Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie zarządzania świadczeniami](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Wkrótce

### <a name="platform-update-32"></a>Aktualizacja platformy Update 32 

Aktualizacja platformy 32 będzie wkrótce dostępna. [Więcej informacji o aktualizacji platformy 32 znajdziesz tutaj](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

### <a name="updated-common-data-service-solution"></a>Zaktualizowano rozwiązanie Common Data Service

Nowe rozwiązanie Common Data Service będzie dostępne wkrótce z następującymi zmianami:

| Opis | Zmiana |
| ----------------------------------------- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | Dodano **Region wynagrodzenia**</br>Dodano **wymiary finansowe** |
| Zmiany jednostki **Pracownik** | Dodano **Kolejność w nazwisku**</br>Dodano **Pracuje z domu**</br>Dodano **Język**</br>Dodano **Data stażu pracy**</br>Dodano **Rocznica**</br>Dodano **Pierwotna data zatrudnienia** |
| Zmiany jednostki **Zatrudnienie** | Dodano **wymiary finansowe**</br>Dodano **Powód rozwiązania umowy**</br>**Data zakończenia** zmieniona z **daty przejścia**</br>Dodano **Okres próbny** |
| Zmiany jednostki **Adres Pracownika** | Dodano **Ulica**</br>**Wiersz adresu 1**, **wiersz adresu 2**i **wiersz adresu 3** oznaczone do zaniechania |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | **Typ planu wynagrodzeń o zmiennej wysokości**</br>**Plan wynagrodzeń o zmiennej wysokości**</br>**Reguły wypłat**</br>**Poziom planu wynagrodzeń o zmiennej wysokości** |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | Dodano **jednostkę kalendarza pracy** |
| Nowa jednostka **Szczegół stanowiska listy płac** | Dodano **Szczegół stanowiska listy płac** |
| Nowa jednostka **Tytuł** | Dodano **Tytuł**. Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Common Data Service. Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**. |

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)