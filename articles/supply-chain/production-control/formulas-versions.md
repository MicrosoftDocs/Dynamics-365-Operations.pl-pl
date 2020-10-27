---
title: Formuły i wersje formuł
description: Ten temat zawiera informacje o formułach i wersjach formuł. Formuła określa materiały, składniki i wyniki określonego procesu w wytwarzaniu procesowym. Formuły służą do planowania i wytwarzania produktów w wytwarzaniu procesowym.
author: cvocph
manager: tfehr
ms.date: 09/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule, EcoResProductProdTypeFormulaNoActiveFormulaFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7fb37483412fdd09fe3734ddb148b050ec02951
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986981"
---
# <a name="formulas-and-formula-versions"></a>Formuły i wersje formuł

[!include [banner](../includes/banner.md)]

Formuła określa materiały, składniki i wyniki określonego procesu w wytwarzaniu procesowym. Wraz z odpowiednią marszrutą formuła definiuje cały proces w wytwarzaniu procesowym. Formuły służą do planowania i wytwarzania produktów w wytwarzaniu procesowym.

Formuła składa się ze składników i ilości wymaganych do wytworzenia określonej ilości produktu typu Formuła. W zależności od wykonywanego zadania, można uzyskać dostęp do funkcji formuły z modułu Zarządzanie zapasami i magazynem lub Zarządzanie informacjami o produktach.

## <a name="formulas-and-formula-lines"></a>Formuły i wiersze formuły
Formuła składa się z jednego lub kilku wierszy formuły, w których określone są składniki lub towary tworzące taką formułę. Wiersz formuły może zawierać pozycje listy składowej (BOM), towary formuły, towary w ilości efektywnej, pozycje zakupione, produkty towarzyszące lub produkty uboczne. Wiele towarów jest stosowanych w różnych produktach, dany towar można zatem uwzględniać w więcej niż jednej formule.

Przykładem formuły jest przepis na czekoladowe ciasteczka. Składniki tej formuły wykorzystują wiele wierszy, takich jak mąka, cukier, jajka, masło i czekolada. Formuła na czekoladowe ciasteczka zawiera składniki, które mogą zostać zastosowane w innych formułach. Podczas przygotowywania ciastek czekoladowych mogą zostać resztki, na przykład okruszki, niektóre ciastka mogą być przypalone lub niedopieczone. Te pozycje można ustawić jako produkty towarzyszące lub produkty uboczne, w zależności od operacji produkcji.

Podczas tworzenia wiersza formuły typ wiersza służy do określenia, jak system ma obsłużyć wiersz po uruchomieniu planowania głównego i zamówień partii produkcji. Różne typy wiersza determinują różne wyniki. W poniższej tabeli opisano typy wierszy, które można wybrać: 

| Typ wiersza     | opis  |
|---------------|--------------|
| Element          | Wybierz opcję **Towar** w wypadku, gdy towar jest nieprzetworzonym surowcem lub półproduktem pobieranym z magazynu albo gdy towarem jest usługa. |
| Fantom       | Wybierz opcję **Fantom**, gdy trzeba rozłożyć produkty typu Formuła niskiego poziomu zawarte w wierszach formuły. Jeżeli szacowane są zamówienia partii a produkty typu Formuła są rozłożone, towary składowe są wymienione jako wiersze formuły w zamówieniu partii. Ponadto odpowiednie marszruty są dodawane do marszruty produkcji. Produkty typu Formuła są rozkładane przy użyciu bieżącej konfiguracji. Używając typu wiersza **Fantom** można obsługiwać produkcję i konfiguracje miar właściwe dla różnych poziomów formuł. Jeżeli wybrano opcję **Fantom** dla produktu na skróconej karcie **Konstruuj** strony **Szczegóły zwolnionego produktu**, a następnie użyto tego produktu w formule typ wiersza formuły zostanie zmieniony na **Fantom**. Opcji **Fantom** nie można wybrać dla towaru w ilości efektywnej ani dla towarów, dla których typ produkcji to **Produkt towarzyszący**, **Produkt uboczny** lub **Element planowania**. |
| Ustalona dostawa | Wybierz opcję **Ustalona dostawa**, aby utworzyć zamówienie partii, zlecenie produkcyjne, kanban, zamówienie przeniesienia lub zamówienie zakupu na składnik zawarty w wierszu formuły. Powiązane zamówienie jest określone na podstawie domyślnych ustawień zamówienia i typu produkcji składnika i jest tworzone po oszacowaniu zamówienia partii. Wymagane ilości składnika są rezerwowane dla zamówienia partii. |
| Dostawca        | Wybierz opcję **Dostawca** w wypadku, gdy w procesie produkcji występuje podwykonawca i trzeba utworzyć produkcję podrzędną lub zamówienie zakupu dla podwykonawcy. Usługa lub praca wykonywana przez podwykonawcę musi zostać utworzona przy użyciu produktu typu Formuła lub usługi. Towar można dołączyć w postaci wiersza formuły do nadrzędnego towaru. Marszruta musi zawierać operację przypisaną do zasobu operacyjnego podwykonawcy. Ta operacja jest dołączana do wiersza formuły przy użyciu pola **Operacja nr** zaznacz wartość Tak. |

