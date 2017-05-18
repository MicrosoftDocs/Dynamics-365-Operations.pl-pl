---
title: "Wpisy kosztów"
description: "Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone. Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 341251119304456a89b02c7a8d4af941ea21196d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="cost-entries"></a>Wpisy kosztów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone. Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia.

Wpisy kosztów są agregacjami dla transakcji magazynowych, które są rejestrowane w aktywnych wymiarach magazynu finansowego.

## <a name="examples"></a>Przykłady
### <a name="example-1-no-cost-entries-are-created"></a>Przykład 1: Nie są tworzone żadne wpisy kosztów

Rejestrowane jest zdarzenie arkusza przeniesienia. Zdarzenie przenosi jedną sztukę towaru A z lokalizacji A do lokalizacji B. Wymiar magazynowy Lokalizacja nie jest traktowany jako część obiektu kosztu. Z tego względu zdarzenie tworzy dwie transakcje magazynowe i żadnych wpisów kosztów.

### <a name="example-2-cost-entries-are-created"></a>Przykład 2: Wpisy kosztów są tworzone

Rejestrowane jest zdarzenie arkusza przeniesienia. Zdarzenie przenosi jedną sztukę towaru A z oddziału 1 do oddziału 2. Wymiar magazynowy Oddział jest traktowany jako część obiektu kosztu. Z tego względu zdarzenie tworzy dwie transakcje magazynowe i dwa wpisy kosztów.

### <a name="example-3-one-cost-entry-is-created"></a>Przykład 3: Tworzony jest jeden wpis kosztów

Zdarzenie przyjęcia produktów jest rejestrowane w zamówieniu zakupu. Zdarzenia rejestruje 100 sztuk towaru A z kosztem jednostkowym 10,00 USD. Ponieważ towar A używa numeru seryjnego do śledzenia celu zarządzania magazynem, tworzony jest unikatowy numer seryjny dla każdego przyjętego towaru. Z tego względu zdarzenie tworzy 100 transakcji magazynowych i jeden wpisz kosztu.

## <a name="cost-entries-page"></a>Strona Wpisy kosztów
Nowa strona **Wpisy kosztów** umożliwia przeglądanie i kontrolowanie rejestracji kosztów i ilości. Ta strona stanowi uzupełnienie stron **Transakcje magazynowe** i **Rozliczenia zapasów**. Rekordy są rejestrowane w porządku chronologicznym dla zdarzenia. W związku z tym można szybko znajdować i kontrolować zakumulowane koszty określonego zdarzenia lub wszystkie zdarzenia, które są powiązane z dokumentem. Oto przykład:

-   Zdarzenie przyjęcia produktów jest rejestrowane dla towaru A. Przyjmowanych jest 100 sztuk z kosztem jednostkowym 10,00 USD.
-   Kilka dni po zarejestrowaniu zdarzenia faktury, koszt wzrasta do 11,00 USD. Dlatego łączna suma wynosi 1100 USD. Tworzony jest drugi załącznik, aby uwzględnić różnicę 100 USD.
-   Kilka dni później opłata dodatkowa w wysokości 15,00 USD na pokrycie kosztów transportu jest rejestrowana na zamówieniu zakupu.

| Załącznik | Data       | Odwołanie      | Identyfikator | Identyfikator partii  | Ilość | Ilość  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | Zamówienie zakupu | 100001 | 0000101 | 100,00   | 1000.00 |
| 00002   | 20-01-2015 | Zamówienie zakupu | 100001 | 0000101 |          | 100,00  |
| 00003   | 31-01-2015 | Korekta     | 100001 | 0000101 |          | 15,00   |

Strona **Wpisy kosztu** umożliwia filtrowanie według identyfikatora dokumentu i daty dokumentu. 

> [!NOTE]
> Wpisy kosztów są dostępne tylko dla [obiektów kosztów](cost-object.md) lub zwolnionych produktów.

<a name="see-also"></a>Informacje dodatkowe
--------

[Obiekty kosztów](cost-object.md)




