---
title: Modelowanie organizacji oszczędnej
description: Ten artykuł zawiera informacje o podstawowych pojęciach używanych w modelowaniu organizacji stosującej produkcję oszczędną.
author: cvocph
manager: tfehr
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33e734aef938c7b58d5c936f6eae32e4f0ab3ba7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211452"
---
# <a name="modeling-a-lean-organization"></a>Modelowanie organizacji oszczędnej

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o podstawowych pojęciach używanych w modelowaniu organizacji stosującej produkcję oszczędną. 

Zazwyczaj scenariusz produkcji oszczędnej to więcej niż tylko zbiór niezwiązanych ze sobą reguł Kanban czy zasad dotyczących dostaw materiałów. Przepływ materiałów i produktów we wszystkich komórkach roboczych i lokalizacjach pracy dla określonego scenariusza produkcji lub dostawy można opisać jako sekwencję lub małą sieć działań przetwarzania lub przenoszenia. Ta sekwencja/sieć nosi nazwę „przepływu produkcji”.

## <a name="production-flows-in-lean-manufacturing"></a>Przepływy produkcji w produkcji oszczędnej
W scenariuszach produkcyjnych opartych na zleceniach produkcyjnych materiały są wydawane względem określonego zlecenia produkcyjnego. Podczas wykonywania sekwencji operacji opartej o listy składowe (BOM) i marszruty produkty są tworzone i na końcu przyjmowane w podanej lokalizacji. Czas realizacji zleceń produkcyjnych waha się od kilku minut do kilku tygodni. Wszystkie powiązane koszty, materiały i robocizna są akumulowane w zleceniu produkcyjnym. 

Aby zminimalizować czasy realizacji dostaw i ryzyko wystąpienia nadwyżek zapasów między gniazdami produkcyjnymi, co następuje przy produkcji wsadowej, scenariusz produkcji oszczędnej wprowadza funkcje uzupełniania zapasów Kanban i supermarketów w obszarach produkcji i uzupełniania zapasów w magazynie. Zazwyczaj te funkcje zakłócają produkcję w częściowo niezależnych cyklach Kanban. Uzupełnianie zapasów Kanban dla półproduktów nie jest już inicjowane przez zamówienie na gotowy produkt. 

Aby ponownie umożliwić kontekst produkcji i kosztów w różnych proponowanych scenariuszach Kanban, wprowadzono przepływy produkcji oparte na działaniach jako podstawę dla produkcji oszczędnej. Wszystkie reguły Kanban odnoszą się do tej wstępnie zdefiniowanej struktury. Model oparty na działaniach umożliwia konfigurowanie różnorodnych scenariuszy. Jednak nie zwiększa on poziomu komplikacji dla pracowników na produkcji, ponieważ wszystkie scenariusze używają tego samego interfejsu użytkownika opartego na działania.

## <a name="semi-finished-products-non-bom-levels"></a>Półprodukty (bez poziomów BOM)
Moduł Lean Manufacturing integruje w jednej strukturze karty Kanban dla produktów i półproduktów umieszczanych w zapasach, oferując w ten sposób ujednolicone środowisko obsługi we wszystkich przypadkach. Dzięki tej architekturze nie trzeba wprowadzać dodatkowych poziomów BOM w celu umożliwienia używania kart Kanban do półproduktów. Ta architektura pozwala także zminimalizować transakcje magazynowe.

## <a name="products-and-material-in-work-in-progress"></a>Produkty i materiały w pracy w toku
Wynikające z produkcji oszczędnej ograniczenie rozmiarów partii do idealnego stanu polegającego na przepływie pojedynczych sztuk może powodować drastyczny wzrost liczby transakcji magazynowych, jeśli każdy proces pobrania lub rejestracji Kanban powoduje powstawanie transakcji na zużywane towary. Architektura przepływu produkcji pozwala na przenoszenie materiałów do przepływu produkcji razem z kartami Kanban wycofania w rozmiarach w jednostkach magazynowych lub transportowych. Wartość wydanego materiału jest dodawana do konta pracy w toku (PWT) związanego z przepływem produkcji. To zachowanie jest podobne zachowania materiału wydawanego do zlecenia produkcyjnego. Tę samą zasadę można stosować do produktów i półproduktów. O ile te produkty nie są tworzone, przenoszone ani zużywane w przepływie produkcji, transakcje magazynowe są opcjonalne. Po zaksięgowaniu produktów w zapasach konto PWT przepływu produkcji jest redukowane przez odjęcie odnośnego kosztu standardowego.

## <a name="value-streams-and-value-stream-mapping"></a>Strumienie wartości i mapowanie strumienia wartości
Architektura modułu Lean Manufacturing została opracowana w oparciu o 5 zasad produkcji oszczędnej sformułowanych przez Womacka i Jonesa: wartość dla klienta, strumień wartości, ciągły przepływ, system ssący i dążenie do doskonałości. Jedną z aprobowanych metod wdrażania rozwiązań produkcji oszczędnej w realnym świecie produkcji jest mapowanie strumienia wartości (VSM). Ta metoda została wprowadzona przez Rothera i Shooka w publikacji „Naucz się Widzieć” wydanej przez Lean Manufacturing Institute. 

Strumień przyszłej wartości można modelować jako wersję przepływu produkcji. Wszystkie procesy strumienia wartości są modelowane jako działania procesu. Przesunięcia lub przeniesienia mogą być modelowane jako działania przeniesienia, jeśli stan przeniesienia musi być zarejestrowany lub jeśli jest wymagana integracja z pobieraniem z zapasów lub wysyłkami skonsolidowanymi. 

Sam strumień wartości jest modelowany jako jednostka operacyjna. Z tego względu strumień wartości może służyć jako wymiar finansowy.

Aby uzyskać więcej informacji o jednostkach operacyjnych, zobacz [Tworzenie nowej jednostki operacyjnej](../../fin-and-ops/organization-administration/tasks/create-operating-unit.md).

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Wycena produkcji oszczędnej w oparciu o przepływ produkcji
Okresowa konsolidacja kosztu przepływu produkcji koryguje powiązane konto PWT i pozwala na określenie odchyleń dla produktów dostarczanych przez przepływ produkcji.

## <a name="continuous-improvement"></a>Ciągłe doskonalenie
Aby lepiej wspierać ciągłe doskonalenie przepływy produkcji są implementowane jako wersje ograniczone czasowo. Z tego względu istniejącą wersję przepływu produkcji, razem ze wszystkimi powiązanymi regułami Kanban, można skopiować do przyszłej wersji przepływu produkcji. Ponadto przepływ przyszłej produkcji można wymodelować przed sprawdzeniem jego poprawności i aktywowaniu dla produkcji. Aby zapewnić bezproblemowy przepływ materiałów w dniu przejścia i później, istniejące karty Kanban ze starszych wersji przepływu produkcji są automatycznie wiązane z nową wersją.

## <a name="simplicity"></a>Prostota
W implementacji idei produkcji oszczędnej wybraliśmy podejście oparte na przepływie produkcji i działaniach, ponieważ umożliwia ono modelowanie prostych i złożonych scenariuszy produkcji w jednej skalowalnej architekturze. Bliższe przyjrzenie się koncepcji działań ujawnia prostotę cenioną przez użytkowników — pracowników z produkcji i logistyki. Dzięki funkcji raportowania według zadań opartych na działaniach zamiast na transakcjach magazynowych, jednolity interfejs użytkownika dla wszystkich rodzajów modelu Lean Manufacturing przenoszą złożoność biznesową z interfejsu użytkownika tam gdzie jest jej miejsce: do przepływu produkcji jako podstawy Lean Manufacturing.



