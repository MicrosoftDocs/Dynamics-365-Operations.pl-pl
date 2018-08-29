---
title: "Synchronizowanie umów na projekty i projektów bezpośrednio z programu Project Service Automation do programu Finance and Operations"
description: "Ten temat zawiera opis szablonu i podstawowych zadań, które są używane do synchronizowania umów projektu i projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 65a274323a2d95c9c76727c9e40aa7e649e6350a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Synchronizowanie umów na projekty i projektów bezpośrednio z programu Project Service Automation do programu Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera opis szablonu i podstawowych zadań, które są używane do synchronizowania umów projektu i projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE] 
> Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, należy zainstalować poprawkę KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

> [!NOTE]
> Zanim będzie można używać rozwiązania do integrowania aplikacji Project Service Automation z Finance and Operations, należy się zapoznać z funkcją Integracja danych dostępną w programie Microsoft Dynamics 365.

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablon integracji, który jest dostępny z funkcji integracji danych, umożliwia przepływ danych na temat umów dotyczących projektów, projektów, wierszy umowy dotyczącej projektu i punktów kontrolnych wiersza umowy projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby przejść do dostępnych szablonów, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.

Następujący szablon i zadania podrzędne służą do synchronizowania umów dotyczących projektu i projektów z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

- **Nazwa szablonu w narzędziu Integracja danych:** Projekty i umowy (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:**

    - Umowy na projekt z PSA do Fin and Ops
    - Projekty z PSA do Fin and Ops
    - Wiersze umowy na projekt z PSA do Fin and Ops
    - Punkty kontrolne wiersza umowy na projekt z PSA do Fin and Ops

Zanim będzie możliwa synchronizacja umów na projekty i projektów, należy zsynchronizować konta.

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation       | Finance and Operations                                 |
|----------------------------------|--------------------------------------------------------|
| Zamówienia                           | Jednostka integracji umowy projektu                |
| Projekty                         | Jednostka integracji dla projektu                         |
| Wiersze zamówienia                      | Jednostka integracji wiersza umowy projektu           |
| Punkty kontrolne wiersza umowy na projekt | Jednostka integracji punktu kontrolnego wiersza umowy projektu |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie umowami na projekt odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance and Operations jako umowy na projekt. W szablonie integracji można ustawić źródło integracji w programie Finance and Operations dla umowy na projekt.

Zarządzanie projektami rozliczanymi według czasu i materiałów oraz projektami ze stała ceną odbywa się w aplikacji Project Service Automation. Projekty te są synchronizowane z aplikacją Finance and Operations jako projekty. W ramach integracji za pomocą szablonu można ustawić źródło integracji w programie Finance and Operations dla projektu.

Zarządzanie wierszami umowy na projekt odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance and Operations jako reguły fakturowania umowy na projekt. Jeśli metoda fakturowania różni się od domyślnej dla typu projektu, synchronizacja spowoduje zaktualizowanie typu projektu dla projektu w wierszu umowy i grupy projektów.

Zarządzanie punktami kontrolnymi wiersza umowy na projekt odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance and Operations jako punkty kontrolne reguł fakturowania umowy na projekt.

## <a name="project-service-automation-to-finance-and-operations-integration-solution"></a>Rozwiązanie do integrowania aplikacji Project Service Automation z Finance and Operations

Pole **Identyfikator umowy dotyczącej projektu** jest dostępne na stronie **Umowy dotyczące projektu**. To pole pełni rolę naturalnego i unikatowego klucza wspierającego integrację.

Jeśli podczas tworzenia nowej umowy projektu wartość **Identyfikator kontraktu projektu** jeszcze nie istnieje, jest ona generowana automatycznie przy użyciu numeracji. Wartość składa się z prefiksu **ORD**, po którym następuje zwiększona kolejna liczba, a następnie sześcioznakowy sufiks. Oto przykład: **ORD-01022-Z4M9Q0**.

Pole **Numeru projektu** jest dostępne na stronie **Projekty**. To pole pełni rolę naturalnego i unikatowego klucza wspierającego integrację.

Jeśli podczas tworzenia nowego projektu wartość **Numer projektu** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji. Wartość składa się z prefiksu **PRJ**, po którym następuje zwiększona kolejna liczba, a następnie sześcioznakowy sufiks. Oto przykład: **PRJ-01049-CCNID0**.

Gdy używane są rozwiązania integracji aplikacji Project Service Automation do Finance and Operations<TO DO: link in the top level document link where we will be adding the instructions for applying the PSA solution>, skrypt uaktualniania ustawia pole **Identyfikator umowy projektu** dla istniejących umów projektów i pole **Numer projektu** dla istniejących projektów w aplikacji Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

- Zanim będzie możliwa synchronizacja umów na projekty i projektów, należy zsynchronizować konta.
- W zestawie połączeń dodaj mapowanie pola klucza integracji **msdyn\_organizationalunits** do elementu **msdyn\_name \[nazwa\]**. Najpierw trzeba będzie dodać projekt do zestawu połączenia. Aby uzyskać więcej informacji o kluczach integracji, zobacz [Integracja danych w usłudze Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).
- W zestawie połączeń dodaj mapowanie pola klucza integracji z **msdyn\_projects** do elementu **msdynce\_projectnumber \[numer projektu\]**. Najpierw trzeba będzie dodać projekt do zestawu połączenia. Aby uzyskać więcej informacji o kluczach integracji, zobacz [Integracja danych w usłudze Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).
- Pole **SourceDataID** umów na projekty i projektów można zaktualizować na inną wartość lub usunąć z mapowania. Domyślną wartością szablonu jest **Project Service Automation**.
- Mapowanie **PaymentTerms** należy zaktualizować, tak aby odzwierciedlało prawidłowe warunki płatności w aplikacji Finance and Operations. Można również usunąć mapowanie z zadania projektu. Mapa wartości domyślnych zawiera wartości domyślne dla danych demonstracyjnych. W poniższej tabeli przedstawiono wartości w rozwiązaniu Project Service Automation.

    | Wartość | opis   |
    |-------|---------------|
    | 1     | Netto 30        |
    | 2     | 2%10, netto 30 |
    | 3     | Netto 45        |
    | 4     | Netto 60        |

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć dodatku Microsoft Power Query dla programu Excel do odfiltrowania danych, jeśli są spełnione następujące warunki:

- Masz zamówienia sprzedaży w Microsoft Dynamics 365 for Sales.
- Istnieje wiele jednostek organizacyjnych w rozwiązaniu Project Service Automation. Jednostki te zostaną zmapowane do wielu podmiotów prawnych w rozwiązaniu Finance and Operations.

Jeśli musisz używać narzędzia Power Query, przestrzegaj następujących wytycznych:

- Szablon Projekty i umowy (PSA do Fin and Ops) zawiera domyślny filtr obejmujący wyłącznie zamówienia sprzedaży typu **Element roboczy (msdyn\_ordertype = 192350001)**. Ten filtr gwarantuje, że umowy dotyczące projektów są tworzone dla zamówień sprzedaży w programie Finance and Operations. Jeśli tworzysz własny szablon, musisz dodać ten filtr.
- Należy utworzyć filtr do narzędzia Power Query uwzględniający tylko organizacje umowy, które mają być synchronizowane z firmą integrującą zestaw połączenia. Na przykład umowy na projekty, które masz zawarte z jednostką organizacyjną Contoso US, powinny być synchronizowane z firmą USSI, ale umowy na projekty zawarte z jednostką organizacyjną Contoso Global mają być synchronizowane z firmą USMF. Jeśli nie dodasz tego filtra do swojego mapowania zadań, wszystkie umowy na projekty będą synchronizowane z firmą zdefiniowaną dla zestawu połączeń, bez względu na jednostkę organizacyjną umowy.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE] 
> Pola **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** i **AddressZipCode** nie są uwzględnione w domyślnym mapowaniu dla umów na projekty. Jeśli trzeba zsynchronizować te dane dla umów dotyczących projektów, możesz dodać mapowania.
>
> Pola **Opis**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** i **ProjectType** nie są uwzględnione w domyślnym mapowaniu dla projektów. Jeśli trzeba zsynchronizować te dane dla projektów, możesz dodać mapowania.

Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mapowanie szablonu](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mapowanie szablonu](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mapowanie szablonu](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

