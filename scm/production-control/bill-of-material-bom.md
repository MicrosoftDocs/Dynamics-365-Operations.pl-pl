---
title: "Listy składowe (BOM) i formuły"
description: "Ten artykuł zawiera informacje o listach składowych (BOM) i formułach, które są najważniejszymi elementami definicji produktów i wariantów produktów. Listy BOM i formuły określają wymagane materiały lub składniki dla określonego produktu. Formuły określają również produkty towarzyszące i uboczne uzyskiwane w określonym kontekście produkcji."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5a23acfa95bb93dbc5990bf3839bbc629f15cc2f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="bills-of-materials-and-formulas"></a>Listy składowe (BOM) i formuły

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o listach składowych (BOM) i formułach, które są najważniejszymi elementami definicji produktów i wariantów produktów. Listy BOM i formuły określają wymagane materiały lub składniki dla określonego produktu. Formuły określają również produkty towarzyszące i uboczne uzyskiwane w określonym kontekście produkcji. 

<a name="bills-of-materials"></a>BOM
------------------

Lista składowa (BOM) określa składniki, które są wymagane do wytworzenia produktu. Składniki mogą być surowcami, półproduktami lub substancjami. W niektórych przypadkach listy składowe mogą zawierać usługi. Jednak zwykle listy składowe BOM zawierają wymagane *zasoby materialne*.  

Jeśli lista składowa jest połączona z marszrutą lub przepływem produkcji, który określa operacje i zasoby potrzebne do wytworzenia produktu, wówczas BOM stanowi podstawę obliczania szacowanego kosztu produktu.  

BOM jest osobną jednostką opisaną przy użyciu następujących informacji:

-   Identyfikator BOM
-   Nazwa BOM
-   Wiersze BOM, które opisują składniki i substancje
-   Wersje BOM, które określają produkt i okres, w którym będzie używana lista składowa

Pojedyncza lista składowa określa jeden poziom identyfikowany przez unikatowy identyfikator. Składniki mogą mieć własne listy składowe, do których odnoszą się wersje BOM W Konstruktorze BOM można wyświetlić i edytować kompletne hierarchie list składowych dla określonego produktu.

### <a name="formulas-co-products-and-by-products"></a>Formuły, produkty towarzyszące i produkty uboczne

Formuła jest podtypem BOM, który jest zwykle stosowany do procesu produkcji. Oprócz składników i substancji formuła opisuje produkty towarzyszące i produkty uboczne. W bieżącej wersji definicja produktów towarzyszących i ubocznych dla formuły wymaga wersji formuły. Formuła jest zwykle definiowana dla jednego określonego wyrobu gotowego (formuły lub element planowania) zdefiniowanego w wersji formuły.

### <a name="boms-in-the-product-lifecycle"></a>BOM w cyklu życia produktu

W cyklu życia produktu mogą być tworzone różne BOM z różnych przyczyn:

-   **Szkic/wersja robocza BOM** — ta lista składowa zawiera wersję próbną oszacowania potrzebnych materiałów w początkowej fazie projektowania ułatwia wstępne oszacowanie kosztów i atrybutów produktów. Ta lista składowa nie jest zazwyczaj używana w planowaniu zasobów przedsiębiorstwa.
-   **Inżynieryjne listy składowe** — ta lista składowa jest zazwyczaj używana podczas tworzenia produktów na podstawie istniejących portfolio produktów. Inżynieryjne listy składowe mają strukturę upraszczającą proces projektowania i grupują złożone produkty w moduły inżynieryjne. W przypadku nieskomplikowanych produktów może być możliwe wykorzystanie inżynieryjnych BOM w bieżącym procesie produkcyjnym. Jednakże w przypadku innych produktów inżynieryjne BOM trzeba przekonwertować na BOM bieżącej produkcji. Inżynieryjne BOM zazwyczaj są reprezentowane przez fantomy w hierarchii BOM. Mimo że inżynieryjnych BOM można używać do planowania i wykonywania czynności produkcyjnych, ta metoda może prowadzić do nieefektywności, szczególnie w przypadku powtarzających się operacji, którym towarzyszy tworzenie wielu zamówień.
-   **Planistyczne BOM** — ta lista składowa jest wykorzystywana do planowania zapotrzebowania materiałowego. Zapotrzebowanie na składniki i substancje jest obliczane na podstawie popytu wyrobów gotowych. Podobnie jak BOM do wyceny, planistyczne BOM mogą uwzględniać określoną kombinację materiałów używanych w danym okresie.
-   **BOM produkcji** — jest to rzeczywista lista składowa używana dla określonej produkcji. BOM produkcji musi brać pod uwagę rzeczywiste zasoby, które służą do wytworzenia produktu. Podczas tworzenia zlecenia produkcyjnego, zamówienia partii lub kanban, następuje połączenie wielu poziomów BOM reprezentowanych przez fantomy. Następnie są przekazywane do operacji w ramach zamówienia.
-   **BOM wyceny** — ta lista składowa jest używana do obliczania szacowanego kosztu produktu. Na przykład, możesz użyć BOM wyceny, gdy używany jest koszt standardowy lub jest obliczany szacowany planowany koszt danego produktu. BOM wyceny może się odnosić do określonej kombinacji materiałów i zasobów, która ma zostać użyta. W związku z tym można użyć BOM wyceny do utworzenia reprezentatywnego szacowanego kosztu dla okresu i zapobiegania powstawaniu rozbieżności w czasie.

