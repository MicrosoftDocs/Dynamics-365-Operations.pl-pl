---
title: Hierarchie sieci sprzedaży
description: Ten artykuł opisuje hierarchie sieci sprzedaży w programie Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cf8db2c828f99dfd4c220966e31894dcd6eda572
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023709"
---
# <a name="retail-hierarchies"></a>Hierarchie handlu detalicznego

[!include [banner](includes/banner.md)]

Ten artykuł opisuje hierarchie w programie Dynamics 365 Commerce.

Można skonfigurować hierarchię kategorii w celu zorganizowania produktów sprzedawanych w Twoim kanale. Hierarchie produktów umożliwiają łączenie produktów w kategorie i grupy. Następnie można używać tych produktów do tworzenia asortymentów produktów i programów lojalnościowych. Można również przypisywać właściwości i atrybuty produktu, strukturę cen, dodawać produkty w do produktów i używać produktów na potrzeby raportowania. Można utworzyć jedną hierarchię kategorii do reprezentowania wszystkich produktów i kategorii w organizacji, a następnie użyć tej hierarchii kategorii do wielu celów. Alternatywnie można utworzyć wiele hierarchii kategorii do celów specjalnych, takich jak promocja produktów. Podczas tworzenia hierarchii produktów należy przypisać typ hierarchii kategorii w celu identyfikacji przeznaczenia hierarchii kategorii. Na przykład tylko hierarchie produktów, które mają przypisany typ **Hierarchia nawigacji w handlu**, są wskazywane podczas przeglądania produktów według kategorii online lub w punkcie sprzedaży.

## <a name="hierarchy-types"></a>Typy hierarchii

Poniższa tabela pokazuje dostępne hierarchie typów kategorii oraz ich ogólne zastosowania.

| Typ hierarchii kategorii       | Cel |
|-------------------------------|---------|
| Hierarchia produktów      | Ten typ kategorii pozwala zdefiniować ogólną hierarchę produktów dla Twojej organizacji. Ten typ hierarchii sprawdza się w merchandisingu, wycenach i promocjach, raportowaniu i planowaniu asortymentu. Z tym typem hierarchii można skojarzyć tylko jedną hierarchię produktu. |
| Uzupełniająca hierarchia | Ten typ hierarchii pozwala tworzyć wszelkie dodatkowe hierarchie kategorii. Załóżmy na przykład, że na wiosnę chcesz promować stroje kąpielowe. W związku z tym umieszczasz produkty związane ze strojem kąpielowym w hierarchii kategorii i stosujesz cennik promocyjny w różnych kategoriach produktów. |
| Hierarchia nawigacji   | Za pomocą tego typu hierarchii można grupować i organizować produkty według kategorii, tak aby dało się przeglądać produkty online lub w punkcie sprzedaży. |

Za pomocą hierarchii kategorii można porządkować produkty, skonfigurować ich atrybuty oraz właściwości na poziomie kategorii. Te atrybuty i właściwości obejmują ustawienia dla wymiarów produktu i ustawienia punktu sprzedaży. Wszystkie produkty, które zostaną przypisane do kategorii, automatycznie dziedziczą atrybuty i właściwości zdefiniowane przez użytkownika. Można także jednocześnie skopiować ustawienia właściwości w odniesieniu do produktu do wielu produktów z wybranej kategorii.
