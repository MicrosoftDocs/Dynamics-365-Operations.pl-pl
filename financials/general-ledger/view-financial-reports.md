---
title: "Wyświetlanie raportów finansowych"
description: "W tym artykule opisano sposób wyświetlania i eksplorowania sprawozdań finansowych w systemie Microsoft Dynamics AX. Artykuł zawiera informacje dotyczące różnych opcji, które można zastosować do sprawozdań finansowych, aby zmienić ich wygląd i zawarte dane."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8b02dbc0181c08611674cdf571075c20d78cebdc
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="view-financial-reports"></a>Wyświetlanie raportów finansowych

[!include[banner](../includes/banner.md)]


W tym artykule opisano sposób wyświetlania i eksplorowania sprawozdań finansowych w systemie Microsoft Dynamics AX. Artykuł zawiera informacje dotyczące różnych opcji, które można zastosować do sprawozdań finansowych, aby zmienić ich wygląd i zawarte dane.

<a name="financial-reporting-overview"></a>Omówienie raportowania finansowego
----------------------------

## <a name="open-a-financial-report"></a>Otwieranie raportu finansowego
Aby otworzyć raport, należy wybrać nazwę raportu. Kiedy raport zostanie otwarty po raz pierwszy, zostanie automatycznie wygenerowany raport za poprzedni miesiąc. Na przykład jeśli raport zostanie otwarty po raz pierwszy w sierpniu 2015, jest generowany raport na 31 lipca 2015 r. Po otwarciu raportu, możesz zapoznać się ze szczegółowymi danymi i opcjami modyfikacji.

## <a name="drill-down-on-a-financial-report"></a>Przechodzenie do raportu finansowego
Raporty finansowe mogą zawierać wiele poziomów szczegółów. Poziom finansowy to pierwszy poziom widoczny po otwarciu raportu finansowego. Aby przejść do poziomu kont, należy wybrać dane do wglądu. Na przykład aby wyświetlić szczegóły konta sprzedaży, wybierz dane sprzedaży, które chcesz zbadać. Z poziomu konta można wyświetlać bardziej szczegółowe dane transakcji składowych salda konta. Istnieją dwa sposoby wyświetlania transakcji: zgłaszane transakcje i transakcje na załączniku.

-   **Transakcje raportu** — transakcje zostaną wyświetlone w widoku sformatowanym w raporcie finansowym. Aby wyświetlić transakcje w widoku sformatowanym, zaznacz dane do Przechodzenie do, a następnie kliknij przycisk **przejdź niżej do poziomu transakcji raportu**.
-   **Transakcje na załączniku** — zostanie otwarte zapytanie o transakcje załącznika, zawierające transakcje. Aby wyświetlić transakcje w zapytaniu o transakcje załącznika, zaznacz dane do zbadania, a następnie kliknij przycisk **Otwórz transakcje na koncie**.

Jeśli dane są danymi budżetu, można otworzyć zapisy na koncie budżetu. Aby zamknąć dowolny poziom raportu i wrócić do miejsca, od którego zaczęto przeglądanie, należy nacisnąć klawisz Esc lub kliknąć przycisk **Zamknij** przycisk (**X**) w prawym górnym rogu.

## <a name="change-report-options"></a>Zmiana opcji raportu
Możesz zmienić dane raportu, dodać atrybuty i filtry wymiarów lub zmienić scenariusz budżetu w raporcie **Wartości rzeczywiste i budżet**. W okienku akcji kliknij **opcje raportów**, a następnie wykonaj jedną lub więcej z następujących czynności:

-   Aby zmienić podstawowe okres i rok bazowy raportu, wybierz okres bazowy i rok bazowy, a następnie kliknij **OK**.
-   Aby zastosować filtry atrybutu do raportu, zaznacz **Dodaj filtr atrybutu**. Wybierz atrybut, wpisz wartość atrybutu, a następnie kliknij **OK**. Na przykład, jeśli wybierzesz atrybut **kategoria konta**, wprowadź **sprzedaż** jako wartość atrybutu. Aby usunąć filtr atrybutów, kliknij **wyczyść**.
-   Aby zastosować filtry wymiarów do raportu, zaznacz opcję **Dodaj filtr wymiarów**. Wybierz wymiar, a następnie wpisz identyfikator wymiaru lub wybierz wymiar z listy. Aby usunąć filtr atrybutów, kliknij **wyczyść**.
-   Aby zmienić scenariusz w raporcie **Wartości rzeczywiste i budżet**, wybierz nowy scenariusz, a następnie kliknij **OK**. Jeśli wybrano scenariusz inny rok, należy zaktualizować rok bazowy. Na przykład, jeśli bieżący scenariusz dotyczy roku obrachunkowego 2015, i wybierzesz nowy scenariusz na 2016 r., zmień rok bazowy na **2016**.

Po kliknięciu przycisku **OK**, wybrane opcje są stosowane do raportu. Jeśli nie chcesz zastosować wybranych opcji, kliknij przycisk **Anuluj**.

