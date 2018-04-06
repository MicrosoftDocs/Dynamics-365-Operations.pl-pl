---
title: Planowanie tras przewozu frachtu z przystankami
description: "W tym artykule opisano różne elementy używane do planowania tras transportu w programie Dynamics 365 for Finance and Operations."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 16255e812773ed35c0e34ec26a8a689ea09632bd
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Planowanie tras przewozu frachtu z przystankami

[!include[banner](../includes/banner.md)]


W tym artykule opisano różne elementy używane do planowania tras transportu w programie Microsoft Dynamics 365 for Finance and Operations.

Dla złożonych tras transportowych, które mają przystanki po drodze, można używać planów tras i przewodników po trasach. Jeśli ta sama trasa będzie stosowana w sposób regularny, można skonfigurować trasę z harmonogramem.

## <a name="route-plans"></a>Plany marszrut
Plan trasy zawiera segmenty trasy, które dostarczają informacji o przystankach na trasie i o przewoźnikach wykorzystywanych w każdym segmencie. Postoje na trasie należy zdefiniować jako centra. Rolę centrum może pełnić dostawca, magazyn, odbiorca albo nawet miejsce przeładunku, gdzie zmieniasz przewoźnika. Dla każdego segmentu można zdefiniować „kursy kasowe” dla różnych opłat. Oto kilka przykładów:

-   Opłaty za dotarcie do wybranych segmentów
-   Opłaty za odbiór towarów
-   Opłaty za dostawę towarów

Każdy plan trasy musi być skojarzony z przewodnikiem po trasie.

## <a name="route-guides"></a>Przewodniki po marszrutach
Przewodnik po trasie definiuje kryteria dopasowywania ładunku do określonego planu trasy. Na przykład można określić centrum źródłowe i centrum przeznaczenia, ograniczyć objętość lub masę kontenera oraz wskazać i przewoźnika, usługę lub grupę. Przewodniki po trasach są dostępne na stronie **Pulpit ustalania stawek i wyznaczania tras**, gdzie ładunki można dopasowywać do tras ręcznie lub automatycznie. Jeśli przewodnik po zadaniach dotyczy trasy z harmonogramem, jest on również dostępny na stronie **Pulpit kompilowania ładunku**.

## <a name="scheduled-routes"></a>Zaplanowane marszruty
Trasa z harmonogramem to wstępnie zdefiniowany plan trasy, który ma harmonogram dat dostaw. Trasy z harmonogramem i bez harmonogramu różnią się sposobem przypisywania do nich ładunków. Jeśli przypiszesz trasę bez harmonogramu przy użyciu pulpitu ustalania stawek i wyznaczania tras, weryfikacja obejmie tylko ładunek i przewodnik po trasie. Jeśli przypiszesz trasę z harmonogramem, będą również uwzględniane daty i adresy z zamówień i centrum oraz data z planu trasy. Nie trzeba używać strony Pulpit ustalania stawek i wyznaczania tras, aby ręcznie przypisać ładunki do trasy z harmonogramem. Zamiast tego można użyć strony Pulpit kompilowania ładunku i wskazać, że dla danej trasy z harmonogramem ładunki mają być kompilowane na podstawie adresów odbiorców i dat dostaw z zamówień sprzedaży. W przypadku tras z harmonogramem plan trasy będzie miał stałe centra źródłowe i przeznaczenia. Zazwyczaj przewoźnik i usługą będą takie same we wszystkich segmentach, ale mogą się różnić. Centra przeznaczenia są tworzone przy użyciu kodów pocztowych odbiorców odwiedzanych na trasie. Dla jednego planu trasy można zdefiniować kilka harmonogramów trasy. Plan trasy musi być skojarzony z przewodnikiem po trasie. Jednakże dla tras z harmonogramami plan można skojarzyć tylko z jednym przewodnikiem po trasie. Harmonogram trasy jest używany tylko do tworzenia rzeczywistych tras na stronie **Harmonogram trasy**. Do proponowania ładunków na stronie Pulpit kompilowania ładunku można użyć domyślnego szablonu ładunku.

## <a name="load-building-workbench"></a>Pulpit kompilowania ładunku
Do proponowania ładunków Pulpit kompilowania ładunku używa adresów odbiorców i dat dostaw z zamówień sprzedaży oraz dostępnych tras z harmonogramami. Domyślnie w pulpicie są wprowadzane wartości z trasy. Można jednak wybrać datę „od” wcześniejszą niż data „od” na trasie. Podczas proponowania ładunku są sprawdzane adres dostawy i data dostawy we wszystkich otwartych zamówieniach sprzedaży. Jeśli kod pocztowy adresu dostawy jest zgodny z kodem pocztowym centrum w planie trasy, a data dostawy mieści się w zakresie wybranym w kryteriach, zamówienie sprzedaży jest proponowane dla dostawy. Jest także uwzględniana pojemność określona w szablonie ładunku. Proponowany jest tylko jeden ładunek na raz. Jeśli masz zamówienie sprzedaży, które nie zostało uwzględnione, może być konieczne użycie innego szablonu ładunku (na przykład szablonu dla większej ciężarówki lub kontenera) albo zaplanowanie dodatkowej dostawy.




