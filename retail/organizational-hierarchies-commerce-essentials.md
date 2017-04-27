---
title: Organizacje i hierarchie organizacyjne (Podstawowe funkcje handlowe)
description: "Moduł Podstawowe funkcje handlowe zawiera trzy rodzaje wewnętrznych organizacji, które można zdefiniować, aby pomóc swojej organizacji realizować proces biznesowy lub osiągnąć cel."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 93711977ad8d861ca75ba80ee542ee112c8ddd2f
ms.lasthandoff: 03/31/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organizacje i hierarchie organizacyjne (Podstawowe funkcje handlowe)

[!include[banner](includes/banner.md)]


Moduł Podstawowe funkcje handlowe zawiera trzy rodzaje wewnętrznych organizacji, które można zdefiniować, aby pomóc swojej organizacji realizować proces biznesowy lub osiągnąć cel. 

Organizacja jest grupą osób, które działają razem dla przeprowadzenia procesu biznesowego lub osiągnięcia celu. Hierarchie organizacyjne reprezentują relacje między jednostkami biznesowymi, które tworzą organizację.

## <a name="organizations"></a>Organizacje
W module Podstawowe funkcje handlowe można zdefiniować trzy typy organizacji wewnętrznych: podmioty prawne (zwykle dla uproszczenia określane jako firmy), jednostki operacyjne i zespoły. W systemie Microsoft Dynamics AX wszystkie wewnętrzne organizacje są typami jednostek Strona. Z tego względu te organizacje używają książki adresowej do przechowywania adresów i innych informacji kontaktowych. Strona, która może być osobą lub organizacją, może należeć do jednej lub więcej książek adresowych.
### <a name="legal-entities"></a>Firmy

Firma to organizacja, która ma zarejestrowaną lub uchwaloną strukturę prawną. Firmy mogą zawierać zgodne z prawem umowy i wymaga się od nich przygotowywania zestawień na temat ich wydajności. Firma to typ podmiotu prawnego w systemie in Microsoft Dynamics AX, a każdy podmiot prawny jest skojarzony z identyfikatorem firmy. To skojarzenie istnieje, ponieważ identyfikator firmy lub DataAreaId, jest używany w niektórych modelach danych, w których firmy są używane jako granica zabezpieczeń danych. Użytkownicy mogą uzyskiwać dostęp do danych tylko dla firmy, do której są aktualnie zalogowani.

### <a name="operating-units"></a>Jednostki operacyjne

Jednostka operacyjna to organizacja używana do dzielenia formantu zasobów ekonomicznych i procesów operacyjnych w firmie. Osoby w jednostce operacyjnej mają obowiązek maksymalizować wykorzystanie ograniczonych zasobów i konta dla zapewnienia ich wydajności. W module Podstawowe funkcje handlowe typy jednostek operacyjnych obejmują centra kosztów, jednostki biznesowe, strumienie wartości, działy i kanały sieci sprzedaży. Poniższa tabela zawiera więcej informacji o każdym typie jednostki operacyjnej.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Typ jednostki operacyjnej** | **Opis**                                                                         | **Cel**                                                                                                                                 |
| Jednostka biznesowa           | Częściowo autonomiczna jednostka operacyjna utworzona w celu spełnienia strategicznych celów biznesowych. | Jednostki biznesowe służą do sprawozdawczości finansowej opartej na branżach lub liniach produktów, które organizacja obsługuje w ramach podmiotów prawnych. |
| Kanał sprzedaży detalicznej          | Jednostka operacyjna, która reprezentuje sklep tradycyjny.                             | Służy do zarządzania i kontrolowania jednego lub więcej sklepów w ramach jednej lub wielu firm.                                                               |

