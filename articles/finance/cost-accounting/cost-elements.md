---
title: Wymiary składników kosztów
description: Wymiary składników kosztów są jednym z filarów rachunku kosztów. Służą do kategoryzowania i śledzenia, dokąd płyną koszty.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e67ce047d08af6d34090ee4e1dc379dd16ecce07
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446892"
---
# <a name="cost-element-dimensions"></a>Wymiary składników kosztów

[!include [banner](../includes/banner.md)]

Wymiary składników kosztów są jednym z filarów rachunku kosztów. Służą do kategoryzowania i śledzenia, dokąd płyną koszty. 

Składnik kosztu odnosi się do elementu istotnego dla kosztów w planie kont. Zasadniczo może to być element dowolnego typu na najniższym poziomie w przedsiębiorstwie, dokąd mogą płynąć koszty. Pod względem koncepcyjnym składnikami kosztów mogą być tak różne elementy, jak konta księgowe i wszystkie zasoby związane z kosztami. Obecnie moduł Rachunek kosztów obsługuje konta księgowe.

## <a name="two-types-of-cost-elements"></a>Dwa rodzaje składników kosztów
Istnieją dwa typy składników kosztów: podstawowe i podrzędne. W poniższej tabeli opisano różnice między tymi typami.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Podstawowe składniki kosztów</strong></td>
<td><strong>Podrzędne składniki kosztów</strong></td>
</tr>
<tr class="even">
<td>Podstawowe składniki kosztów reprezentują przepływów kosztów z księgowości finansowej do rachunku kosztów. Struktura składników kosztów odpowiada strukturze konta wynikowego w księdze głównej, gdzie składnik kosztu może odpowiadać kontu głównemu. Nie wszystkie konta główne muszą być reprezentowane jako składniki kosztów. Zależy to od potrzeb biznesowych. Przykłady podstawowych składników kosztów:
<ul>
<li>Koszt własny sprzedaży (COG)</li>
<li>Koszty pośrednie materiału</li>
<li>Koszty pracownicze</li>
<li>Koszty energii</li>
</ul></td>
<td>Podrzędne składniki kosztów reprezentują wewnętrzny przepływ kosztów, ponieważ koszty te są tworzone i wykorzystywane tylko w rachunku kosztów. Służą one zapewnieniu możliwości śledzenia źródła kosztów. Te składniki kosztów są używane w alokacji kosztów i obliczeniach kosztów ogólnych. Przykłady podrzędnych składników kosztów:
<ul>
<li>Koszty produkcji</li>
<li>Koszty ogólne produkcji, materiałów i marketingu</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Wymiary składników kosztów i elementy członkowskie wymiarów składników kosztów
Składniki kosztów są określane jako *wymiary składników kosztów* . Wartości poszczególnych wymiarów są nazywane *elementami członkowskimi wymiarów składników kosztów*. Na przykład masz strukturę amerykańskiego planu kont (COA), która jest podstawą do sprawozdawczości ustawowej. Ten plan kont służy jako wymiar składników kosztów. Konta, czyli podstawowe składniki kosztów, są przedstawiane jako elementy członkowskie wymiaru składników kosztów w rachunku kosztów. Poniższy zrzut ekranu przedstawia przykład kont głównych jako wymiaru składników kosztów, gdzie faktyczne konta główne są elementami członkowskimi wymiaru składników kosztów. 

[![Zrzut ekranu kont głównych jako wymiar elementu kosztu](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Importowanie elementów członkowskich wymiarów składników kosztów za pośrednictwem łączników danych
Aby ułatwić sobie konfigurowanie elementów członkowskich wymiarów składników kosztów w module Rachunek kosztów, można używać łączników danych wbudowanych w systemie lub utworzonych samodzielnie do podstawowych składników kosztów z jednego lub więcej systemów źródłowych.

## <a name="implementation-considerations"></a>Uwagi dotyczące implementacji
Składniki kosztów reprezentują najniższy poziom szczegółów kosztów, dlatego podczas implementowania struktury składników kosztów należy się upewnić, że są uwzględnione wszystkie składniki kosztów wymagane w sprawozdawczości dla kierownictwa. Może być trudne znalezienie odpowiedniej liczby składników kosztów na potrzeby kontroli kosztów. Posiadanie tysięcy składników kosztów może utrudnić kontrolowanie ich wszystkich. Dlatego alternatywnie można grupować składniki kosztów i zarządzać kontrolą kosztów na poziomie zbiorczym.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]