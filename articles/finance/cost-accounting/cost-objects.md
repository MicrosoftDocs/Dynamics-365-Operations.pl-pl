---
title: Wymiary obiektów kosztów
description: Podczas analizowania kosztów wymiary składników kosztów służą do ustalania, gdzie płyną koszty. Wymiary obiektów kosztów są używane do określenia, gdzie należy przypisać koszty. Ten temat zawiera informacje o wymiarach obiektów kosztów.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6c15402993568c53eda8e03351fc2fccbcd82ab8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770834"
---
# <a name="cost-object-dimensions"></a>Wymiary obiektów kosztów

[!include [banner](../includes/banner.md)]

Podczas analizowania kosztów wymiary składników kosztów służą do ustalania, gdzie płyną koszty. Wymiary obiektów kosztów są używane do określenia, gdzie należy przypisać koszty. Ten temat zawiera informacje o wymiarach obiektów kosztów.

Obiektem kosztów może być dowolny typu obiektu, który chcesz oszacować, przydzielić mu koszty lub bezpośrednio zmierzyć. Typowymi obiektami kosztów są produkty, projekty, zasoby, działy, centra kosztów i regiony geograficzne. Kierownictwo używa obiektów kosztów do mierzenia kosztów, ale także do analizy rentowności.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Wymiary obiektów kosztów i elementy członkowskie wymiarów obiektów kosztów
Obiekty kosztów są nazywane *wymiarami obiektów kosztów*. Po ustaleniu, do której jednostki powinien się odnosić wymiar obiektów kosztów, należy określić wartości poszczególnych wymiarów lub zaimportować je do modułu Rachunek kosztów z innych systemów źródłowych. Te wartości poszczególnych wymiarów są nazywane *elementami członkowskimi wymiarów obiektów kosztów*. Na przykład jako wymiaru obiektów kosztów chcesz użyć wymiaru finansowego o nazwie Centrum kosztu. Aby zobaczyć, jak koszty przepływają do poszczególnych centrów kosztów, należy zaimportować elementy członkowskie wymiaru obiektów kosztów. W tym przypadku elementy członkowskie wymiaru obiektów kosztów są rzeczywistymi centrami kosztów, takimi jak Sprzedaż, Produkcja, Administracja i Lokalizacje geograficzne. Poniższy zrzut ekranu przedstawia przykład centrów kosztów jako wymiaru obiektów kosztów, gdzie faktyczne centra kosztów są elementami członkowskimi wymiaru obiektów kosztów. 

[![Zrzut ekranu przedstawiający centra kosztów jako wymiar obiektu kosztów](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importowanie elementów członkowskich wymiarów obiektów kosztów za pośrednictwem łączników danych
Aby ułatwić sobie importowania elementów członkowskich wymiarów obiektów kosztów, można za pomocą łączników danych pobierać wartości z jednostek, które mają zostać użyte jako wymiary obiektów kosztów. Można używać łączników danych wbudowanych w systemie lub łączników niestandardowych, utworzonych przez siebie.



