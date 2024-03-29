---
title: Omówienie organizacji i hierarchii organizacyjnych
description: Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę.
author: sericks007
ms.date: 01/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom:
- "17291"
- intro-internal
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8e8f2c2004582f42c3f464fedf9f3d049b5278f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992084"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>Omówienie organizacji i hierarchii organizacyjnych

[!include [banner](../includes/banner.md)]

Organizacja to grupa osób, które pracują razem, aby przeprowadzić proces biznesowy lub osiągnąć cel. Hierarchie organizacyjne reprezentują relacje między organizacjami, które tworzą firmę.

## <a name="organizations"></a>Organizacje

Można zdefiniować następujące typy organizacji wewnętrznych: podmioty prawne (zwykle dla uproszczenia określane jako firmy), jednostki operacyjne i zespoły.

Wszystkie organizacje wewnętrzne są typami jednostek **Strona**. Z tego względu te organizacje używają książki adresowej do przechowywania adresów i informacji kontaktowych. Strona, który może być osobą lub organizacją, może należeć do jednej lub więcej książek adresowych.

### <a name="legal-entities"></a>Firmy

Firma to organizacja, która ma zarejestrowaną lub uchwaloną strukturę prawną. Firmy mogą zawierać zgodne z prawem umowy i wymaga się od nich przygotowywania zestawień na temat ich wydajności.

Firma jest typem podmiotu prawnego. Obecnie firmy to jedyny rodzaj podmiotu prawnego, który można tworzyć, a każdy podmiot prawny jest skojarzony z identyfikatorem firmy. To skojarzenie istnieje, ponieważ niektóre obszary funkcjonalne w programie wykorzystują identyfikator lub DataAreaId firmy w ich modelach danych. W tych obszarach funkcjonalnych firmy są używane jako granica zabezpieczeń danych. Użytkownicy mogą uzyskiwać dostęp do danych tylko dla firmy, do której są aktualnie zalogowani.

### <a name="operating-units"></a>Jednostki operacyjne

Jednostka operacyjna to organizacja używana do dzielenia formantu zasobów ekonomicznych i procesów operacyjnych w firmie. Osoby w jednostce operacyjnej mają obowiązek maksymalizować wykorzystanie ograniczonych zasobów i konta dla zapewnienia ich wydajności.

Typy jednostek operacyjnych obejmują centra kosztów, jednostki biznesowe, strumienie wartości, działy i kanały komercyjne. Poniższa tabela zawiera więcej informacji o każdym typie jednostki operacyjnej.

| Typ jednostki operacyjnej | Opis | Cel |
|---------------------|-------------|---------|
| Centrum kosztów         | Jednostka operacyjna, w której menedżerowie są rozliczani z budżetowanych i rzeczywistych rozchodów. | Służy do zarządzania i kontroli operacyjnej procesów biznesowych, które obejmują kilka podmiotów prawnych. |
| Jednostka biznesowa       | Częściowo autonomiczna jednostka operacyjna utworzona w celu spełnienia strategicznych celów biznesowych. | Używana do sprawozdawczości finansowej opartej na branżach lub liniach produktów, które organizacja obsługuje niezależnie od podmiotów prawnych. |
| Strumień wartości        | Jednostka operacyjna, która kontroluje jeden lub więcej przepływów produkcji. | Powszechnie używana w module produkcji oszczędnej do kontrolowania działań i przepływów, które są wymagane w celu dostaw produktu lub usługi do konsumentów. |
| Dział          | Jednostka operacyjna, która reprezentuje kategorię lub funkcjonalną część organizacji, która wykonuje określone zadanie, takie jak sprzedaż lub księgowanie. | Używana w raportach dla obszarów funkcjonalnych. Dział może mieć obowiązek raportowania zysków i strat i może się składać z grupy centrów kosztów. |
| Kanał sprzedaży      | Jednostka operacyjna reprezentująca sklep stacjonarny, sklep internetowy lub call center. | Służy do kontroli operacyjnej przynajmniej jednego sklepu w ramach podmiotu prawnego lub wielu podmiotów prawnych oraz do zarządzania takim sklepem. |

### <a name="teams"></a>Zespoły

Zespół to organizacja, której członkowie mają wspólne obowiązki, zainteresowania lub cel. Nie można używać zespołów w hierarchiach organizacyjnych.

## <a name="organizational-hierarchies"></a>Hierarchie organizacyjne

Hierarchie organizacyjne umożliwiają przeglądanie i raportowanie działalności biznesowej z różnych perspektyw. Można na przykład skonfigurować hierarchię podmiotów prawnych na potrzeby tworzenia raportów podatkowych, statutowych i ustawowych. Hierarchia oparta na jednostkach operacyjnych służy do raportowania informacji finansowych niewymaganych przez prawo, ale używanych w kontroli wewnętrznej. Na przykład, można utworzyć hierarchię zakupów w celu kontroli zasad, reguł i procesów biznesowych zakupów.

> [!NOTE]
> Po dodaniu jednostki operacyjnej do hierarchii nie można jej usunąć. 

Każdej hierarchii jest przypisywany. Cel hierarchii określa typy organizacji, które mogą być uwzględniane w hierarchii. Cel decyduje również o tym, w których scenariuszach aplikacji można używać hierarchii.

Organizacje w hierarchii mogą współużytkować parametry, zasady i transakcje. Organizacja może dziedziczyć lub zastępować parametry swojej organizacji nadrzędnej. Jednak współużytkowane dane główne, takie jak produkty i książki adresowe, dotyczą całej organizacji i nie można ich zastąpić dla poszczególnych organizacji. Tworzenie organizacji i hierarchii wymaga dokładnego zaplanowania. Więcej informacji można znaleźć w temacie [Planowanie hierarchii organizacyjnej](plan-organizational-hierarchy.md).

## <a name="additional-resources"></a>Dodatkowe zasoby
- [Planowanie hierarchii organizacyjnej](plan-organizational-hierarchy.md)
- [Tworzenie hierarchii organizacyjnej](tasks/create-organization-hierarchy.md)
- [Tworzenie firmy](tasks/create-legal-entity.md)
- [Tworzenie jednostki operacyjnej](tasks/create-operating-unit.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
