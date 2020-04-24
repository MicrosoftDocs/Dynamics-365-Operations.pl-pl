---
title: Omówienie stanów cyklu życia produktu
description: Stan cyklu życia produktu dokumentuje stan cyklu życia zwolnionego produktu lub wariantu produktu.
author: cvocph
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 7889f1d21bf38a9063fff6a64da50febd15df5d6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209451"
---
# <a name="product-lifecycle-state-overview"></a>Omówienie stanów cyklu życia produktu

[!include [banner](../includes/banner.md)]

Stan cyklu życia produktu dokumentuje stan cyklu życia zwolnionego produktu lub wariantu produktu. Stany cyklu życia produktu są definiowane przez użytkownika, zwykle menedżera produktu lub menedżera danych głównych produktu. Na określone procesy biznesowe, takie jak planowanie główne, ma wpływ określony stan cykl życia.   

Zwolniony produkt lub wariant produktu można skojarzyć ze stanem cyklu życia produktu, który dokumentuje, w którym stanie cyklu życia jest aktualnie określony produkt lub wariant. Można zdefiniować dowolną liczbę stanów cyklu życia produktu, określając ich nazwę i opis. Jeden stan cyklu życia można wybrać jako stan domyślny nowych zwolnionych produktów. Warianty zwolnionych produktów dziedziczą stan cyklu życia produktu ze zwolnionego produktu głównego podczas tworzenia. Przy zmianie stanu cyklu życia zwolnionego produktu głównego można wybrać aktualizację wszystkich istniejących wariantów, które mają ten sam stan oryginalny.  

## <a name="create-a-new-product-lifecycle-state"></a>Tworzenie nowego stanu cyklu życia produktu 

- Aby utworzyć nowy stan cyklu życia produktu, odtwórz lub przeczytaj przewodnik zadania **Tworzenie nowego stanu cyklu życia produktu**. 

-  Aby utworzyć domyślny stan cyklu życia produktu, odtwórz lub przeczytaj przewodnik zadania **Tworzenie domyślnego stanu cyklu życia produktu**.   

## <a name="associate-product-lifecycle-states-to-released-products"></a>Kojarzenie stanów cyklu życia produktu ze zwolnionymi produktami  

Istnieje kilka sposobów skojarzenia stanu cyklu życia produktu ze zwolnionymi produktami lub wariantami produktów.

-  Przy tworzeniu nowego zwolnionego produktu automatycznie przypisywany jest domyślny **Stan cyklu życia produktu**. 
-  Przy zwalnianiu produktu do firmy automatycznie przypisywany jest domyślny **Stan cyklu życia produktu**. 
-  Przy zwalnianiu wariantu produktu do firmy **stan cyklu życia produktu** skojarzony ze zwolnionym produktem głównym w tej firmie jest automatycznie przypisywany do nowego wariantu. 

Stan cyklu życia produktu można zaktualizować ręcznie, używając następujących elementów: 

-    Strona listy **Zwolnione produkty** lub opcja **Widok szczegółów**. 
-  Strona listy **Warianty zwolnionych produktów** lub opcja **Widok szczegółów**. 
-  Przestarzałe produkty lub warianty produktów można znaleźć na podstawie popytu i skojarzyć stan cyklu życia produktu.  

Aby uzyskać szczegółowe informacje na temat kojarzenia stanów cyklu życia produktu, odtwórz lub przeczytaj następujące dwa przewodniki zadania.

-  Aby skojarzyć stan cyklu życia produktu ze zwolnionym produktem głównym, przeczytaj lub odtwórz przewodnik zadania **Przypisywanie cyklu życia produktu do zwolnionego produktu głównego**. 

-  Aby skojarzyć stan cyklu życia produktu ze zwolnionym produktem, przeczytaj lub odtwórz przewodnik zadania **Przypisywanie cyklu życia produktu do zwolnionego produktu**. 

## <a name="impact-on-master-planning"></a>Wpływ na planowanie główne 

Stan cyklu życia produktu ma tylko jedną flagę kontrolną: **Jest aktywna dla planowania**. Domyślnie jest ustawiona na **Tak** dla wszystkich utworzonych stanów cyklu życia produktu, ale można ją zmienić na **Nie**. Po ustawieniu na **Nie** skojarzone zwalniane produkty lub warianty zwalnianych produktów są: 

-  Wykluczane z planowania głównego. 
-  Wykluczane z obliczania na poziomie BOM. 

Aby uzyskać szczegółowe informacje o sposobie używania stanu cyklu życia produktu do wykluczania produktów z planowania głównego i obliczania na poziomie BOM, odtwórz lub przeczytaj przewodnik zadania **Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego**.

