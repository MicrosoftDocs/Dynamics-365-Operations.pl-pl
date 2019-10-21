---
title: Hierarchie sieci sprzedaży
description: Ten artykuł opisuje hierarchie sieci sprzedaży w programie Dynamics 365 Retail.
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
ms.openlocfilehash: cb383c5bc5ad5d641db6f30e915ea43ba5980005
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025084"
---
# <a name="retail-hierarchies"></a>Hierarchie sieci sprzedaży

[!include [banner](includes/banner.md)]

Ten artykuł opisuje hierarchie sieci sprzedaży w programie Dynamics 365 Retail.

Można skonfigurować hierarchię kategorii w sieci sprzedaży w celu zorganizowania produktów sprzedawanych w Twoim kanale sprzedaży. Hierarchie produktów sieci sprzedaży umożliwiają łączenie produktów w kategorie i grupy. Następnie można używać tych produktów do tworzenia asortymentów produktów i programów lojalnościowych. Można również przypisywać właściwości i atrybuty produktu, strukturę cen, dodawać produkty w do produktów i używać produktów na potrzeby raportowania. Można utworzyć jedną hierarchię kategorii sieci sprzedaży do reprezentowania wszystkich produktów i kategorii w organizacji, a następnie użyć tej hierarchii kategorii do wielu celów. Alternatywnie można utworzyć wiele hierarchii kategorii sieci sprzedaży do celów specjalnych, takich jak promocja produktów. Podczas tworzenia hierarchii produktów detalicznych należy przypisać typ hierarchii kategorii w celu identyfikacji przeznaczenia hierarchii kategorii. Na przykład tylko hierarchie produktów, które mają przypisany typ **Hierarchia nawigacji w sieci sprzedaży**, są wskazywane podczas przeglądania produktów według kategorii online lub w punkcie sprzedaży.

## <a name="retail-hierarchy-types"></a>Typy hierarchii w sieci sprzedaży

Poniższa tabela pokazuje dostępne hierarchie typów kategorii w sieci sprzedaży oraz ich ogólne zastosowania.

| Typ hierarchii kategorii       | Cel |
|-------------------------------|---------|
| Hierarchia produktów sieci sprzedaży      | Ten typ kategorii pozwala zdefiniować ogólną hierarchę produktów dla Twojej organizacji. Ten typ hierarchii sprawdza się w merchandisingu, wycenach i promocjach, raportowaniu i planowaniu asortymentu. Z tym typem hierarchii można skojarzyć tylko jedną hierarchię produktu w sieci sprzedaży. |
| Uzupełniająca hierarchia produktów | Ten typ hierarchii pozwala tworzyć wszelkie dodatkowe hierarchie kategorii w sieci sprzedaży. Załóżmy na przykład, że na wiosnę chcesz promować stroje kąpielowe. W związku z tym umieszczasz produkty związane ze strojem kąpielowym w hierarchii kategorii i stosujesz cennik promocyjny w różnych kategoriach produktów. |
| Hierarchia nawigacji sprzedaży   | Za pomocą tego typu hierarchii można grupować i organizować produkty według kategorii, tak aby dało się przeglądać produkty online lub w punkcie sprzedaży. |

Za pomocą hierarchii kategorii w sieci sprzedaży można porządkować produkty, skonfigurować ich atrybuty oraz właściwości na poziomie kategorii. Te atrybuty i właściwości obejmują ustawienia dla wymiarów produktu i ustawienia punktu sprzedaży. Wszystkie produkty, które zostaną przypisane do kategorii, automatycznie dziedziczą atrybuty i właściwości zdefiniowane przez użytkownika. Można także jednocześnie skopiować ustawienia właściwości w odniesieniu do produktu do wielu produktów z wybranej kategorii.
