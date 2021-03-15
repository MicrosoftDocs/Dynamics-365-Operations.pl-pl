---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 marca 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 3 marca 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 03/03/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e4007daa51d661a2a6b67c323cfaf05c22543371
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128048"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 marca 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2955. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>Rozwiązanie Dataverse jest teraz dostępne z następującymi zmianami:

Nowe rozwiązanie Dataverse będzie dostępne wkrótce z następującymi zmianami:

| Opis | Zmiana |
| ----------------------------------------- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | Dodano **Region wynagrodzenia**</br>Dodano **wymiary finansowe** |
| Zmiany jednostki **Pracownik** | Dodano **Kolejność w nazwisku**</br>Dodano **Pracuje z domu**</br>Dodano **Język**</br>Dodano **Data stażu pracy**</br>Dodano **Rocznica**</br>Dodano **Pierwotna data zatrudnienia** |
| Zmiany jednostki **Zatrudnienie** | Dodano **wymiary finansowe**</br>Dodano **Powód rozwiązania umowy**</br>**Data zakończenia** zmieniona z **daty przejścia**</br>Dodano **Okres próbny** |
| Zmiany jednostki **Adres Pracownika** | Dodano **Ulica**</br>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | **Typ planu wynagrodzeń o zmiennej wysokości**</br>**Plan wynagrodzeń o zmiennej wysokości**</br>**Reguły wypłat**</br>**Poziom planu wynagrodzeń o zmiennej wysokości** |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | Dodano **jednostkę kalendarza pracy** |
| Nowa jednostka **Szczegół stanowiska listy płac** | Dodano **Szczegół stanowiska listy płac** |
| Nowa jednostka **Tytuł** | Dodano **Tytuł**. Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Dataverse. Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**. |

W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach. Aby ręcznie zainstalować najnowsze rozwiązanie Dataverse dla modułu Human Resources:

1.  Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).

2.  Wybierz opcję **Środowiska**.

3.  Znajdź środowisko, które chcesz uaktualnić. Środowisko powinno odpowiadać **nazwie środowiska** w sekcji **informacji programu Common Data Service** w formularzu **O** w usłudze Human Resources.

4.  Wybierz środowisko, aby wyświetlić szczegóły środowiska.

5.  Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry. Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.

6.  Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.

7.  Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Importowanie problemów z jednostką danych rejestracji urlopu (406082)

Można teraz zarejestrować pracownika w nowym planie dla urlopu tego samego typu, o ile nowa data rejestracji jest późniejsza niż data wygasłej rejestracji poprzedniego planu.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problem z eksportowaniem stóp składek w jednostce payrollWorkerEnrolledBenefitDetail 401k w DMF (420700)

Ta zmiana koryguje funkcję eksportu dla jednostki **payrollWorkerEnrolledBenefitDetail** w celu odzwierciedlenia bieżących wartości udziału pracodawcy.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>Wyszukiwanie w usprawnionym formularzu Pracownik powoduje pojawienie się informacji, że pole Osoba musi być wypełnione (402525)

Podczas wyszukiwania pracownika etatowego nie będzie już wyświetlany komunikat z informacją, że należy wypełnić pole **osoba**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>Wartość pola uwagi nie jest renderowana w formularzu Dodaj więcej kwalifikacji (380134)

Ta zmiana powoduje usunięcie zagadnienia podczas personalizowania formularza **Dodaj kolejne umiejętności** w module samoobsługowym pracownika etatowego.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Wiele planów stałych wynagrodzeń nie wygasa podczas przenoszenia pracowników etatowych (389466)

W przypadku zmiany wszystkie aktywne rekordy stałego wynagrodzenia dla starego stanowiska wygasną w dniu przejścia.

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