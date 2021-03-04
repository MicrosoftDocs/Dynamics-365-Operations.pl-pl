---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 25 lutego 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 02/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1302686aeba52de484ad520efe292fafefc39ebf
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526817"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (25 lutego 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2927. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Włącz jednostkę nawigacji zarządzania sprawami i narzędzia do zarządzania danymi (DMF) (414754)

Ta funkcja podglądu umożliwia dodatkową nawigację w przypadkach zarządzania sprawami. Tę funkcję podglądu można włączyć w obszarze roboczym **Zarządzanie funkcjami**. Te elementy menu są wyświetlane w obszarze roboczym **Zgodność** programu Dynamics 365 Human Resources. W przypadku tej zmiany usługa Human Resources może uzyskiwać dostęp do:

- Wszystkie sprawy
- Moje sprawy
- Moje otwarte sprawy
- Moje zaległe sprawy
- Sprawy przypisane do mnie za pośrednictwem przepływu pracy

Wraz z tymi nowymi widokami dostępna jest również jednostka DMF **Szczegóły sprawy**.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Włącz definicje relacji w globalnej książce adresowej (414762)

Relacje są teraz włączone w globalnej książce adresowej. Przed wydaniem z tego tygodnia pole informacji **relacji** wyświetlało wszystkie relacje zdefiniowane w systemie. Teraz można zdefiniować te relacje na stronie globalnej książki adresowej.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>W przypadku istnienia aktywnych rekordów wynagrodzeń dla danego stanowiska można usunąć stanowisko (414568)

Przy tej zmianie zostanie wyświetlone ostrzeżenie podczas próby usunięcia stanowiska, jeśli pracownik ma aktywny rekord wynagrodzenia dla tego samego stanowiska. W takim przypadku należy zaktualizować rekord stałego wynagrodzenia pracownika przed usunięciem stanowiska.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>Przepływ pracy recenzji wydajności okazjonalnie dodaje podpisy, które nie są częścią procesu (414171)

Ta zmiana powoduje usunięcie problemy, gdy do przeglądu wydajności zostaną dodane dodatkowi podpisani uczestnicy.

## <a name="worker-position-assignment-not-created-in-common-data-service-when-selected-on-the-new-worker-dialog-413479"></a>Przypisanie stanowiska roboczego nie zostało utworzone w Common Data Service w przypadku wybrania opcji w oknie dialogowym Nowy pracownik (413479)

Ta zmiana powoduje usunięcie błędu podczas zatrudniania nowego pracownika i przypisywania nowego zatrudnienia do stanowiska za pośrednictwem okna dialogowego **Nowy pracownik**. Przypisana pozycja jest teraz odzwierciedlona w programie Common Data Service.

## <a name="coming-soon"></a>Wkrótce

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

W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach. Aby ręcznie zainstalować najnowsze rozwiązanie Common Data Service dla modułu Human Resources:

1.  Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).

2.  Wybierz opcję **Środowiska**.

3.  Znajdź środowisko, które chcesz uaktualnić. Powinno ono odpowiadać **nazwie środowiska** w sekcji **informacji programu Common Data Service** w formularzu **O** w usłudze Human Resources.

4.  Wybierz środowisko, aby wyświetlić szczegóły środowiska.

5.  Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry. Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.

6.  Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.

7.  Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.

## <a name="in-preview"></a>Wersja próbna

Następujące funkcje w wersji zapoznawczej zostały udostępnione 3 lutego 2020 r.:

- **Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]