Typy BOM, które są używane w implementacji, zależą od implementacji oraz scenariuszy i wymagań biznesowych. W prostych implementacjach BOM odnoszące się do planowania, produkcji i wyceny można łączyć w jedną listę składową. W środowiskach, które wymagają częstych zmian inżynieryjnych i wielu alternatywnych marszrut, zazwyczaj konieczne jest używanie bardziej złożonego zestawu list składowych.

### <a name="approval-of-boms-and-formulas"></a>Zatwierdzenie BOM i formuły

Każdą listę składową i formułę można z osobna odrzucać lub zatwierdzać. Na ogół zatwierdzenie BOM lub formuły występuje, gdy zostanie zatwierdzona pierwsza odpowiednia wersja BOM. W niektórych scenariuszach biznesowych zatwierdzenia te mogą być różnymi etapami procesu i mogą obejmować różnych właścicieli procesu.  

Należy zwrócić uwagę, że jeśli BOM jest niezatwierdzona, wszystkie powiązane wersje BOM są również niezatwierdzone.

## <a name="bom-and-formula-versions"></a>Wersje BOM lub formuły
Aby powiązać BOM lub formułę z wariantem produktu, który ma być wytworzony, należy utworzyć wersję BOM lub formuły. Ważność wersji BOM i wersji formuły może być ograniczona przez okres, ilości, oddział, wymiary określonego produktu i inne kryteria. Wersje formuły mają dodatkowe ważne atrybuty, takie jak definicje uzysku, produktów towarzyszących i ubocznych, oraz instrukcje dystrybucji kosztu dla formuły.

### <a name="approval-of-bom-and-formula-versions"></a>Zatwierdzenie wersji BOM i formuły

Wersja BOM musi zostać zatwierdzona, żeby można było jej użyć w procesie planowania lub produkcji. Po zatwierdzeniu wersji BOM powiązane BOM też mogą zostać zatwierdzone w zależności od wyboru użytkownika i uprawnień uwierzytelniania. Należy zwrócić uwagę, że wersja BOM może zostać zatwierdzona tylko wtedy, gdy powiązana BOM jest zatwierdzona.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Aktywacja domyślnej wersji BOM lub formuły

Aby ustawić określoną BOM lub formułę jako wersję domyślną, która będzie używana w planowaniu głównym lub do tworzenia zleceń produkcyjnych, trzeba aktywować tę wersję. Po uaktywnieniu wersji jest weryfikowana unikatowości wersji dla danych ograniczeń (na przykład okresu, oddziału lub ilości). Jeśli wersja, którą próbujesz uaktywnić, powoduje konflikt z wersją już aktywną, zostanie wyświetlony komunikat o błędzie. Należy następnie zdezaktywować wersję powodującą konflikt lub zmodyfikować jej ograniczenia (zwykle okres), aby uniknąć niejednoznacznej aktywacji.

### <a name="product-change-with-case-management"></a>Zmiany w produkcie z zarządzaniem sprawą

