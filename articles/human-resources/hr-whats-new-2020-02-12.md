---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (12 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 12 lutego 2020 roku.
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
ms.openlocfilehash: b89e022441f69825d9c9c56ecdbca2e09e461b9e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526947"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (12 lutego 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2867. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>Istniejące jednostki CompFixedEmpls i HcmPersonImage powinny być dostępne z protokołu OData (414178)

W przypadku nowego wydania z tego tygodnia jednostki **CompFixedEmpls** i **HcmPersonImage** są obecnie publiczne i dostępne za pośrednictwem protokołu ODAta.

## <a name="delete-employment-from-common-data-service-doesnt-work-when-employment-details-arent-active-403193"></a>Usuwanie zatrudnienia z Common Data Service nie działa, jeśli szczegóły zatrudnienia nie są aktywne (403193)

Dzięki tej zmianie można teraz usunąć zatrudnienie przez Common Data Service, gdy nie istnieją aktywne szczegóły dotyczące zatrudnienia.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>Przepływ pracy rejestracji kursu zmienia stan na zakończony oraz błędy po drugim zatwierdzeniu (409749)

Przepływ pracy rejestracji kursu został zaktualizowany w celu umożliwienia wielu osobom zatwierdzającym.

## <a name="in-preview"></a>Wersja próbna

Następujące funkcje w wersji zapoznawczej są dostępne od 3 lutego 2020 r.:

- **Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).

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
| Zmiany jednostki **Adres Pracownika** | Dodano **Ulica**</br>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | **Typ planu wynagrodzeń o zmiennej wysokości**</br>**Plan wynagrodzeń o zmiennej wysokości**</br>**Reguły wypłat**</br>**Poziom planu wynagrodzeń o zmiennej wysokości** |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | Dodano **jednostkę kalendarza pracy** |
| Nowa jednostka **Szczegół stanowiska listy płac** | Dodano **Szczegół stanowiska listy płac** |
| Nowa jednostka **Tytuł** | Dodano **Tytuł**. Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Common Data Service. Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**. |

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]