> [!NOTE]
> Z względu na wydajność zdecydowanie zalecane jest skojarzenie wszystkich przestarzałych zwolnionych produktów lub wariantów produktów, szczególnie w przypadku pracy z wariantami konfiguracji produktów, których nie można wykorzystać ponownie, ze stanem cyklu życia produktu nieaktywnym dla planowania głównego.  

## <a name="default-migration-import-and-export"></a>Domyślna migracja, import i eksport 

Stany cyklu życia produktu są obsługiwane przez jednostki danych, a stan cyklu życia można ustawić na zmienny za pomocą jednostki danych zwolnionego produktu lub jednostki danych zwolnionego wariantu.

## <a name="find-obsolete-products-and-products-variants"></a>Znajdowanie przestarzałych produktów i wariantów produktów 

Aby znaleźć przestarzałe zwolnione produkty lub warianty produktów można uruchomić symulację, a następnie zaktualizować ich stan cyklu życia produktu. Aby znaleźć przestarzałe produkty, odtwórz i przeczytaj przewodnik zadania **Znajdowanie wariantów przestarzałych produktów i przypisywanie stanu cyklu życia produktu**. Ten przewodnik zadania pokazuje, jak znaleźć przestarzałe zwolnione produkty lub warianty produktów i skojarzyć stan cyklu życia produktu z przestarzałymi produktami. Pokazuje także, jak wyświetlić wyniki symulacji i ocenić, ile produktów i wariantów produktów będzie skojarzonych z nowym stanem cyklu życia produktu po uruchomieniu aktualizacji bez symulacji.  

Po uruchomieniu analizy w trybie symulacji produkty i warianty produktów określone jako przestarzałe są wyświetlane w określonej formie, w której można je łatwo przejrzeć. Analiza wyszukuje transakcje i określone dane główne w celu identyfikacji produktów, na które nie ma popytu w zmiennym okresie ani danych głównych, które mogą powodować popyt. Nowe zwolnione produkty w zmiennym okresie można wykluczyć z analizy. Gdy analiza zwróci oczekiwany wynik, użytkownik może uruchomić analizę i ustawić nowy stan cyklu życia produktu dla wszystkich produktów określonych w analizie jako przestarzałe.  

> [!NOTE]
> Należy pamiętać, że wszystkie analizy i aktualizacje muszą zostać wykonane w tej samej firmie.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Kryteria wyboru i aktualizacji zwolnionych produktów lub wariantów produktów 

W celu wybrania i aktualizacji zwolnionych produktów i wariantów produktów należy użyć następujących kryteriów: 

-    Stan cyklu życia produktu lub wariantu produktu musi różnić się od nowego wymaganego stanu. 
-  Produkt lub wariant produktu został utworzony klika dni wcześniej na podstawie liczby dni wprowadzonych w oknie dialogowym wyboru. 
-  Nie ma otwartych zamówień produktu (= stan < zakończony) na produkt lub wariant produktu. 
-  Nie ma otwartych transakcji zapasów (= stan wydania ReservPhysical do QuotationIssue lub stan odbioru Registrered do QuotationReceipt) dla produktu lub wariantu produktu. 
-  Nie ma transakcji zapasów w ciągu ostatnich dni dla produktu lub wariantu produktu. 
-  Nie ma przyszłego popytu ani prognozy dostaw dla produktu lub wariantu produktu.  
-  Nie ustawiono minimalnego poziomu zapasów w zapotrzebowaniu na pozycję dla produktu lub wariantu produktu. 
-  Nie ma aktywnej reguły kanban stałej ilości dla produktu lub wariantu produktu.  
-  Brak wiersza zlecenia serwisowego dla produktu lub wariantu produktu. 
-  Brak wierszy aktywnej lub przyszłej umowy sprzedaży lub zakupu dla produktu lub wariantu produktu. 
-  Produkt lub wariant produktu nie jest używany w BOM skojarzonym w niewygasłej zatwierdzonej wersji BOM dla produktu lub wariantu aktywnego dla planowania.

## <a name="related-topics"></a>Powiązane tematy

-  [Tworzenie nowego stanu cyklu życia produktu](tasks/new-product-lifecycle-state.md)
-  [Tworzenie domyślnego stanu cyklu życia produktu](tasks/default-product-lifecycle-state.md)
-  [Przypisywanie stanu cyklu życia produktu do zwolnionego produktu głównego](tasks/product-lifecycle-state-released-product-master.md)
-  [Przypisywanie stanu cyklu życia produktu do zwolnionego produktu](tasks/product-lifecycle-state-released-product.md)
-  [Znajdowanie wariantów przestarzałych produktów i przypisywanie stanu cyklu życia produktu](tasks/obsolete-product-variants.md)
-  [Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego](tasks/exclude-products-master-planning.md)
