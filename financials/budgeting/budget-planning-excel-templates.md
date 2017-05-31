---
title: "Szablony planowania budżetu dla programu Excel"
description: "W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane w planach budżetu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 93aa0aeffad0411542f36e27745f63198c4438b2
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="budget-planning-templates-for-excel"></a>Szablony planowania budżetu dla programu Excel

[!include[banner](../includes/banner.md)]


W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane w planach budżetu.

W tym temacie pokazano, jak tworzyć szablony programu Excel przeznaczone dla planów budżetu, wykorzystując do tego standardowy zestaw danych demonstracyjnych i logowanie użytkownika będącego administratorem. Aby uzyskać więcej informacji na temat planowania budżetu, zobacz [Przegląd planowania budżetu.](budget-planning-overview-configuration.md) Można również przejść samouczek [Planowanie budżetu 101](budget-plan.md), który przekazuje podstawowe informacje o konfiguracjach modułu i zasadach użytkowania.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generowanie arkusza przy użyciu układu dokumentu planu budżetu
Dokumenty planu budżetu można wyświetlać i edytować za pomocą jednego lub więcej układów. Z każdym układem może być skojarzony szablon dokumentu planu budżetu, który umożliwia wyświetlanie i edytowanie danych planu budżetu w arkuszu programu Excel. W tym temacie szablon dokumentu planu budżetu zostanie wygenerowany przy użyciu istniejącej konfiguracji układu. Otwórz **listę planów budżetu** (**Budżetowanie**&gt; **Plany budżetu**). Kliknij przycisk **Nowy**, aby utworzyć nowy dokument planu budżetu. [![bpt1](./media/bpt11-1024x552.png)](./media/bpt11.png) 

