---
title: Planowanie produkcji
description: W tym temacie opisano planowanie produkcji i sposób modyfikowania planowanych zleceń produkcyjnych przy użyciu funkcji optymalizacji planowania.
author: ChristianRytt
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 85167e3de5f586c341143a43412501377a6c689e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570904"
---
# <a name="production-planning"></a>Planowanie produkcji

[!include [banner](../../includes/banner.md)]

Optymalizacja planowania obsługuje kilka scenariuszy produkcji. Podczas migrowania z istniejącego, wbudowanego aparatu planowania głównego należy pamiętać o pewnych zmienionych zachowaniach.

Poniższy film przedstawia krótkie wprowadzenie do niektórych pojęć omówionych w tym temacie: [Dynamics 365 Supply Chain Management: Ulepszenia optymalizacji planowania](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Włączanie funkcji w systemie

Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Planowane zlecenia produkcyjne w celu optymalizacji planowania*.

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

Aby mieć pewność, że optymalizacja planowania zawiera informacje wymagane do obliczenia poprawnego wyniku, musisz uwzględnić wszystkie produkty, które mają relacje z produktami w całej strukturze listy składowej (BOM) planowanego zamówienia. W przypadku scenariuszy planowania, które obejmują produkcję, zaleca się uniknięcie przefiltrowanych przebiegów planowania głównego.

Chociaż podrzędne elementy zależne są automatycznie wykrywane i uwzględniane w planowaniu głównym, gdy jest używany wbudowany aparat planowania głównego, optymalizacja planowania nie wykonuje obecnie tej akcji.

Jeśli na przykład do wytwarzania produktu B jest używany jeden element bolt ze struktury listy składowej (BOM) produktu A, w filtrze muszą zostać uwzględnione wszystkie produkty w strukturze BOM produktów A i B. Ponieważ zapewnienie, że wszystkie produkty są częścią filtra może być skomplikowane, zalecamy unikanie filtrowanych przebiegów planowania głównego, gdy w grę wchodzą zlecenia produkcyjne. W przeciwnym razie planowanie główne przyniesie niepożądane rezultaty.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Powody, dla których należy unikać filtrowania planów generalnych

Kiedy uruchamiasz filtrowane planowanie główne dla produktu, Optymalizacja planowania (w przeciwieństwie do wbudowanego silnika planowania głównego) nie wykrywa wszystkich podproduktów i surowców w strukturze BOM tego produktu, a zatem nie uwzględnia ich w przebiegu planowania głównego. Nawet jeśli Optymalizacja planowania identyfikuje pierwszy poziom w strukturze BOM produktu, nie ładuje żadnych ustawień produktu (takich jak domyślny typ zamówienia lub zakres pozycji) z bazy danych.

W optymalizacji planowania dane dla badania są ładowane wcześniej i stosowane są filtry. Oznacza to, że jeśli podprodukt lub surowiec wchodzący w skład określonego produktu nie jest częścią filtra, informacje o nim nie zostaną przechwycone dla przebiegu. Dodatkowo, jeżeli podprodukt lub surowiec jest również zawarty w innym produkcie, wówczas przefiltrowany przebieg obejmujący tylko oryginalny produkt i jego składniki spowodowałby usunięcie istniejącego planowanego popytu, który został utworzony dla tego innego produktu.

Ta logika może spowodować, że filtrowane przebiegi planowania głównego dadzą nieoczekiwane wyniki. Poniższe sekcje zawierają przykłady ilustrujące nieoczekiwane wyniki, które mogą wystąpić.

### <a name="example-1"></a>Przykład 1

Wyrób gotowy *FG* składa się z następujących komponentów:

- Surowiec *R*
- Podprodukt *S1*, która składa się z podproduktu *S2*

W magazynie znajdują się zapasy surowca *R*, natomiast podprodukt *S1* nie jest obecny w magazynie.

W przypadku filtrowanego planowania głównego dla wyrobu gotowego *FG* otrzymamy planowane zlecenie produkcyjne dla wyrobu gotowego *FG*, planowane zlecenie zakupu surowca *R* oraz planowane zlecenie zakupu podproduktu *S1*. Jest to niepożądany wynik, ponieważ optymalizacja planowania zignorowała istniejącą podaż na surowiec *R*, a podprodukt *S1* musi być produkowany przy użyciu *S2*, a nie zamawiany bezpośrednio. Dzieje się tak, ponieważ optymalizacja planowania posiada listę składników dla wyrobu gotowego *FG* bez żadnych powiązanych informacji, takich jak istniejąca podaż jego komponentów lub ich domyślne ustawienia zamówienia.

### <a name="example-2"></a>Przykład 2

W oparciu o poprzedni przykład dodatkowy gotowy produkt, *FG2*, również korzysta z podproduktu *S1*. Planowane zamówienie istnieje dla wyrobu gotowego *FG2*, a planowany popyt istnieje dla wszystkich jego komponentów, w tym *S1*.

Aby zniwelować niepożądane wyniki filtrowanego przebiegu planowania głównego z poprzedniego przykładu, należy dodać wszystkie podprodukty i surowce ze struktury BOM wyrobu gotowego *FG* do filtra, a następnie przeprowadzić pełną regenerację.

Po uruchomieniu pełnej regeneracji system usuwa wszystkie istniejące wyniki dla wszystkich uwzględnionych produktów, a następnie odtwarza wyniki w oparciu o nowe obliczenia. Oznacza to, że istniejący planowany popyt na wyrób *S1* jest usuwany, a następnie odtwarzany z uwzględnieniem tylko zapotrzebowania na wyroby gotowe *FG*, natomiast zapotrzebowanie na wyroby gotowe *FG2* jest pomijane. Dzieje się tak, ponieważ podczas uruchamiania optymalizacji planowania nie jest brane pod uwagę planowane zapotrzebowanie innych planowanych zleceń produkcyjnych &mdash; tylko planowane zapotrzebowanie wygenerowane podczas uruchamiania.

> [!NOTE]
> Jeśli istniejące planowane zamówienie na towar gotowy *FG2* ma status *Zatwierdzono*, to zatwierdzone planowane zapotrzebowanie zostanie uwzględnione, nawet jeśli produkt nadrzędny nie jest dodany do filtra.

Dlatego, jeśli nie doda się wszystkich komponentów wyrobu gotowego *FG*, wyrobu gotowego *FG2* oraz wszystkich innych produktów, których te komponenty są częścią (wraz z ich komponentami), to przefiltrowany przebieg planowania głównego da niepożądane wyniki.

Ponieważ zapewnienie, że wszystkie produkty są częścią filtra może być skomplikowane, zalecamy unikanie filtrowanych przebiegów planowania głównego, gdy w grę wchodzą zlecenia produkcyjne.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