## <a name="update-a-financial-report"></a>Aktualizacja raportu finansowego
Można odświeżyć raport (aktualizacja) finansowy, aby zawierał dane dla okresu i rok, za który wygenerowano raport. Na przykład w przypadku aktualizacji raportu finansowego, który został wygenerowany za październik 2015 r., raport będzie zawierał wszystkie nowe transakcje zaksięgowane w październiku 2015 r. Aby zaktualizować raport finansowy, w okienku akcji kliknij **Odśwież**. Zaktualizowany raport jest dostępny tylko dla osoby, która go zaktualizowała. Aby inne osoby mogły zobaczyć takie same dane, należy opublikować raportu.

## <a name="publish-a-financial-report"></a>Publikowanie raportu finansowego
Po dokonaniu aktualizacji raportu finansowego, można go opublikować. Inne osoby w organizacji będzie mogły go wyświetlać. Aby opublikować raport, w okienku akcji kliknij przycisk **Opublikuj**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Wyświetlanie raportu finansowego w innej walucie
Raport finansowy może być wyświetlany w dowolnej walucie w dowolnym momencie. Aby wyświetlić raport w innej walucie, w okienku akcji kliknij przycisk **Waluty**, a następnie wybierz walutę. Raport jest przeliczany na tę walutę, a wyniki są wyświetlane. Wszelkie kody walut lub symbole, które są uwzględniane jako część projektu raportu, są aktualizowane w celu odzwierciedlenia nowej waluty. Waluty, które są wyświetlane na liście, są walutami raportowania, które są skonfigurowane w systemie Microsoft Dynamics AX.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Wyświetlanie sumarycznego widoku raportu finansowego
Raport finansowy może zawierać wiersze szczegółów i wiersze zestawień. Wiersze szczegółów to wiersze, które zawierają konta głównego i wymiary. Wiersze zestawień to wiersze opisu, sumy i obliczeń. Aby wyświetlić tylko wiersze podsumowania raportu, kliknij przycisk **Pokaż**, a następnie kliknij przycisk **Tylko wiersze podsumowania**. Raport jest zwinięty i wyświetla tylko wiersze podsumowania. Aby wyświetlić wiersze szczegółów wraz z wierszami zestawień, kliknij **Pokaż**, a następnie kliknij ponownie przycisk **Tylko wiersze podsumowania**.

## <a name="open-a-financial-report-from-a-previous-month"></a>Otwieranie raport finansowego z poprzedniego miesiąca
Raporty można wyświetlać dla bieżącego miesiąca lub poprzednich miesięcy bez ponownego generowania raportu. Aby otworzyć raport dla poprzedniego miesiąca, kliknij przycisk **Pokaż**, a następnie kliknij przycisk **Poprzednie raporty**. Zostanie wyświetlona lista wcześniejszych miesięcy, dla których wygenerowano raport. Rozwiń miesiąc, dla którego chcesz wyświetlić raport, wybierz datę, a następnie kliknij **OK**. Wyświetlany jest raport za poprzedni miesiąc. Aby powrócić do raportu bieżącego miesiąca, kliknij **Anuluj**.

## <a name="print-a-financial-report"></a>Drukowanie raportu finansowego
Aby wydrukować raport finansowy w okienku akcji kliknij **Drukuj**, a następnie wykonaj jeden lub więcej z tych kroków, aby ustawić opcje drukowania:

-   Aby uwzględnić różne poziomy szczegółów w wydrukowanym raporcie, ustaw suwak na **Tak** lub **Nie**. Jeśli raport używa drzewa raportowania, można uwzględnić wszystkie jednostki raportowania lub tylko bieżącą jednostkę raportowania.
-   Aby ustawić rozmiar strony, wybierz rozmiar strony z listy.
-   Aby ustawić układ strony, wybierz układ z listy. Jeśli chcesz, by zawartość raportu pasowała do wybranej szerokości, ustaw suwak na **Tak**.
-   Aby ustawić marginesy strony, wpisz rozmiar marginesów górnego, dolnego, lewego i prawego w calach.

Po zakończeniu ustawiania opcji drukowania, kliknij przycisk **Druku** w celu wydrukowania raportu. Jeśli nie chcesz drukować raportu, kliknij zamiast tego przycisk **Anuluj**. Zostanie wyświetlony podgląd drukowanego raportu. Można wybrać, aby wysłać raport do drukarki, a także dostosować opcje drukowania.

## <a name="export-a-financial-report"></a>Eksportowanie raportu finansowego
Aby wyeksportować raport finansowy, w okienku akcji kliknij **Eksportuj**. Raport jest eksportowany do programu Microsoft Excel, a Twoja przeglądarka wyświetli monit o otwarcie lub zapisanie wyeksportowanego pliku. Ustawienia eksportu zdefiniowane w projekcie raportu są stosowane do wyeksportowanego raport.    

<a name="see-also"></a>Informacje dodatkowe
--------

[Raportowanie finansowe w systemie Microsoft Dynamics AX](/dynamics365/operations/dev-itpro/analytics/financial-reporting-intro)