Za pomocą opcji wierszy **Dodaj** dodaj wiersze. Kliknij opcję **Układy**, aby wyświetlić konfigurację układu dokumentu planu budżetu. 
[![bpt2](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Możesz przejrzeć konfigurację układu i dostosować ją w razie potrzeby. Wybierz kolejno opcje **Szablon** &gt; **Generuj**, aby utworzyć plik programu Excel dla tego układu. Po wygenerowaniu szablonu przejdź do opcji **Szablon** &gt; **Widok** i otwórz oraz przejrzyj szablon dokumentu planu budżetu. Plik programu Excel można zapisać na lokalnym dysku. [![bpt3](./media/bpt3-1024x545.png)](./media/bpt3.png) 

> [!NOTE] 
> Nie można edytować układu dokumentu planu budżetu, gdy zostanie z nim skojarzony szablon program Excel. Aby zmodyfikować układ, należy usunąć skojarzony plik szablonu programu Excel i wygenerować układ ponownie. Jest to niezbędne, aby zachować synchronizację pól w układzie i arkuszu. 

Szablon programu Excel będzie zawierał wszystkie elementy z układu dokumentu planu budżetu, gdzie kolumna **Dostępny w arkuszu** jest ustawiona na Prawda. Nakładające się elementy są niedozwolone w szablonie programu Excel. Na przykład jeśli układ zawiera kolumny Wniosek K1, Wniosek K2, Wniosek K3 i Wniosek K4 oraz kolumnę łącznej kwoty wniosku reprezentującą sumę wszystkich 4 kolumn kwartalnych, w szablonie programu Excel do użycia będą dostępne tylko indywidualne kolumny kwartalne lub kolumna wartości łącznej. Podczas aktualizacji nie można zaktualizować nakładających się kolumn w pliku programu Excel, ponieważ dane w tabeli mogłyby stać się nieaktualne i błędne.

[![bpt4](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Aby uniknąć potencjalnych problemów z wyświetlaniem i edytowaniem danych planu budżetu za pomocą programu Excel, ten sam użytkownik powinien być zalogowany w programie Dynamics 365 for Operations oraz łączniku danych dodatku pakietu Office dla usługi Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Dodawanie nagłówka do szablonu dokumentu planu budżetu
Aby dodać informacje nagłówka, zaznacz górny wiersz w pliku programu Excel i wstaw puste wiersze. W obszarze **Łącznik danych** kliknij opcję **Projekt** i dodaj pola nagłówka do pliku programu Excel.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

Na karcie **Projekt** kliknij** **pola **Dodaj**, a następnie wybierz pozycję **BudgetPlanHeader** jako źródło danych jednostki.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Ustaw kursor w żądanym miejscu w pliku programu Excel. Kliknij przycisk **Dodaj etykietę**, aby dodać etykietę pola w wybranym miejscu. Kliknij przycisk **Dodaj wartość**, aby dodać pole wartości w wybranym miejscu. Kliknij przycisk **Gotowe**, aby zamknąć projektanta.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Dodawanie kolumny obliczanej do tabeli szablonu dokumentu planu budżetu
--------------------------------------------------------------

Następnie kolumny obliczane zostaną dodane do wygenerowanego szablonu dokumentu planu budżetu. Kolumna **Wniosek razem**, która sumuje wartości kolumn od Wniosek K1 do Wniosek K4, oraz kolumna **Korekta**, która przelicza wartość w kolumnie **Wniosek razem** o ustawiony wcześniej współczynnik.

W obszarze **Łącznik danych** kliknij opcję **Projekt** i dodaj kolumny do tabeli. Obok źródła danych **BudgetPlanWorksheet** kliknij przycisk **Edytuj**, aby rozpocząć dodawanie kolumn.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Wybrana grupa pól pokazuje kolumny dostępne w szablonie. Kliknij przycisk **Formuła**, aby dodać nową kolumnę. Nazwij nową kolumnę, a następnie wklej wzór do pola **Formuła**. Kliknij przycisk **Aktualizuj**, aby wstawić kolumnę.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Aby zdefiniować formułę (wzór), utwórz ją w arkuszu kalkulacyjnym, a następnie skopiuj do okna **Projekt**. Tabela powiązania z programem Dynamics 365 for Operations zazwyczaj nosi nazwę „AXTable1”. Na przykład aby podsumować kolumny Wniosek K1: Wniosek K4 w arkuszu kalkulacyjnym, formuła ma postać = AxTable1\[Wniosek K1\]+AxTable1\[Wniosek K2\]+AxTable1\[Wniosek K3\]+AxTable1\[Wniosek K4\].

Powtórz te kroki, aby wstawić kolumnę **Korekta**. Dla tej kolumny użyj formuły = AxTable1\[Wniosek razem\]\*$I$1. Spowoduje to pobranie wartości z komórki I1 i pomnożenie jej przez wartości z kolumny **Wniosek razem** w celu obliczania kwot korekt.

Zapisz i zamknij plik programu Excel. Wróć do programu Dynamics 365 for Operations i w obszarze **Układy** kliknij kolejno opcje **Szablon &gt; Przekaż**, aby przekazać zapisany szablon programu Excel przeznaczony do używania w planie budżetu. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Zamknij suwak **Układy**. W dokumencie **Plan budżetu** kliknij opcję **Arkusz**, aby wyświetlić i edytować dokument w programie Excel. Należy zauważyć, że do utworzenia tego arkusza planu budżetu został użyty skorygowany szablon programu Excel, a kolumny obliczane są aktualizowane przy użyciu formuł zdefiniowanych w poprzednich krokach. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Porady i wskazówki dotyczące tworzenia szablonów planu budżetu
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Czy można dodać i używać więcej źródeł danych do szablonu planu budżetu?

Tak, za pomocą menu **Projekt** można dodać więcej jednostek do tego samego lub innych arkuszy w szablonie programu Excel. Na przykład można dodać źródło danych **BudgetPlanProposedProject**, aby utworzyć i prowadzić listę proponowanych projektów w tym samym czasie, kiedy pracujesz z danymi planu budżetu w programie Excel. Należy zauważyć, że dołączenie dużych źródeł danych może mieć negatywny wpływ na działanie skoroszytu programu Excel. 

Można użyć opcji **Filtr** w obszarze **Łącznik danych**, aby dodać żądane filtry do dodatkowych źródeł danych.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Czy można ukryć opcję Projekt w obszarze Łącznik danych dla innych użytkowników?

Tak, otwórz opcje narzędzia **Łącznik danych** i tam można schować opcję **Projekt** przed innymi użytkownikami.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Rozwiń opcje narzędzia **Łącznik danych** i wyczyść pole wyboru **Włącz projekt**. Opcja **Projekt** przestanie być widoczna w obszarze **Łącznik danych**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Czy można uniemożliwić użytkownikom przypadkowe zamknięcie łącznika danych podczas pracy z danymi?

Zalecamy zablokowanie szablonu, aby uniemożliwić użytkownikom jego zamknięcie. Aby włączyć blokadę, kliknij przycisk **Łącznik danych** w prawym górnym rogu. Pojawi się strzałka. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Kliknij strzałkę, a pojawi się dodatkowe menu. Wybierz opcję **Blokowanie**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Czy w moich szablonach planu budżetu mogę używać innych funkcji programu Excel, takich jak formatowanie komórek, kolory, formatowanie warunkowe i wykresy?

Tak, większość standardowych funkcji programu Excel będzie działać w szablonach planu budżetu. Zalecamy użytkownikom stosowanie kolorów do rozróżniania między kolumnami tylko do odczytu i edytowalnymi. Formatowanie warunkowe może służyć do wyróżniania problematycznych obszarów budżetu. Sumy kolumn można łatwo przedstawiać za pomocą standardowych formuł programu Excel nad tabelą.

Można również tworzyć i używać tabel i wykresów przestawnych w celu dodatkowego grupowania i wizualizacji danych budżetu. Na karcie **Dane** w grupie **Połączenia** kliknij przycisk **Odśwież wszystko**, a następnie kliknij opcję **Właściwości połączenia**. Kliknij kartę **Użycie**. W obszarze **Odśwież** zaznacz pole wyboru **Odśwież dane podczas otwierania pliku**. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)




