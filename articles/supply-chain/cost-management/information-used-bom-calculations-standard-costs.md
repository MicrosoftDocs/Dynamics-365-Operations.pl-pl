---
title: Informacje wykorzystywane w obliczeniach na potrzeby BOM z użyciem kosztów standardowych
description: W obliczeniach listy składowej (BOM) są wykorzystywane dane z różnych źródeł w celu obliczenia kosztów standardowych wytwarzanego towaru. Źródła zawierają informacje o towarach, marszrutach, formułach obliczania kosztów pośrednich i wersjach wyceny.
author: AndersGirke
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b1aa33c11f7cfbbde2a278bef25189ac697d19
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575130"
---
# <a name="information-used-in-bom-calculations-with-standard-costs"></a>Informacje wykorzystywane w obliczeniach na potrzeby BOM z użyciem kosztów standardowych

[!include [banner](../includes/banner.md)]

W obliczeniach listy składowej (BOM) są wykorzystywane dane z różnych źródeł w celu obliczenia kosztów standardowych wytwarzanego towaru. Źródła zawierają informacje o towarach, marszrutach, formułach obliczania kosztów pośrednich i wersjach wyceny.

Informacje o nabytych towarach używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Koszty − Koszty nabytych towarów są aktualizowane we właściwych dla oddziału rekordach kosztów standardowych w ramach wersji ceny. W każdym takim rekordzie określona jest data obowiązywania, natomiast data obliczania BOM określa, które rekordy kosztów zostaną użyte. Na przykład w przypadku obliczania BOM, dla którego określono datę obliczania w przyszłości, może zostać użyty rekord kosztów ze statusem Oczekujący i przyszłą datą obowiązywania.
-   Grupa kosztów − Na podstawie grupy kosztów przypisanej do nabytego towaru wykonywana jest segmentacja obliczonych kosztów wytworzonego towaru.
-   Warunki wyświetlania ostrzeżeń uwzględnione w grupie obliczania BOM towaru umożliwiają wykrywanie potencjalnych problemów w ramach obliczeń na potrzeby BOM. Może to być np. zerowy koszt kupionego towaru lub zerowa ilość w BOM, albo nieaktualny rekord kosztu. Obowiązujące warunki wyświetlania ostrzeżeń mogą zostać zastąpione podczas inicjowania obliczeń na potrzeby BOM.

Informacje o wytworzonych towarach używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Standardowa ilość w zamówieniu dla magazynu − Standardowa ilość w zamówieniu na dany towar (dla magazynu) spełnia funkcję domyślnej księgowej wielkości partii na potrzeby amortyzacji stałych kosztów w ramach obliczeń na potrzeby BOM. Księgowa wielkość partii odzwierciedla również wielokrotność ilości na zamówieniu (jeśli określona).
-   Warunki wyświetlania ostrzeżeń uwzględnione w grupie obliczania BOM towaru umożliwiają wykrywanie potencjalnych problemów w ramach obliczeń na potrzeby BOM. Jednym z przykładów może być brak BOM lub marszruty dla wytwarzanego towaru. Obowiązujące warunki wyświetlania ostrzeżeń mogą zostać zastąpione podczas inicjowania obliczeń na potrzeby BOM.

Informacje o specyfikacji materiałowej (BOM) używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Wersja BOM − W wersji BOM przypisanej do wytwarzanego towaru określony jest zakres dat obowiązywania; wersja jest ponadto zatwierdzona i aktywna. Wersja BOM może być właściwa dla całej firmy lub dla danego oddziału oraz może opcjonalnie odzwierciedlać ograniczenia dotyczące ilości.
-   Ilość towaru w wierszu BOM − Ilość składnika jest zazwyczaj zmienna, ale może być stała. Ilość ta zazwyczaj dotyczy wyprodukowania jednej sztuki towaru, ale może być także wyrażona na 100 lub na 1000 sztuk (na potrzeby precyzyjnych obliczeń). Ilość ta może zostać również obliczona na podstawie wymiarów.
-   Ilość odpadków dla towaru w wierszu BOM − Dla składnika może być określona zmienna lub stała ilość planowanych odpadków.
-   Daty obowiązywania dotyczące towaru w wierszu BOM − Dla składnika może być określony zakres dat obowiązywania.
-   Typ produkcji dotyczący towaru w wierszu BOM − Wielkość obliczanej partii na potrzeby amortyzacji kosztów stałych odzwierciedla ilość z obliczeń BOM oraz tryb rozłożenia związany z produkcją na zamówienie, ponieważ w obliczeniach na potrzeby BOM zakłada się, że wytwarzany składnik zostanie wyprodukowany raczej w ściśle określonej ilości niż w ilości określonej w standardowym zamówieniu.
-   BOM podrzędny dla wytwarzanego składnika − Dla wytwarzanego składnika można opcjonalnie określić wersję BOM, która w obliczeniach BOM zostanie użyta zamiast bieżącej, aktywnej wersji BOM.
-   Marszruta podrzędna dla wytwarzanego składnika – Dla wytwarzanego składnika można opcjonalnie określić wersję marszruty, która w obliczeniach BOM zostanie użyta zamiast bieżącej, aktywnej wersji marszruty.
-   Numer operacji oraz wpływ wartości procentowej odpadków dla operacji − Numer operacji łączy składnik z konkretną operacją, a dla każdej operacji można określić ilość odpadków. Dzięki takiemu połączeniu w obliczeniach BOM może zostać uwzględniona wartość procentowa i zakumulowana wartość procentowa odpadków (dla wielu operacji) w odniesieniu do wymaganej ilości składnika.
-   Opcja zignorowania towaru w wierszu BOM w obliczeniach kosztów − Składnik może zostać zignorowany podczas obliczeń na potrzeby BOM.

