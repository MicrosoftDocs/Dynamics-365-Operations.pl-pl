---
title: Planowanie produkcji
description: W tym temacie opisano planowanie produkcji i sposób modyfikowania planowanych zleceń produkcyjnych przy użyciu funkcji optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992402"
---
# <a name="production-planning"></a>Planowanie produkcji

Optymalizacja planowania obsługuje kilka scenariuszy produkcji. Podczas migrowania z istniejącego, wbudowanego aparatu planowania głównego należy pamiętać o pewnych zmienionych zachowaniach.

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a>Planowane zlecenia produkcyjne

Gdy planowanie główne tworzy zamówienia planowane w celu spełnienia wymagań, typ zamówienia jest określany na podstawie wartości pola **Typ planowanego zamówienia**. Jeśli w polu **Typ planowanego zamówienia** jest ustawiona wartość *Produkcja*, tworzone są planowane zlecenia produkcyjne. Te planowane zlecenia produkcyjne zawierają informacje o aktywnej liście składowej (BOM) i identyfikatorze marszruty z powiązanych ustawień produkcji.

## <a name="requirements-from-boms"></a>Wymagania z listy składowej (BOM)

Informacje BOM są uwzględniane podczas planowania głównego. Dane wyjściowe planu obejmują podaż materiałów w celu pokrycia powiązanego popytu materiałowego dla produkcji.

Podczas planowania głównego do określania materiałów wymaganych do produkcji służy bieżąca, aktywna lista składowa (BOM). W tym kroku wykonywane są wszystkie poziomy struktury listy składowej (BOM) powiązane z wymaganym zleceniem produkcyjnym. Zapotrzebowanie na materiały jest wypełniane przy użyciu dostępnych zapasów, istniejących dostaw dostępnych na zamówieniu oraz zatwierdzonych zamówień planowanych. Jeśli w dowolnym miejscu jest wymagany dodatkowy materiał, tworzone jest zamówienie planowane w celu pokrycia zapotrzebowania.

## <a name="scheduling-during-firming"></a>Planowanie podczas akceptowania

Planowane zlecenia produkcyjne zawierają identyfikator marszruty wymagany do planowania produkcji. Obsługa planowania podczas uruchamiania planowania zamówień planowanych jest w fazie oczekiwania. Identyfikator marszruty służy do planowania planowanych zleceń produkcyjnych podczas ich akceptowania. Dlatego czas realizacji w planowanych zleceniach produkcyjnych może różnić się od czasu realizacji dla powiązanych z nimi zaplanowanych, zaakceptowanych zleceń produkcyjnych, które są generowane na ich podstawie, w sposób opisany poniżej:

- **Planowane zlecenie produkcyjne** — czas realizacji jest oparty na statycznym czasie realizacji ze zwolnionego produktu.
- **Zaakceptowane zlecenie produkcyjne** — czas realizacji jest oparty na planowaniu przy użyciu informacji o marszrucie i powiązanych ograniczeniach zasobów.

Aby uzyskać więcej informacji o oczekiwanej dostępności funkcji, zobacz temat [Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md).

Jeśli korzystasz z funkcji produkcji, które nie są jeszcze dostępne dla optymalizacji planowania, możesz nadal używać wbudowanego aparatu planowania głównego. Wyjątki nie są wymagane.

## <a name="delays"></a>Opóźnienia

Jeśli czas realizacji dla wymaganego materiału jest dłuższy niż okres między datą dzisiejszą a datą zapotrzebowania materiałowego, planowane zamówienie na wymagany materiał i związane z nim zlecenie produkcyjne zostanie opóźnione. W przypadku zamówień planowanych opóźnienie (w dniach) jest obliczane na podstawie czasu realizacji ze zwolnionego produktu. Informacje o opóźnieniu są następnie propagowane na wszystkich poziomach struktury listy składowej (BOM). W związku z tym można śledzić wpływ opóźnionego surowca podczas drogi do zlecenia sprzedaży klienta.

## <a name="modifying-planned-orders"></a>Modyfikowanie planowanych zamówień

Po zmianie informacji na zamówieniu planowanym wyświetlany jest następujący komunikat: „Pamiętaj, że wpływ ręcznych zmian na zamówienia planowane nie będzie uwzględniany w pozostałej części planu przed następnym uruchomieniem planowania głównego”.

Aby zmienić informacje dotyczące planowanego zamówienia i zobaczyć wpływ na pokrewne wymagania materiałowe, należy wykonać następujące czynności.

1. Aktualizowanie planowanego zamówienia.
2. Zatwierdzanie planowanego zamówienia.
3. Uruchamianie planowania głównego.

Po uruchomieniu planowania głównego nie należy używać filtrów, jeśli są uwzględnione planowane zlecenia produkcyjne. Więcej informacji znajduje się w dalszej sekcji [Filtry](#filters) w tym temacie.

> [!NOTE]
> Jeśli data dostawy planowanego zamówienia zostanie zmieniona na datę późniejszą, popyt może zostać ustalony względem nowego zamówienia planowanego. Takie działanie ma miejsce, gdy nowa data dostawy powoduje opóźnienie dla ustaleń popytu, ale zgodnie z ustawieniami czasu realizacji można uniknąć opóźnienia.

## <a name="explosion-page"></a>Strona Rozłożenie

Strony **Rozłożenie** można użyć do analizy popytu wymaganego dla określonego zlecenia produkcyjnego lub planowanego zlecenia produkcyjnego, powiązanego zapotrzebowania oraz informacji dotyczących oznaczania transakcji. Informacje na stronie **Rozłożenie** są aktualizowane podczas planowania głównego. Nie można zaktualizować informacji bezpośrednio ze strony **Rozłożenie**.

## <a name="filters"></a><a name="filters"></a>Filtry

W przypadku scenariuszy planowania, które obejmują produkcję, zaleca się uniknięcie przefiltrowanych przebiegów planowania głównego. Aby mieć pewność, że optymalizacja planowania zawiera informacje wymagane do obliczenia poprawnego wyniku, musisz uwzględnić wszystkie produkty, które mają relacje z produktami w całej strukturze listy składowej (BOM) planowanego zamówienia.

Chociaż podrzędne elementy zależne są automatycznie wykrywane i uwzględniane w planowaniu głównym, gdy jest używany wbudowany aparat planowania głównego, optymalizacja planowania nie wykonuje tej akcji.

Jeśli na przykład do wytwarzania produktu B jest używany jeden element bolt ze struktury listy składowej (BOM) produktu A, w filtrze muszą zostać uwzględnione wszystkie produkty w strukturze BOM produktów A i B. Ze względu na to, że zapewnienie, że wszystkie produkty są częścią filtru, może być bardzo złożone, zalecamy uniknięcie odfiltrowanych przebiegów planowania głównego podczas realizacji zleceń produkcyjnych.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]