Sprawa zmiany w produkcie do zatwierdzenia i uaktywnienia nowych lub zmienionych BOM i wersji BOM zapewnia prosty sposób przeglądania ograniczeń wersji BOM. Można także zatwierdzać i aktywować wszystkie BOM i formuły odnoszące się do określonej zmiany dla jednaj daty aktywacji.

### <a name="alternative-bom-versions"></a>Alternatywne wersje BOM

Czasami aktywna wersja BOM lub formuły nie powinna już być używana do prognozowania, sprzedaży lub w produktach nadrzędnych. W takim przypadku można wybrać określoną zatwierdzoną listę składową jako część zapotrzebowania (wiersz prognozy, wiersz sprzedaży lub wiersz BOM), jeśli istnieje zatwierdzona wersja BOM lub formuły dla alternatywnej listy składowej lub formuły.  

Podczas tworzenia zamówień planowanych zleceń produkcyjnych i kart Kanban, planista lub kierownik produkcji może używać dowolnej zatwierdzonej wersji BOM, która obowiązuje w dniu planowanej produkcji do planowania lub produkcji określonego produktu. Wersji BOM, która jest używana nie musi być uaktywniona jako domyślna wersja BOM.

## <a name="bom-and-formula-lines"></a>Wiersze BOM i formuły
Wiersz BOM jest tworzony dla każdego materiału, usług lub substancji. Definiuje także planowane zużycie określonego wariantu produktu i różne atrybuty związane z planowanym zużyciem.  

Wiersze BOM mogą mieć następujące typy: **Pozycja**, **Fantom**, **Ustalona dostawa**, **Dostawca**.

### <a name="item"></a>Pozycja

Wybierz typ wiersza **Pozycja** dla materiałów lub usług, które są bezpośrednio zużywane i nie wymagają dalszego rozłożenia lub ustalonej dostawy.

### <a name="phantom"></a>Fantom

Wybierz opcję **Fantom**, gdy trzeba rozłożyć towary BOM niskiego poziomu, zawarte w wierszu BOM. W planowaniu głównym, w obliczeniach kosztów planowanych lub w trakcie szacowania zlecenia produkcyjnego używającego wierszy BOM o typie **fantom** wiersz nadrzędny BOM, który odnosi się do wariantu produktu z fantomową listą składową, jest zastępowany komponentami wymienionymi jako wiersze BOM na tej liście składowej, jak określa odpowiednia aktywna wersja BOM tego wariantu produktu. Jeśli wariant produktu ma odpowiednią aktywną marszrutę, operacje tej marszruty są scalane w jedną nadrzędną marszrutę.  

Należy zwrócić uwagę, że fantomy są zwykle używane do uproszczenia procesu inżynieryjnego. Nadmierne korzystanie z fantomowych BOM na wielu poziomach wpływa na wydajność, szczególnie w scenariuszach produkcji o dużej powtarzalności. Aby zwiększyć wydajność, należy unikać głębokich hierarchii fantomów. Użyj wstępnie rozwiniętych BOM i marszrut.

### <a name="pegged-supply"></a>Ustalona dostawa

Wybierz**ustalana dostaw** typ wiersza, aby utworzyć produkcję podrzędną, karty kanban zdarzenia wiersza BOM lub bezpośredniego zamówienia zakupu dla dowolnego wariantu produktu, który odwołuje się do wiersza BOM. Produkcję podrzędną, kanban zdarzenia lub zamówienie zakupu są tworzone podczas szacowania zamówienia produkcyjnego. Wymagane ilości towarów są automatycznie rezerwowane na potrzeby zamówienia produkcyjnego zużywającego towary.

### <a name="vendor"></a>Dostawca

Wybierz typ wiersza **Dostawca**, jeśli w procesie produkcji występuje podwykonawca i trzeba automatycznie utworzyć produkcję podrzędną lub zlecenie zakupu dla podwykonawcy.  

**Uwaga na temat operacji produkcji podrzędnej w BOM:** usługi lub praca wykonywane przez podwykonawcę należy utworzyć jako usługę, która jest śledzona w magazynie. Usługę należy dołączyć do elementu nadrzędnego jako wiersz BOM. Marszruta musi zawierać operację przypisaną do zasobu operacyjnego podwykonawcy.




