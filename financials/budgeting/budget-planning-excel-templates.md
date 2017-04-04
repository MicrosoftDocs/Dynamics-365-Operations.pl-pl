---
title: "Szablony planowania budżetu do programu Excel"
description: "W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane z planów budżetu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Szablony planowania budżetu do programu Excel

W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane z planów budżetu.

W tym temacie pokazuje, jak utworzyć szablony programu Excel, które będą używane z planami budżetu przy użyciu zestawu danych standardowych demo i zalogowanie się jako użytkownik Admin. Aby uzyskać więcej informacji na temat planowania budżetu, zobacz [omówienie planowania budżetu.](budget-planning-overview-configuration.md) Można również śledzić [101 planowanie budżetu](budget-plan.md) samouczka, aby dowiedzieć się podstawowy moduł zasad konfiguracji i użytkowania.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generowanie arkusza przy użyciu układ dokumentu planu budżetu
Dokumenty planu budżetu można wyświetlać i edytować za pomocą jednego lub więcej układów. Każdy układ może mieć szablon dokumentu planu budżetu skojarzone do wyświetlania i edytowania danych planu budżetu w arkuszu programu Excel. W tym temacie szablonu dokumentu planu budżetu zostanie wygenerowany przy użyciu istniejącej konfiguracji układu. Otwórz **listy planów budżetu** (**Budżetowanie**&gt;**plany budżetu**). Kliknij **nowy** Aby utworzyć nowy dokument planu budżetu. [![bpt1](./media/bpt11-1024x552.png)](./media/bpt11.png) 