Informacje o zasobie operacyjnym używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Koszty godzinowe − Koszty godzinowe związane z zasobem operacyjnym są określane w ramach kategorii kosztów przypisanych do czasu przezbrajania i czasu procesu. Kategorie te powinny być rozpoznawane zarówno dla grup zasobów, jak i dla samych zasobów operacyjnych. Koszty godzinowe przypisane do kategorii kosztów mogą być właściwe dla oddziału lub dotyczyć całej firmy.
-   Koszty jednostkowe − W niektórych środowiskach produkcyjnych koszty ponoszone w zasobach operacyjnych są przypisywane na jednostkę produkcji, co mogłoby stanowić inną kategorię kosztów dotyczącą ilości. Na przykład koszty dotyczące ilości mogą odzwierciedlać stawki akordowe, a producent farb może przypisywać koszty w zasobów operacyjnych na litr wyprodukowanej farby.
-   Zastępowanie informacji dotyczących marszrut właściwych dla zasobu operacyjnego − Informacje o kategoriach kosztów właściwych dla zasobu operacyjnego będą dziedziczone przez poszczególne operacje w przypadku, gdy możliwe jest zastąpienie takich informacji. W obliczeniach na potrzeby BOM użyte zostaną informacje o kategoriach kosztów określone w ramach operacji dotyczących marszrut.
-   Grupa kosztów dla kategorii kosztów − Grupa kosztów przypisana do kategorii kosztów umożliwia segmentację obliczonych kosztów wytworzonych towarów. Na przykład różne grupy kosztów mogą zostać użyte na potrzeby segmentacji obliczonych kosztów związanych z wykorzystaniem maszyn i pracą lub z czasem przezbrajania i czasem procesu.

Informacje o marszrucie używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Wersja marszruty − W wersji marszruty przypisanej do wytwarzanego towaru określony jest zakres dat obowiązywania; wersja jest ponadto zatwierdzona i aktywna. Wersja marszruty musi być właściwa dla oddziału oraz może opcjonalnie odzwierciedlać ograniczenia dotyczące ilości.
-   Czas związany z marszrutą − Czas ten może zostać określony dla czasu przezbrajania i czasu procesu. Czas godzinowy zazwyczaj dotyczy wyprodukowania jednej sztuki towaru, ale może być także wyrażony na 100 lub na 1000 sztuk (na potrzeby precyzyjnych obliczeń).
-   Czas związany z marszrutą dotyczący zasobów dodatkowych − Zasób dodatkowy ma ten sam numer operacji co zasób główny oraz jest mu przypisany taki sam czas związany z marszrutą. Na przykład operacja może wymagać wykorzystania maszyny (jako zasobu głównego) oraz nakładu pracy i wykorzystania narzędzi (jako zasobów dodatkowych).
-   Wartość procentowa odpadków związana z marszrutą − W obliczeniach na potrzeby BOM uwzględniane są wartości procentowe i skumulowane wartości procentowe dotyczące odpadków. Dotyczy to czasu wymaganego dla operacji marszruty i wymaganej ilości składników, które są połączone z numerami operacji.
-   Kategorie kosztów dotyczące marszrut − informacje o kategoriach kosztów właściwych dla zasobu operacyjnego będą dziedziczone przez poszczególne operacje w przypadku, gdy możliwe jest zastąpienie takich informacji. W obliczeniach na potrzeby BOM użyte zostaną informacje o kategoriach kosztów określone w ramach operacji dotyczących marszrut.

Informacje o ogólnych kosztach produkcji używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Dopłata − Formuła obliczania dopłat odzwierciedla procent wartości (np. 100%), który jest związany z określoną grupą kosztów, np. kosztami pracy.
-   Stawka − Formuła obliczania stawek odzwierciedla kwotę jednostkową (np. 10,00 USD na godzinę), która jest związana z określoną grupą kosztów, np. kosztami pracy.
-   Koszty ogólne zależne od czasu i od zużycia materiałów − Ogólne koszty produkcji mogą być związane z marszrutami lub materiałami.

Informacje o wersji ceny używane w przypadku obliczeń kosztu standardowego na potrzeby BOM to m.in.:
-   Typ ceny − Wersja ceny musi zawierać koszty standardowe. W przypadku obliczeń na potrzeby BOM z użyciem kosztów standardowych obowiązuje kilka ograniczeń. Na przykład opłaty dodatkowe muszą zostać uwzględnione w kosztach jednostkowych, a tryb rozłożenia w przypadku obliczeń na potrzeby BOM musi być jednopoziomowy.
-   Obowiązkowa zasada alternatywnego źródła danych − Wersja ceny może przewidywać obowiązkowe zastosowanie zasady alternatywnego źródła danych, np. użycia określonej wersji ceny lub aktywnego rekordu kosztów. Obowiązkowa zasada alternatywnego źródła danych ma zazwyczaj zastosowanie w przypadku wersji ceny, która dotyczy przyrostowych aktualizacji kosztów z wykorzystaniem dwóch wersji obliczania kosztów.
-   Flaga blokująca dla kosztów oczekiwanych − Flaga ta może zapobiec związanym z BOM obliczeniom oczekiwanych kosztów wytworzonych towarów.
-   Określona data początkowa − domyślna data rozpoczęcia wszystkich obliczeń na potrzeby BOM, które uwzględniają daną wersję ceny.
-   Określony oddział − ogranicza obliczenia na potrzeby BOM do konkretnego oddziału.
-   Wersja wyceny musi uwzględniać koszty. Opcjonalnie może też zawierać cen sprzedaży w celu obliczania sugerowanych cen sprzedaży produkowanych towarów.

Przy inicjowaniu obliczania BOM można określić kilka źródeł informacji. Mogą to być m.in. oddział, data obliczenia i wersja wyceny.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]