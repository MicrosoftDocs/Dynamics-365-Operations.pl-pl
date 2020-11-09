---
title: Przegląd katalogów zaopatrzenia
description: W tym artykule opisano w sposób ogólny, jak specjaliści ds. zakupów mogą konfigurować katalogi zaopatrzenia i nimi zarządzać. Katalogi zaopatrzenia definiują towary i usługi, które pracownicy firmy mogą zamawiać do użytku wewnętrznego.
author: mkirknel
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, CatDisplayProductRelationAdd
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64c7c2787e2ac996e3016f5b23fc48582f5533ad
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018912"
---
# <a name="procurement-catalogs-overview"></a>Przegląd katalogów zaopatrzenia

[!include [banner](../includes/banner.md)]

W tym artykule opisano w sposób ogólny, jak specjaliści ds. zakupów mogą konfigurować katalogi zaopatrzenia i nimi zarządzać. Katalogi zaopatrzenia definiują towary i usługi, które pracownicy firmy mogą zamawiać do użytku wewnętrznego.

Specjaliści ds. zakupu mogą tworzyć i obsługiwać katalogi towarów i usług, które mogą być kupowane na użytek wewnętrzny organizacji. Po skonfigurowaniu katalogów pracowników może utworzyć zapotrzebowania na zakup do zamawiania zawartych w nich pozycji. Katalogi te mogą służyć do wymuszania zasad zakupów, aby pracownicy mogli zamawiać tylko towary i usługi, które są dozwolone dla ich firmy. Podczas tworzenia katalogu zaopatrzenia, należy rozważyć następujące zadania:

-   Skonfiguruj hierarchię kategorii zaopatrzenia przed utworzeniem katalogu.
-   Określ, które produkty pracownicy będą mogli zamawiać. Można wyświetlić lub ukryć określone produkty w węźle katalogu lub można wyświetlić lub ukryć wszystkie produkty z węzła.
-   Określ, ile katalogów zaopatrzenia potrzebujesz. Dostęp do katalogu zaopatrzenia zależy od reguły dotyczącej katalogów skonfigurowanej dla firmy i jednostki operacyjnej, do której przypisany jest pracownik.

Kilka czynników decyduje o produktach dostępnych do zamówienia dla pracowników i kategoriach zaopatrzenia, z których mogą oni skorzystać podczas tworzenia zapotrzebowań na zakup:

-   Reguła dostępu do kategorii w zasadach zakupów określa kategorie zaopatrzenia, które są dostępne w zapotrzebowaniu na zakup. Jeśli żadna reguła nie zostanie określona, będą dostępne wszystkie kategorie zaopatrzenia.
-   Pracownicy mogą zamawiać tylko te produkty, które znajdują się w aktywnym katalogu zaopatrzenia organizacji i są w dostępnym węźle (a nie w ukrytym). Produkt musi być również w kategorii, do której określony pracownik ma dostęp zgodnie z regułą dostępu do kategorii.
-   Reguła katalogu określa używany katalog. Jeśli nie zostanie określona żadna reguła katalogu, tylko reguła dostępu do kategorii będzie określała produkty, które pracownik może zamówić z zapotrzebowania.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli opisano zadania, które należy wykonać, zanim specjalista ds. zakupów będzie mógł utworzyć katalog zaopatrzenia.

| Zadanie                                                | Rola               | Opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ustawianie hierarchii kategorii zaopatrzenia.            | Menedżer ds. zakupów | Hierarchie kategorii zaopatrzenia klasyfikują produkty lub transakcje dla celów raportowania i analiz. Używając hierarchii kategorii zaopatrzenia, firmy mogą strategicznie zarządzać kategoriami, produktami, dostawcami i innymi czynnikami zaopatrzenia z centralnej lokalizacji. Dla całej organizacji zdefiniowana jest jedna hierarchia kategorii zaopatrzenia. Katalog jest oparty na hierarchii kategorii zaopatrzenia: kategorie w hierarchii stają się węzłami w katalogu. Dostawcy i produkty znajdują się w katalogu. |
| Dodawanie dostawców i produktów do kategorii zaopatrzenia. | Menedżer ds. zakupów | Po utworzeniu hierarchii kategorii zaopatrzenia w danej organizacji, każdą kategorię zaopatrzenia można skojarzyć z określonymi dostawcami, produktami i tak dalej. Te skojarzenia są automatycznie kopiowane do katalogu.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Konfigurowanie katalogu
Po spełnieniu wymagań wstępnych, można skonfigurować katalogi. Można utworzyć jeden katalog dla całej organizacji lub wiele katalogów dla poszczególnych oddziałów. W przypadku utworzenia jednego katalogu dla całej organizacji dostęp do niego będzie kontrolowany przez zasady zakupów.  

Katalog określa, które produkty są dostępne podczas tworzenia zapotrzebowań na zakup, ale można wprowadzić dodatkowe ograniczenia, korzystając z zasad dostępu do kategorii. Ze względu na to, że węzły w katalogu są kategoriami zaopatrzenia, mogą być pominięte przez regułę dostępu do kategorii. W takim przypadku produkty w kategorii będą niedostępne dla pracowników na potrzeby zapotrzebowań. Reguły dostępu do kategorii można określić na stronie **Zasady zakupów**. W poniższej tabeli opisano zadania, które trzeba wykonać w celu skonfigurowania katalogu.

| Zadanie                                                   | Rola             | Opis                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie nowego katalogu.                                  | Pracownik działu zakupów | Podczas tworzenia katalogu, należy określić nazwę i opis dla katalogu. Można również określić, czy katalog będzie aktualizowany ręcznie czy automatycznie, oraz określić właściciela katalogu.                                                                                                                                      |
| Określ, czy produkty są dostępne w katalogu. | Pracownik działu zakupów | Ze względu na to, że produkty są dziedziczone z kategorii zaopatrzenia, pojawiają się w odpowiednich węzłach katalogu. Można kontrolować, czy wszystkie produkty w węźle będą ukryte czy widoczne, gdy katalog będzie wykorzystywany do tworzenia zapotrzebowania na zakup. Można również kontrolować, czy poszczególne produkty w węźle są ukryte albo wyświetlane. |
| Publikowanie katalogu.                                   | Pracownik działu zakupów | Zanim katalog będzie dostępny dla pracowników do tworzenia zapotrzebowań konieczne jest zdefiniowanie jego reguł, ustawienie statusu jako **Aktywny** i opublikowanie katalogu. Można również dezaktywować katalogi, które już nie mają być dostępne dla użytkowników.                                              |

Aktualizacje są publikowane automatycznie lub ręcznie, w zależności od opcji wybranych dla katalogu w polu **Domyślny typ aktualizacji** na stronie **katalogów**. Dostępne są następujące domyślne typy aktualizacji dla katalogów:

-   **Dynamiczna** — katalog jest automatycznie aktualizowany po każdej wprowadzonej do niego zmianie.
-   **Statyczna** — katalogi trzeba aktualizować ręcznie.
-   **Obie** — Jeśli katalog zawiera kategorie produktów, które mają domyślny typ aktualizacji **Statyczna** , należy go ręcznie aktualizować w przypadku zmiany tych kategorii. Jeśli katalog zawiera kategorie produktów, które mają domyślny typ aktualizacji **Dynamiczna** , jest automatycznie aktualizowany po wprowadzeniu każdej zmiany.


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustawianie hierarchii kategorii zaopatrzenia](tasks/set-up-procurement-category-hierarchy.md)



