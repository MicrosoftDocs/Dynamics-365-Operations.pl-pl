---
title: "Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system"
description: "Ten artykuł wyjaśnia dwa rodzaje ograniczeń tabel dla składników w modelu konfiguracji produktu — zdefiniowane przez użytkownika i zdefiniowane przez system. Ograniczenia tabel reprezentują macierze dozwolonych kombinacji atrybutów, gdzie każdy wiersz definiuje jeden zestaw możliwych wartości atrybutów."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4b1d70a446bb4255375a36393778fe2ee6d6fa4e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a>Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system

[!include[banner](../includes/banner.md)]


Ten artykuł wyjaśnia dwa rodzaje ograniczeń tabel dla składników w modelu konfiguracji produktu — zdefiniowane przez użytkownika i zdefiniowane przez system. Ograniczenia tabel reprezentują macierze dozwolonych kombinacji atrybutów, gdzie każdy wiersz definiuje jeden zestaw możliwych wartości atrybutów.

Powiązane tabele przedstawiają macierze kombinacji atrybutów, które są dozwolone dla składników w modelu konfiguracji produktu. Każdy wiersz w tabeli definiuje jeden zestaw atrybutów możliwych wartości. Można zadeklarować dwa typy ograniczeń w modelu konfiguracji produktu:

-   **Ograniczenia wyrażenia** — można utworzyć wyrażenie, które określa relacje między atrybutami, aby zagwarantować, że podczas konfigurowania produktu mogą być wybrane tylko zgodne wartości.
-   **Powiązane tabele** — można utworzyć tabelę, która określa wszystkie kombinacje, które są dozwolone dla określonego zestawu atrybutów. Dostępne są dwa typy powiązanych tabel: zdefiniowane przez użytkownika i zdefiniowane przez system.

Ten artykuł opisuje powiązane tabeli zdefiniowane przez użytkownika i przez system dla składników w modeli konfiguracji produktu.

## <a name="user-defined-table-constraints"></a>Powiązane tabele zdefiniowane przez użytkownika
Powiązane tabele zdefiniowane przez użytkownika to typ macierzy używany do opisywania kombinacji dla wartości atrybutów, które są zdefiniowane przez typy atrybutu. Na przykład jeśli produkujesz głośniki, możesz w powiązanych tabelach zdefiniowanych przez użytkownika możesz umieścić kolumny dla wykończenia i maskownicy. Typ atrybutu dla wykończenia ma cztery wartości a typ atrybutu dla maskownicy ma trzy możliwe wartości. Z tego powodu, jeśli ograniczenia nie są używane, jest 4 x 3 = 12 możliwych kombinacji. Jednak w tym przykładzie tylko sześć kombinacji jest dozwolonych, jak pokazano w poniższej tabeli. Te informacje są wyświetlane na karcie **Dozwolone kombinacje** na stronie **Edycja powiązanych tabel**.

| Wykończenie | Maskownica |
|----------------|-------------|
| Czarny          | Czarny       |
| Czarny          | Metal       |
| Dąb            | Czarny       |
| Rosewood       | Biały       |
| Biały          | Czarny       |
| Biały          | Biały       |

Powiązane tabele zdefiniowane przez użytkownika są definiowane przez statyczne danych wejściowych tabeli, co działa tak samo jak w przypadku ograniczenia wyrażenia. Jeśli używasz powiązanej tabeli zdefiniowanej przez użytkownika, ma to tę zaletę, że tabele są często tworzenie, analiza i obsługa tabel jest często łatwiejsza niż długich ograniczenia wyrażeń.

## <a name="system-defined-table-constraints"></a>Powiązane tabele zdefiniowanych przez system
Powiązane tabele zdefiniowane przez system tworzą dynamiczne mapowanie między typem atrybutem i polem w tabeli. Gdy powiązana tabela zdefiniowana przez system jest uwzględniana w modelu konfiguracji produktu, mapowanie gwarantuje, że dane w tabeli są wyświetlane zamiast wartości typu atrybutu. Wynikiem jest ograniczenie dynamiczne, ponieważ powiązane tabele mogą być modyfikowane (np. przez inne moduły).  

Podczas tworzenia powiązanych tabel zdefiniowanych przez system wybiera się tabelę, opcjonalnie definiuje się kwerendę do użycia, a następnie kojarzy się typy atrybutów z polami w wybranej tabeli. Typy pól muszą pasować do typów atrybutów.  

Zanim ograniczenie tabeli będzie mogło zacząć obowiązywać w modelu konfiguracji produktu, należy je dodać do ograniczenia jednego ze składników modelu. Procedura obejmuje utworzenie nowego ograniczenia, wybranie typu ograniczenia tabeli, a następnie wybranie definicji ograniczenia tabeli, która ma być używana. Ponadto wszystkie pola w powiązanych tabelach muszą być mapowane do atrybutów w modelu konfiguracji produktu.

<a name="see-also"></a>Informacje dodatkowe
--------

[Podstawowe pojęcia dotyczące modeli konfiguracji produktów](product-configuration-models.md)