Użyj **Dodaj** linii opcję, aby dodać wiersze. Kliknij **układy** do wyświetlania konfiguracji układu dokumentu planu budżetu. 
[![bpt2](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Można przeglądać konfigurację układu i dostosuj je w razie potrzeby. Przejdź do **szablon**&gt;**Generuj** do tworzenia pliku programu Excel dla tego układu. Po wygenerowaniu szablonu, przejdź do **szablon**&gt;**widoku** otworzyć i przejrzeć szablonu dokumentu planu budżetu. Plik programu Excel można zapisać na dysk lokalny. [![bpt3](./media/bpt3-1024x545.png)](./media/bpt3.png) 

> [!NOTE] 
> Nie można edytować układu dokumentu planu budżetu, po szablonu programu Excel jest z nim skojarzony. Aby zmodyfikować układ, należy usunąć skojarzony plik szablonu programu Excel i ją wygenerować. Jest to wymagane, aby zachować pola w układzie i zsynchronizowane arkusza. 

Szablon programu Excel będzie zawierać wszystkie elementy z układu dokumentu planu budżetu, gdzie **dostępne w arkuszu** kolumny jest ustawiona na True. Nakładających się elementów są niedozwolone w szablonie programu Excel. Na przykład jeśli układ zawiera Q1 żądania, żądanie Q2, Q3 żądania i Q4 żądania kolumn i kolumny prosi o łączną kwotę, która reprezentuje sumę wszystkich kolumn kwartalnych 4, tylko kolumny kwartalnych lub całkowite kolumn jest dostępny do użycia w szablonie programu Excel. Plik programu Excel nie można zaktualizować kolumny nakładających się podczas aktualizacji, ponieważ dane w tabeli może stać się nieaktualne lub nieprawidłowe.

[![bpt4](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Aby uniknąć potencjalnych problemów z wyświetlania i edytowania danych planu budżetu za pomocą programu Excel, powinny być rejestrowane tego samego użytkownika do obu 365 Dynamics dla operacji i łącznika danych dodatek Microsoft Dynamics Office.

## <a name="add-a-header-to-budget-plan-document-template"></a>Dodać nagłówek do szablonu dokumentu planu budżetu
Aby dodać informacje nagłówka, zaznacz górny wiersz w pliku programu Excel i wstawić puste wiersze. Kliknij **projekt** w **Łącznik danych** do dodawania pól nagłówka do pliku programu Excel.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

W **projekt** kartę, ** ** kliknij **Dodaj** pól, a następnie wybierz **tabel BudgetPlanHeader** jako źródło danych jednostki.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Ustaw kursor w wybrane miejsce w pliku programu Excel. Kliknij **Dodaj etykietę** Aby dodać etykietę pola do wybranej lokalizacji. Wybierz **Dodaj wartość** dodać pole wartości do wybranego miejsca. Kliknij **Sporządzono** o zamknięcie projektanta.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Dodać kolumnę obliczeniową do tabeli Szablon dokumentu planu budżetu
--------------------------------------------------------------

Dalej, obliczonej kolumny zostaną dodane do szablonu dokumentu planu budżetu wygenerowane. A **prosi o łączną kwotę** kolumny, która zawiera podsumowanie Q1 żądania: kolumny Q4 żądania i **korekty** kolumna, która oblicza ponownie **prosi o łączną kwotę** kolumnę przez współczynnik.

Kliknij **projekt** w **Łącznik danych** Aby dodać kolumny do tabeli. Kliknij **edytować** obok **BudgetPlanWorksheet** źródła danych, aby rozpocząć dodawanie kolumn.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Grupa zaznaczone pole wyświetla kolumny, które są dostępne w szablonie. Kliknij **formuła** do dodania nowej kolumny. Nazwa nowej kolumny, a następnie wkleić formułę do **formuła** pole. Kliknij **aktualizacja** ją wstawić.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Aby zdefiniować formułę, tworzyć formuły w arkuszu kalkulacyjnym, a następnie skopiuj ją do **projekt** okna. 365 Dynamics dla operacji powiązania tabela będzie zazwyczaj o nazwie "AXTable1". Na przykład, aby podsumować Q1 żądania: żądanie Q4 kolumn w arkuszu kalkulacyjnym, formuła = AxTable1\[żądania Q1\]+ AxTable1\[żądania Q2\]+ AxTable1\[żądania Q3\]+ AxTable1\[żądania Q4\].

Powtórz te kroki, aby wstawić **regulacji** kolumny. Użyj formuły = AxTable1\[prosi o łączną kwotę\]\*$I$ 1 dla tej kolumny. Spowoduje to potrwać wartość w komórce I1 i mnożenie wartości w **prosi o łączną kwotę** kolumny do obliczania kwot korekty.

Zapisz i zamknij plik programu Excel. Wróć do Dynamics 365 dla operacji i w **układy**, kliknij przycisk **szablon &gt;przekazać** przekazać zapisanego szablonu programu Excel ma być używany dla planu budżetu. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Zamknij **układy** suwak. W **planu budżetu** dokumentu, kliknij przycisk **arkusza** do przeglądania i edycji dokumentów w programie Excel. Należy zauważyć, że skorygowana szablon programu Excel został użyty do utworzenia tego arkusza planu budżetu i kolumn obliczeniowych są aktualizowane za pomocą formuł, które zostały zdefiniowane w poprzednich krokach. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Wskazówki i porady dotyczące tworzenia szablonów planu budżetu
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Można dodawać i użyć dodatkowych źródeł danych do szablonu planu budżetu?

Tak, można użyć **projekt** menu, aby dodać dodatkowe obiekty do tej samej lub innych arkuszy w szablonie programu Excel. Na przykład, można dodać **BudgetPlanProposedProject znajdują** źródła danych do tworzenia i obsługi listy proponowanych projektów w tym samym czasie, kiedy praca z budżetu plan danych w programie Excel. Należy zauważyć, że w tym źródła danych dużej może mieć wpływ na wydajność skoroszytu programu Excel. 

Można użyć **filtr** opcji w **Łącznik danych** Aby dodać żądane filtry do dodatkowych źródeł danych.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Można ukryć opcji Projekt w złącze danych dla innych użytkowników?

Tak, otwórz **Łącznik danych** opcje, aby ukryć **projekt** opcji od innych użytkowników.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Rozwiń węzeł **opcje łącznika danych** i wyczyść **włączyć projekt** pole wyboru. Spowoduje to ukrycie **projekt** opcję **Łącznik danych**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Można uniemożliwić użytkownikom z przypadkowo zamknięcia Łącznik danych podczas pracy z danymi?

Firma Microsoft zaleca blokowanie szablon, aby zabezpieczyć przed jego zamknięciem. Aby włączyć funkcję blokady, kliknij przycisk **Łącznik danych**, w prawym górnym rogu pojawia się strzałka. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Kliknij strzałkę obok menu dodatkowych. Wybierz **blokady**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Czy mogę używać innych funkcji programu Excel, takich jak formatowanie komórek, kolorów, formatowanie warunkowe i wykresy z Moje szablony planu budżetu

Tak, większość standardowych funkcji programu Excel będzie działać w szablony planu budżetu. Zalecane jest użycie kodowanie kolorami dla użytkowników do rozróżniania między kolumnami tylko do odczytu i edycji. Formatowania warunkowego można wyróżnić obszary problematyczne budżetu. Sumy kolumn można łatwo przedstawiane za pomocą standardowych formuł programu Excel nad tabelą.

Można również tworzyć i używać tabel przestawnych i wykresów do dodatkowych grup i wizualizacji danych budżetu. Na **danych** kartę w **połączenia** grupy, kliknij przycisk **Odśwież wszystko**, a następnie kliknij przycisk **właściwości połączenia**. Kliknij **użycie** kartę. Pod **Odśwież**, wybierz opcję **odświeżanie danych podczas otwierania pliku** pole wyboru. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)