## <a name="organizational-hierarchies"></a>Hierarchie organizacyjne
W module Podstawowe funkcje handlowe każdej hierarchii jest przypisywany cel. Cel hierarchii określa typy organizacji, które mogą być uwzględniane w hierarchii. Cel decyduje również o tym, w których scenariuszach aplikacji można używać hierarchii. Na przykład hierarchia w module detalicznym może służyć do zakupów i sprzedaży produktów w sklepie sieci sprzedaży. Organizacje w hierarchii mogą współużytkować parametry, zasady i transakcje. Organizacja może dziedziczyć lub zastępować parametry swojej organizacji nadrzędnej. Jednak współużytkowane dane główne, takie jak produkty i książki adresowe, dotyczą całej organizacji i nie można ich zastąpić dla poszczególnych organizacji.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Najważniejsze wskazówki dotyczące konfigurowania organizacji w hierarchii

Podczas implementowania hierarchii organizacyjnej należy wziąć pod uwagę następujące wskazówki:
-   Utwórz dział do określenia przestrzeni wspólnej między firmą i jednostką biznesową. Następnie zbierz dane z działu do firmy na potrzeby raportowania ustawowego i z działu do jednostki biznesowej dla sprawozdawczości wewnętrznej.
-   W jednej firmie nie konfiguruj wielu hierarchii dla tego samego celu.
-   Nie twórz hierarchii dla każdego celu. Zazwyczaj można używać jednej hierarchii dla wielu celów. Na przykład do wszystkich celów związanych z zasadami można przypisać jedną hierarchię jednostek operacyjnych.
-   Utwórz zrównoważoną hierarchię. W hierarchii wszystkie węzły, które są w tej samej odległości od węzła głównego, są zdefiniowane jako poziom. W zrównoważonej hierarchii tylko jeden typ jednostki operacyjnej może wystąpić na każdym poziomie, a odległość od węzła głównego do każdego poziomu jest taka sama. Jeśli istnieją stopnie pośrednie między działem a firmą lub jednostką biznesową, symbol zastępczy organizacji może być wymagany w celu utworzenia zrównoważonej hierarchii.
-   Nie ustawiaj osobnej hierarchii jednostek operacyjnych, jeśli struktura firmy jest również strukturą operacyjną. Mieszana hierarchia firm i jednostek operacyjnych może służyć do obu celów.
-   Przed ustawieniem głównych scenariuszy restrukturyzacji użyj efektywnych dat hierarchii w celu wykonania analizy wpływu i testów weryfikacyjnych.
-   Zapisanie hierarchii jako wersji roboczej umożliwia wprowadzenie w niej zmian przed publikacją.
-   Ogranicz liczbę osób, które mają uprawnienia do dodawania i usuwania organizacji z hierarchii w środowisku produkcyjnym. Mniejsza liczba zmniejsza ryzyko, że mogą wystąpić kosztowne błędy i trzeba będzie dokonywać korekt.

## <a name="retail-store-management"></a>Zarządzanie sklepem sieciowym
W poniższej tabeli opisano scenariusze modułu Podstawowe funkcje handlowe, gdzie można używać hierarchii organizacyjnych.
| Zadanie                                                                           | Opis                                                                                                                                                                                                                                                                                                | Cel hierarchii    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Zarządzaj asortymentami sieci sprzedaży                                                      | Identyfikacja produktów, które są dostępne w każdym sklepie.                                                                                                                                                                                                                                             | Asortyment sieci sprzedaży    |
| Zarządzanie uzupełnianiami sieci sprzedaży                                                    | Grupuj sklepy do uzupełnienia zapasów na podstawie reguł uzupełnienia.                                                                                                                                                                                                                                          | Uzupełnianie zapasów sieci sprzedaży |
| Raportuj dane dla sklepów                                                         | Grupuj sklepy na potrzeby raportowania.                                                                                                                                                                                                                                                                                | Raportowanie sieci sprzedaży     |
| Księgowanie zapasów, obliczanie zestawień lub księgowanie zestawień dla grupy sklepów | Utwórz grupę sklepów, które można przypisać do zadania wsadowego. Podczas definiowania zadania wsadowego w celu księgowania zapasów, obliczania zestawień lub księgowania zestawień, można określić hierarchię, której dotyczy to zadanie. Jeśli sklepy są dodane lub usunięte z hierarchii, nie trzeba modyfikować zadania wsadowego. | Księgowanie punktu sprzedaży sieci sprzedaży   |