## <a name="formula-versions"></a>Wersje formuły
Gdy tworzona jest nowa formuła, należy najpierw utworzyć wersję formuły przed dodaniem towarów wiersza formuły z konkretnym opisem. Każda formuła musi mieć przynajmniej jedną wersję. Przycisk **Zatwierdzone** w wersji formuły jest dostępny dopiero po pomyślnym zapisaniu rekordu wersji. Każdy rekord wersji formuły jest skojarzony z jednym lub wieloma produktami towarzyszącymi i ubocznymi, które można produkować po wyprodukowaniu gotowego produktu. Wiele produktów można wytwarzać z tych samych składników w różnych rozmiarach partii, w wielokrotności lub przy użyciu różnych uzysków. Można utworzyć wiele wersji formuły, według potrzeby.

Aby zarządzać wieloma aktywnymi wersjami formuły, należy użyć zakresów daty wejścia w życie lub pól ilości „od". Wiele aktywnych wersji formuły może istnieć tylko wtedy, gdy zakres dat i ilość „od” nie pokrywają się.

W przeciwieństwie do BOM, który jest często skojarzony z wieloma wersjami BOM, w formule istnieje zwykle tylko jedna wersja formuły. Należy pamiętać, że można aktywować tylko jedną wersję formuły dla wymiarów zapotrzebowań i ilości dla danego produktu. Jednakże wiele wersji formuły może istnieć z innych powodów i można wybrać je ręcznie podczas tworzenia zamówienia partii.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Zatwierdzanie i aktywowanie formuł oraz wersji formuł
Formuły i wersje formuł muszą zostać zatwierdzone przed użyciem do planowania i produkcji. Formuły są zwykle aktywowane przed użyciem. Jednakże podczas produkcji można wybrać wersję formuły, która jest zatwierdzona, ale nie uaktywniona.

Aby ułatwić zabezpieczenie formuły lub wersji formuły, można ustawić parametry **Zablokuj edycję** i **Zablokuj usuwanie zatwierdzenia** na stronie **Parametry kontroli produkcji**.

Jeżeli wybrano opcję **Zablokuje edycję**, a formuła jest zatwierdzona, żadnych pól w wierszach formuły nie można usunąć ani edytować. Jednakże po usunięciu zatwierdzenia formuły można usuwać i modyfikować wiersze formuły. Można także tworzyć nowe formuły i nowe wersje formuł.

Jeżeli wybrano opcję **Zablokuj usuwanie zatwierdzenia**, nie można usunąć zatwierdzenia zatwierdzonej formuły ani wersji formuły. Jednakże można tworzyć nowe formuły i nowe wersje formuł oraz usuwać aktywację wersji formuły.

Używając funkcji podpisu elektronicznego, można dodać więcej poziomów kontroli. Jeżeli użytkownik jest skonfigurowany tak, że w momencie zatwierdzania formuły wymagany jest podpis elektroniczny, po uaktywnieniu formuły wyświetlana jest strona **Podpis**. Przed wprowadzeniem zmiany użytkownik musi być uprawniony do elektronicznego podpisywania, a poprawność certyfikatu musi zostać pomyślnie sprawdzona. Jeżeli nie można uwierzytelnić podpisu, zatwierdzenie lub usunięcie zatwierdzenia jest zabronione, a zmiana, która zainicjowała zatwierdzenie lub usunięcie zatwierdzenia jest przywracana do pierwotnego stanu.

## <a name="use-the-scalable-feature"></a>Korzystanie z funkcji Skalowalne
Funkcja Skalowalne jest dostępna tylko wtedy, gdy wszystkie składniki towaru w formule są ustawione na **Zmienne zużycie**. Ta funkcja jest niedostępna, jeżeli składniki towaru są ustawione na **Stałe zużycie** lub **Zużycie etapowe**. Jeżeli używana jest funkcja skalowalne, zmiana składnika w formule spowoduje również dostosowanie ilości wybranych składników. Koryguje się również rozmiar formuły. Podobnie w przypadku zmiany rozmiaru formuły zmienia się ilość skalowalnych składników. Ta funkcja jest przeznaczona do tworzenia i obsługi formuły. Nie wskazuje, czy ilość składnika będzie skalowana w górę lub w dół w zamówieniu partii.

## <a name="use-step-consumption"></a>Korzystanie ze zużycia etapowego
Zużycie etapowe eliminuje konieczność wprowadzania ilości na karcie **Wiersz formuły** dla składnika. Zamiast tego konfigurowana jest funkcja Zużycie etapowe z wartościami **Od serii** i **Ilość**. Wybierane są informacje ze zużycia etapowego na rekord serii, które są zgodne z ilością w zamówieniu partii. Zużycie etapowe jest przydatne, gdy wielkość zużycia nie jest liniowa względem rozmiaru zamówienia partii i zwiększa wymaganie dopiero po osiągnięciu określonego progu ilości. Aby włączyć tę funkcję dla nowej formuły, w grupie **Obliczanie zużycia** zmień ustawienie formuły dla odpowiedniego składnika ze **Standardowe** na **Etapowe**. Tę metodę zużycia należy określić na karcie **Konfiguracja** strony **Wiersz formuły**.
