---
title: Planowanie tras przewozu frachtu z przystankami
description: "W tym artykule opisano różne elementy używane do planowania tras transportu w programie Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: e7965c094f91bcbcad21ecfa599f133a6e84f4f7
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Planowanie tras przewozu frachtu z przystankami
<a id="plan-freight-transportation-routes-with-multiple-stops" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano różne elementy używane do planowania tras transportu w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

Dla złożonych tras transportowych, które mają przystanki po drodze, można używać planów tras i przewodników po trasach. Jeśli ta sama trasa będzie stosowana w sposób regularny, można skonfigurować trasę z harmonogramem.

## Plany marszrut
<a id="route-plans" class="xliff"></a>
Plan trasy zawiera segmenty trasy, które dostarczają informacji o przystankach na trasie i o przewoźnikach wykorzystywanych w każdym segmencie. Postoje na trasie należy zdefiniować jako centra. Rolę centrum może pełnić dostawca, magazyn, odbiorca albo nawet miejsce przeładunku, gdzie zmieniasz przewoźnika. Dla każdego segmentu można zdefiniować „kursy kasowe” dla różnych opłat. Oto kilka przykładów:

-   Opłaty za dotarcie do wybranych segmentów
-   Opłaty za odbiór towarów
-   Opłaty za dostawę towarów

Każdy plan trasy musi być skojarzony z przewodnikiem po trasie.

## Przewodniki po marszrutach
<a id="route-guides" class="xliff"></a>
Przewodnik po trasie definiuje kryteria dopasowywania ładunku do określonego planu trasy. Na przykład można określić centrum źródłowe i centrum przeznaczenia, ograniczyć objętość lub masę kontenera oraz wskazać i przewoźnika, usługę lub grupę. Przewodniki po trasach są dostępne na stronie **Pulpit ustalania stawek i wyznaczania tras**, gdzie ładunki można dopasowywać do tras ręcznie lub automatycznie. Jeśli przewodnik po zadaniach dotyczy trasy z harmonogramem, jest on również dostępny na stronie **Pulpit kompilowania ładunku**.

## Zaplanowane marszruty
<a id="scheduled-routes" class="xliff"></a>
Trasa z harmonogramem to wstępnie zdefiniowany plan trasy, który ma harmonogram dat dostaw. Trasy z harmonogramem i bez harmonogramu różnią się sposobem przypisywania do nich ładunków. Jeśli przypiszesz trasę bez harmonogramu przy użyciu pulpitu ustalania stawek i wyznaczania tras, weryfikacja obejmie tylko ładunek i przewodnik po trasie. Jeśli przypiszesz trasę z harmonogramem, będą również uwzględniane daty i adresy z zamówień i centrum oraz data z planu trasy. Nie trzeba używać strony Pulpit ustalania stawek i wyznaczania tras, aby ręcznie przypisać ładunki do trasy z harmonogramem. Zamiast tego można użyć strony Pulpit kompilowania ładunku i wskazać, że dla danej trasy z harmonogramem ładunki mają być kompilowane na podstawie adresów odbiorców i dat dostaw z zamówień sprzedaży. W przypadku tras z harmonogramem plan trasy będzie miał stałe centra źródłowe i przeznaczenia. Zazwyczaj przewoźnik i usługą będą takie same we wszystkich segmentach, ale mogą się różnić. Centra przeznaczenia są tworzone przy użyciu kodów pocztowych odbiorców odwiedzanych na trasie. Dla jednego planu trasy można zdefiniować kilka harmonogramów trasy. Plan trasy musi być skojarzony z przewodnikiem po trasie. Jednakże dla tras z harmonogramami plan można skojarzyć tylko z jednym przewodnikiem po trasie. Harmonogram trasy jest używany tylko do tworzenia rzeczywistych tras na stronie **Harmonogram trasy**. Do proponowania ładunków na stronie Pulpit kompilowania ładunku można użyć domyślnego szablonu ładunku.

## Pulpit kompilowania ładunku
<a id="load-building-workbench" class="xliff"></a>
Do proponowania ładunków Pulpit kompilowania ładunku używa adresów odbiorców i dat dostaw z zamówień sprzedaży oraz dostępnych tras z harmonogramami. Domyślnie w pulpicie są wprowadzane wartości z trasy. Można jednak wybrać datę „od” wcześniejszą niż data „od” na trasie. Podczas proponowania ładunku są sprawdzane adres dostawy i data dostawy we wszystkich otwartych zamówieniach sprzedaży. Jeśli kod pocztowy adresu dostawy jest zgodny z kodem pocztowym centrum w planie trasy, a data dostawy mieści się w zakresie wybranym w kryteriach, zamówienie sprzedaży jest proponowane dla dostawy. Jest także uwzględniana pojemność określona w szablonie ładunku. Proponowany jest tylko jeden ładunek na raz. Jeśli masz zamówienie sprzedaży, które nie zostało uwzględnione, może być konieczne użycie innego szablonu ładunku (na przykład szablonu dla większej ciężarówki lub kontenera) albo zaplanowanie dodatkowej dostawy.




