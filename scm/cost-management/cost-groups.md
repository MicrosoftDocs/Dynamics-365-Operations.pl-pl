---
title: "Grupy kosztów"
description: "Grupy kosztów są podstawą podczas segmentowania i analizowania udziałów kosztów w obliczonym koszcie wyprodukowanego towaru, takich jak koszt materiału bądź robocizny czy narzuty. Segmentacja grup kosztów jest nazywana w środowiskach produkcyjnych także podziałem kosztów, dekompozycją kosztów lub klasyfikacją kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3592f3c076681c5b755b62383212bbe6d158f62d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="cost-groups"></a>Grupy kosztów

[!include[banner](../includes/banner.md)]


Grupy kosztów są podstawą podczas segmentowania i analizowania udziałów kosztów w obliczonym koszcie wyprodukowanego towaru, takich jak koszt materiału bądź robocizny czy narzuty. Segmentacja grup kosztów jest nazywana w środowiskach produkcyjnych także podziałem kosztów, dekompozycją kosztów lub klasyfikacją kosztów. 

Segmentacja grup kosztów jest nazywana w środowiskach produkcyjnych także podziałem kosztów, dekompozycją kosztów lub klasyfikacją kosztów. Segmentacja grup kosztów może służyć do następujących celów. Oto kilka przykładów:

-   Segmentowanie kosztów materiałów różnych typów, takich jak składniki i materiały opakowań służące do produkcji konserw na podstawie grup kosztów przypisanych do towarów.
-   Segmentowanie kosztów zasobów operacyjnych różnych typów, takich jak różne typy robocizny czy maszyn na podstawie grup kosztów przypisanych do kategorii kosztów związanych z zasobami operacyjnymi i operacjami marszruty.
-   Segmentowanie kosztów na potrzeby przezbrajania i produkcji w marszrutach na podstawie grup kosztów przypisanych do kategorii kosztów związanych z marszrutami.
-   Segmentowanie kosztów dla narzutów różnych typów, takich jak narzuty związane z robocizną czy maszynami na podstawie grup kosztów przypisanych do kosztów pośrednich w konfiguracji arkusza wyceny.
-   Stanowią podstawę do obliczania różnych narzutów produkcyjnych w konfiguracji arkusza wyceny. To może obejmować różne narzuty związane z informacjami marszrut o zasobach operacyjnych lub o konfiguracji i czasie procesu. Narzuty produkcyjne mogą być także związane z udziałami kosztów surowców, odzwierciedlając filozofię odchudzonej produkcji (lean manufacturing) eliminującej zapotrzebowanie na informacje na temat marszruty.

Segmentacja grup kosztów dotyczy obliczonego kosztu wyprodukowanego towaru niezależnie od tego, czy koszt był oparty na kosztach standardowych, czy planowanych. Strona **Podsumowanie** wyświetlana tę segmentację według grupy kosztów, poziomu lub grupę kosztów i poziomu jednocześnie. 

Możliwość zarządzania segmentacją grup kosztów na wielu poziomach struktury produktu jest nazywana *podziałem*. Podział dotyczy tylko produkowanych towarów, które używają modelu magazynu z kosztem standardowym. Jeśli podział nie jest używany, koszt przetwarzanego składnika jest traktowany jako udział kosztów materiału. Parametr zapasów dla podziału kosztów według księgi podrzędnej wskazuje, że segmentacja grup kosztów zostanie zachowana na wielu poziomach w rachunku kosztów standardowych. Jeśli natomiast zasada nie ma poziomów, segmentacja grupy kosztów dotyczy tylko obliczeń dla jednego poziomu. Na przykład strona **Akumulacja kosztów według grupy kosztów** wyświetla segmentację grupy kosztów na wielu poziomach dla składników kosztów standardowych. 

Segmentacja grup kosztów dotyczy także odchyleń kosztów standardowych. Drugi parametr zapasów określa, czy odchylenia będą określane według grupy kosztów, czy po prostu zostaną podsumowane. 

Do grupy kosztów można przypisać typ grupy kosztów oraz działanie służące do celów segmentacji uzupełniającej.

-   **Typ grupy kosztów** — do każdej grupy kosztów należy przypisać typ grupy kosztów, który określa grupę kosztów jako odnoszącą się do materiałów bezpośrednich, produkcji bezpośredniej lub bezpośredniego outsourcingu albo w celu oznaczenia jej jako koszt pośredni lub niezdefiniowany. Grupę kosztów określona jako materiały bezpośrednie można przypisać do towarów. Grupę kosztów produkcji bezpośredniej można przypisać do kategorii kosztów. Grupa kosztów outsourcingu bezpośredniego może być przypisana do typu produktu usługi, która służy do klasyfikowania kosztów związanych z zakupem usługi do działań podwykonawstwa. Grupę kosztów pośrednich można przypisać do kosztów pośrednich dla dopłat i stawek. Grupę kosztów określoną jako niezdefiniowaną można przypisać do towarów, kategorii kosztów lub kosztów pośrednich. Przypisanie typu grupy kosztów służy kilku celom. Po pierwsze ogranicza możliwość przypisywania grupy kosztów i wyświetlania listy mających zastosowanie grup kosztów. Po drugie zapewnia uzupełniającą segmentację na potrzeby sprawozdawczości. Po trzecie może służyć do przypisywania kont księgowych dla zmian.
-   **Działanie** — każdej grupie kosztów można opcjonalnie przypisać działanie, które określa grupę kosztów jako odnoszącą się do kosztów stałych lub zmiennych. Grupa kosztów, która ma wartość NULL dla działania, jest traktowana jako koszt zmienny. Przypisanie działania służy wyłącznie do tworzenia raportów. Na przykład koszty mogą być wyświetlane z podziałem na koszty stałe i zmienne w arkuszu wyceny oraz na stronie **Akumulacja kosztów według grupy kosztów**. Jeśli przypiszesz wartość procentową ustawień zysku do każdej grupy kosztów, obliczanie listy składowej (BOM) poda sugerowaną cenę sprzedaży na podstawie wzoru „koszt plus narzut”.





