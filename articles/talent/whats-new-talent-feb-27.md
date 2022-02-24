---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (27 lutego 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
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
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: afa1044c8adc9566149e20ade57e771b50d9c53f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529145"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (27 lutego 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2163

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Dodanie elementu menu Pola niestandardowe do administrowania systemem

Została dodana opcja przejścia do menu **Pola niestandardowe** w obszarze roboczym **administrowanie systemem**.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Ukrywanie importowania i tworzenie opcji dla nowych aplikacji mobilnych

Obecnie w module Talent nie można tworzyć nowych aplikacji mobilnych. Możliwość tworzenia nowych opcji na telefony komórkowe została usunięta z menu **aplikacji mobilnej**.

### <a name="variable-compensation-award-dmf-entity"></a>Nagrody dla wynagrodzenia o zmiennej wysokości (jednostka DMF)

W tej wersji można eksportować jednostkę (DMF) **Nagrody dla wynagrodzenia o zmiennej wysokości**.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Adresy w Wielkiej Brytanii są widoczne na stronie analiz zarządzania pracownikami tak jak adresy w Szwajcarii

W tej wersji adresy są pogrupowane według miejscowości. Ta wersja rozwiązuje problemy, które powodowały, że wizualizacje nieprawidłowo pokazywały lokalizację pracownika.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>Raport Power BI siły roboczej zawiera błąd, gdy data stażu pracownika jest dniem przestępnym

Została wprowadzona poprawka w programie Microsoft Power BI dla dat przejścia na emeryturę, wypadających 29 lutego.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>Stałe wynagrodzenie pracownika, Nagrody pracownika o zmiennej wysokości, Zmienne plany pracownika (rejestracje)zezwalają na korzystanie z pól niestandardowych

Teraz można dodawać pola niestandardowe w obszarach Stałe wynagrodzenie pracownika, Nagrody pracownika o zmiennej wysokości, Zmienne plany pracownika (rejestracje). Teraz można śledzić dodatkowe informacje dotyczące stałych i zmiennych wynagrodzeń pracownika (oprócz informacji dostępnych domyślnie). Pola niestandardowe można wprowadzać i aktualizować za pośrednictwem interfejsu użytkownika lub obiektów, które są dostępne.

### <a name="other-miscellaneous-bug-fixes"></a>Inne dodatkowe poprawki błędów

W tej wersji są też dostępne inne poprawki niewielkich błędów.

## <a name="coming-soon"></a>Wkrótce

### <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)

W wielu organizacjach menedżerowie ds. wynagrodzenia i świadczeń mogą mieć dostęp tylko do konkretnych rekordów wynagrodzeń. Te rekordy mogą dotyczyć kierowników lub pracowników regionalnych. Ta zmiana pozwala działowi kadr (HR) zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Role zabezpieczeń, które można przypisać do stałych i zmiennych planów będą określały dostęp do tych planów i danych pracownika (np. informacji o wynagrodzeniu i premiach). Tylko role z danym dostępem mogą przetwarzać wynagrodzenia dla tych pracowników.

### <a name="platform-update-24-for-finance-and-operations"></a>Aktualizacja 24 platformy dla Finance and Operations

Aby uzyskać więcej informacji o 24. aktualizacji platformy Microsoft Dynamics 365 Finance and Operations (marzec 2019), zobacz [Funkcje w wersji zapoznawczej w aktualizacji Platform update 24 rozwiązania Finance and Operations (marzec 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Włącz stałe wynagrodzenie dla przyszłych przypisań stanowisk

Jest to typowe, że nowo zatrudniani pracownicy mają daty rozpoczęcia pracy w przyszłości. Ta zmiana umożliwia definiowanie stałych wynagrodzeń dla pracowników z przypisaniem stanowisk w przyszłości.

## <a name="known-issues"></a>Znane problemy

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>Zmiany w szablonie integracji Core HR (Talent Common Data Service do Finance)
Szablon Core HR został zaktualizowany do „szablonu zaawansowanej kwerendy”. Dlatego domyślnie zaawansowana kwerenda będzie dostępna dla projektów, które zostały utworzone za pomocą tego szablonu. Ponadto wszelkie funkcje mapowania domyślnego będą widoczne tylko w edytorze zaawansowanej kwerendy. (Funkcje domyślnego mapowania są wyświetlane jako „FN” w mapowaniach.)

Aby uzyskać więcej informacji na temat błędów mapowania, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 Talent: Core HR (14 grudnia 2018 r.)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Aby użyć nowego szablonu, utwórz nowy projekt, a następnie wybierz nowy szablon integracji w rozwiązaniu Talent.

Aby zaktualizować istniejący szablon, wykonaj następujące kroki:

1. Zaktualizuj następujące mapowania:

    - **Zadanie Stanowiska do stanowiska:** usuń to mapowanie.
    - **Zadanie Stanowiska do Przypisania pracy nadrzędnej do stanowisk:** usuń to mapowanie.
    - **Zadanie stanowiska do bazowego stanowiska:** dodaj nowe mapowanie z **Zadanie stanowiska** Common Data Service do pozycji **bazowe stanowisko** w Finance and Operations. Przenieś je na pozycję 7 w sekwencji.

        [![Mapowanie zadania stanowiska do bazowego stanowiska](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Szczegóły stanowiska do bazowego stanowiska:** dodaj nowe mapowanie z **Zadanie stanowiska** Common Data Service do pozycji **Szczegóły stanowiska** w Finance and Operations. Przenieś je na pozycję 8 w sekwencji.

        [![Mapowanie zadania stanowiska do szczegółów dotyczących stanowiska](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Czas trwania stanowiska do bazowego stanowiska:** dodaj nowe mapowanie z **Zadanie stanowiska** Common Data Service do pozycji **Czas trwania stanowiska** w Finance and Operations.

        [![Mapowanie zadania stanowiska do okresów ważności stanowiska](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Hierarchie stanowiska do bazowego stanowiska:** dodaj nowe mapowanie z **Zadanie stanowiska** Common Data Service do pozycji **Hierarchie stanowiska** w Finance and Operations. Wybierz **kwerenda zaawansowana**, aby kwerenda zaawansowana była dostępna dla tego projektu.

       [![Przycisk kwerendy zaawansowanej](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Dodaj następujące mapowania:
    
    [![Mapowanie](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Wybierz łącze **zaawansowane kwerendy i filtrowanie** obok pola **wyszukiwania**.  

    3. Znajdź kolumnę **cdm_parentjobpositionid.cdm_jobpositionnumber**, a następnie wybierz przycisk ze strzałką w dół po prawej stronie.

    4. W oknie dialogowym wybierz **Usuń pusty**.

    5. Wybierz **Dodaj kolumnę \> Dodaj kolumnę warunkową**, aby dodać przekształcenia wartości domyślnych dla HIERARCHYTYPENAME.

        [![Polecenie Dodaj kolumnę warunkową](./media/Add-column.png)](./media/Add-column.png)

    6. W okienku **Dodaj kolumnę warunkową** wprowadź **HIERARCHYTYPENAME** jako nazwę nowej kolumny.
    7. W części **Jeżeli** warunku wybierz pole i użyj **równe** jako relacji, i wprowadź wartość. W częściach **_Wówczas_* i **W przeciwnym razie** warunku określ domyślną wartość. W takim przypadku należy wprowadzić **Wiersz** w obu częściach.

        [![Pole dialogowe dodawania kolumny warunkowej](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Wybierz **OK**, aby zamknąć okno **zaawansowanej kwerendy i filtrowania**.
    9. Na stronie **zadania mapowania** wybierz nową kolumnę jako źródło do utworzenia innego mapowania dla HIERARCHYTYPENAME.

        [![Mapowanie](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
