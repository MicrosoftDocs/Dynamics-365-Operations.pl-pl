---
title: "Kategorie kosztów używane w marszrutach produkcji"
description: "Ten artykuł zawiera informacje o kategoriach kosztów mających zastosowanie do środowisk produkcyjnych, w których są używane marszruty."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5b4030e7f02b14d0e5a9cf62ddc8a1809dfa91f3
ms.lasthandoff: 03/29/2017


---

# <a name="cost-categories-used-in-production-routing"></a>Kategorie kosztów używane w marszrutach produkcji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o kategoriach kosztów mających zastosowanie do środowisk produkcyjnych, w których są używane marszruty.

Kategorie kosztów mają zastosowanie do środowisk produkcyjnych, w których są używane marszruty. Są one przypisywane do zasobów operacyjnych i operacji marszruty w celu definiowania kosztów godzinowych oraz segmentowania udziałów kosztów w obliczonych kosztach wytwarzanych towarów. Grupy kosztów przypisywane do kategorii kosztów klasyfikują udziały w kosztach produkcji na podstawie zasobów operacyjnych i typów działań, takich jak czas przezbrajania i czas procesu. Specyficzność przypisań grup kosztów umożliwia obliczanie kosztów ogólnych produkcji na podstawie informacji o marszrutach. 

**Uwaga:** W środowisku produkcyjnym kategorie kosztów występują pod różnymi nazwami, takimi jak „kody stawek robocizny” lub „kody stawek maszynowych”. 

Każda kategoria kosztów ma skojarzone rekordy kosztów i przypisaną grupę kosztów. Do różnych celów produkcyjnych są wymagane różne kategorie kosztów.

-   Przypisywanie różnych kosztów godzinowych w zależności od zasobu operacyjnego. Na przykład koszty mogą być różne dla różnych typów umiejętności personelu, maszyn lub komórek produkcyjnych.
-   Należy przypisywać różne koszty godzinowe dotyczące czasu przezbrajania lub czasu procesu związanych z marszrutami.
-   Przypisywanie kosztów zasobów operacyjnych na podstawie wyprodukowanej ilości, a nie kosztów godzinowych, np. stawek akordowych.
-   Segmentowanie grup udziałów kosztów do obliczonego kosztu wytwarzanego towaru. Na przykład można segmentować koszty robocizny i maszyn.
-   Określanie grup kosztów będących podstawą dla formuł obliczania kosztów ogólnych, np. związanych z pracą i maszynami lub z czasami przezbrajania i procesu.

Kategorię kosztów można przypisać do czasu przezbrajania, czasu procesu oraz ilości w operacji marszruty. Jeśli na przykład segmentacja kosztów lub grup kosztów jest inna dla czasów przezbrajania i procesu, należy zdefiniować i przypisać różne kategorie kosztów dla czasu przezbrajania i czasu procesu. Selektywne używanie kategorii kosztów dla czasu przezbrajania, czasu procesu i ilości zależy od grupy marszrut przypisanej do operacji. Przypisanie kategorii kosztów do czasu i ilości może wynikać z ogólnofirmowych zasad podanych na stronie **Parametry kontroli produkcji**. 

Każda kategoria kosztów ma przypisane koszty, które bazują na definicji rekordów kosztów w wersji wyceny. Na stronie **Kategoria kosztu własnego** można zdefiniować rekordy kosztów dla określonej wersji wyceny i oddziału. Nowo wprowadzany rekord kosztu w kategorii kosztów ma stan **Oczekujące** i planowaną datę wejścia w życie. Aktywacja rekordu kosztu powoduje aktualizację stanu do wartości **Aktywne** oraz aktualizację daty wejścia w życie na datę aktywacji. Różne rekordy kosztów mogą odzwierciedlać różne oddziały, daty wejścia w życie lub stany. W obliczeniach list składowych (BOM) dla dat przyszłych lub historycznych są używane rekordy kosztów z odpowiednimi datami wejścia w życie. Aktywny rekord kosztu będzie używany do szacowania kosztów zlecenia produkcyjnego oraz wyceny czasu zgłaszanego dla zlecenia produkcyjnego. 

Rekord kosztu w kategorii kosztów może być specyficzny dla oddziału lub ogólnofirmowy. Aby rekord kosztu był specyficzny dla oddziału, należy mu przypisać oddział. W przeciwnym wartość pusta wskazuje, że rekord kosztu dotyczy wszystkich oddziałów w firmie. Koszty mogą się różnić między oddziałami, dlatego rekordy kosztów muszą być definiowane jako specyficzne dla oddziału. 

Operacja marszruty zazwyczaj dziedziczy kategorie kosztów przypisane do zasobu operacyjnego lub operacji głównej. Po utworzeniu zlecenia produkcyjnego operacje marszruty produkcji odzwierciedlają wybraną wersję marszruty. Można ręcznie zastąpić kategorie kosztów przypisane do operacji w marszrucie produkcji. 

Niektóre typy działań produkcyjnych mogą mieć zastosowanie do szacowania i raportowania czasu trwania projektu. W takim przypadku kategoria kosztów jest wymagana na potrzeby produkcji i projektu. Jeśli kategoria kosztów jest oznaczona do używania w projektach, należy zdefiniować dodatkowe informacje związane z projektami.




