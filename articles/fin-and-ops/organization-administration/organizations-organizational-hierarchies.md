---
title: Organizacje i hierarchie organizacyjne
description: "Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel. Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 4a7e1253d83e9212d423868a1f841b6944b07ad7
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="organizations-and-organizational-hierarchies"></a>Organizacje i hierarchie organizacyjne

[!include[banner](../includes/banner.md)]


Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel. Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę.

<a name="organizations"></a>Organizacje
-------------

W programie Microsoft Dynamics 365 for Finance and Operations można zdefiniować następujące typy organizacji wewnętrznych: podmioty prawne (zwykle dla uproszczenia określane jako firmy), jednostki operacyjne i zespoły.

Wszystkie organizacje wewnętrzne są typami jednostek **Strona**. Z tego względu te organizacje używają książki adresowej do przechowywania adresów i informacji kontaktowych. Strona, który może być osobą lub organizacją, może należeć do jednej lub więcej książek adresowych.
### <a name="legal-entities"></a>Firmy

Firma to organizacja, która ma zarejestrowaną lub uchwaloną strukturę prawną. Firmy mogą zawierać zgodne z prawem umowy i wymaga się od nich przygotowywania zestawień na temat ich wydajności. 

Firma jest typem podmiotu prawnego. W tej wersji programu Microsoft Dynamics 365 for Finance and Operations firma (w rozumieniu „przedsiębiorstw”) to jedyny rodzaj firmy, który można tworzyć, a każda firma jest skojarzona z identyfikatorem firmy. To skojarzenie istnieje, ponieważ niektóre obszary funkcjonalne w programie wykorzystują identyfikator lub DataAreaId firmy w ich modelach danych. W tych obszarach funkcjonalnych firmy są używane jako granica zabezpieczeń danych. Użytkownicy mogą uzyskiwać dostęp do danych tylko dla firmy, do której są aktualnie zalogowani.

### <a name="operating-units"></a>Jednostki operacyjne

Jednostka operacyjna to organizacja używana do dzielenia formantu zasobów ekonomicznych i procesów operacyjnych w firmie. Osoby w jednostce operacyjnej mają obowiązek maksymalizować wykorzystanie ograniczonych zasobów i konta dla zapewnienia ich wydajności. 

W programie Microsoft Dynamics 365 for Finance and Operations typami jednostek operacyjnych są centra kosztów, jednostki biznesowe, strumienie wartości, działy i kanały sprzedaży detalicznej. Poniższa tabela zawiera więcej informacji o każdym typie jednostki operacyjnej.

| Typ jednostki operacyjnej | Opis         | Cel      |
|---------------------|---------------------|--------------|
| Centrum kosztów         | Jednostka operacyjna, w której menedżerowie są rozliczani z budżetowanych i rzeczywistych rozchodów.                                                      | Służy do zarządzania i kontroli operacyjnej procesów biznesowych, które obejmują kilka podmiotów prawnych.                                         |
| Jednostka biznesowa       | Częściowo autonomiczna jednostka operacyjna utworzona w celu spełnienia strategicznych celów biznesowych.                                                        | Używana do sprawozdawczości finansowej opartej na branżach lub liniach produktów, które organizacja obsługuje niezależnie od podmiotów prawnych. |
| Strumień wartości        | Jednostka operacyjna, która kontroluje jeden lub więcej przepływów produkcji.                                                                                  | Powszechnie używana w module produkcji oszczędnej do kontrolowania działań i przepływów, które są wymagane w celu dostaw produktu lub usługi do konsumentów.  |
| Dział          | Jednostka operacyjna, która reprezentuje kategorię lub funkcjonalną część organizacji, która wykonuje określone zadanie, takie jak sprzedaż lub księgowanie. | Używana w raportach dla obszarów funkcjonalnych. Dział może mieć obowiązek raportowania zysków i strat i może się składać z grupy centrów kosztów.   |
| Kanał sprzedaży      | Jednostka operacyjna, która reprezentuje sklep tradycyjny, sklep internetowy lub internetowy serwis sprzedażowy.                                          | Służy do kontroli operacyjnej przynajmniej jednego sklepu w ramach podmiotu prawnego lub wielu podmiotów prawnych oraz do zarządzania takim sklepem.                                  |

### <a name="teams"></a>Zespoły

Zespół to organizacja, której członkowie mają wspólne obowiązki, zainteresowania lub cel. Nie można używać zespołów w hierarchiach organizacyjnych.

<a name="organizational-hierarchies"></a>Hierarchie organizacyjne
--------------------------

Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw. Można na przykład skonfigurować hierarchię podmiotów prawnych na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych. Hierarchia oparta na jednostkach operacyjnych służy do raportowania informacji finansowych niewymaganych przez prawo, ale używanych w kontroli wewnętrznej. Na przykład, można utworzyć hierarchię zakupów w celu kontroli zasad, reguł i procesów biznesowych zakupów. 

Każdej hierarchii jest przypisywany cel (przeznaczenie) w programie Microsoft Dynamics 365 for Finance and Operations. Cel hierarchii określa typy organizacji, które mogą być uwzględniane w hierarchii. Cel decyduje również o tym, w których scenariuszach aplikacji można używać hierarchii. 

Organizacje w hierarchii mogą współużytkować parametry, zasady i transakcje. Organizacja może dziedziczyć lub zastępować parametry swojej organizacji nadrzędnej. Jednak współużytkowane dane główne, takie jak produkty i książki adresowe, dotyczą całej organizacji i nie można ich zastąpić dla poszczególnych organizacji. Tworzenie organizacji i hierarchii wymaga dokładnego zaplanowania. Więcej informacji można znaleźć w temacie [Planowanie hierarchii organizacyjnej](plan-organizational-hierarchy.md).





