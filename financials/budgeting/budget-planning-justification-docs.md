---
title: "Dokumenty uzasadniające planowania budżetu"
description: "Dokumenty uzasadniające dostarczają narracji dla osób żąda budżetu, aby wyjaśnić, dlaczego niezbędne jest konkretny budżet."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Dokumenty uzasadniające planowania budżetu

Dokumenty uzasadniające dostarczają narracji dla osób żąda budżetu, aby wyjaśnić, dlaczego niezbędne jest konkretny budżet. 

Szablon planu budżetu jest tworzone przez menedżera budżetu w programie Microsoft Word i przypisany do bieżącego procesu planowania budżetu. Budżet właściciele można następnie otworzyć szablon i mieć dane automatycznie wypełniane w programie Word na podstawie swojej propozycji budżetu. Można następnie dodać dodatkowy tekst lub dane przed zapisaniem i dołączania ich dokumentu spersonalizowane uzasadnienia do ich planu budżetu.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Ustawienia dodatek Microsoft Dynamics Office dla programu Microsoft Word

1.  Otwórz nowy dokument programu Microsoft Word.
2.  Kliknij **Wstaw** na Wstążce, a następnie kliknij **sklep**.
3.  Wyszukaj dodatek Microsoft Dynamics Office i kliknij przycisk **Dodaj**.
4.  W programie Word, w prawym okienku kliknij **dodać informacje o serwerze**.
5.  Wpisz lub wklej adres URL serwera i kliknij przycisk **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definiowanie szablonu uzasadnienia w programie Microsoft Word

1.  Kliknij **projekt** w dodatek Microsoft Dynamics Office po zalogowaniu.
2.  Informacje nagłówka, można użyć **dodać pola** przycisk.
3.  Wybierz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **dalej**. **Uwaga:** tego podmiotu nie jest wymagane dla każdego dokumentu uzasadnienia. Inne podmioty mogą być używane, ale przekazywania do usługi Microsoft Dynamics 365 dla operacji zakończy się niepowodzeniem, jeśli ta encja nie jest uwzględniana.
4.  W dokumencie programu Word, należy dodać BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter i DocumentNumber etykiety i wartości. **Uwaga:** w razie potrzeby można użyć etykiet niestandardowych, zamiast standardowych etykiet.
5.  Kliknij **Sporządzono** do wykonania sekcji nagłówka.
6.  Aby uzyskać poziom szczegółów wiersza kwot planu budżetu, kliknij **Dodaj tabelę**.
7.  Ponownie, wybierz źródło danych jednostki BudgetPlanJustification i kliknij przycisk **dalej**.
8.  Dodaj pola do EffectiveDate, ScenarioName, AccountDisplayValue i AccountingCurrencyExpenseAmount. **Uwaga:** Jeśli komentarze są dostępne do dodania w obrębie wierszy planu budżetu indywidualnych, te można dodać do tabeli w tym miejscu.
9.  Dodaj dodatkowymi instrukcjami, aby zapewnić użytkownikowi końcowemu i wykonywać niezbędne formatowanie lub style w dokumencie.
10. Zapisz dokument na komputer lokalny i zamknij plik przed kontynuowaniem.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Skonfigurować proces planowania budżetu do używania Szablon uzasadnienia

1.  W programie Microsoft Dynamics 365 dla operacji, przejdź do **Budżetowanie**&gt;**instalacji**&gt;**planowania budżetu**&gt;**szablony dokumentów uzasadnienie**.
2.  Kliknij **nowy** i przejdź do nowo utworzonego dokumentu programu Microsoft Word.
3.  Wprowadź nazwę wyświetlaną szablonu i opis. Click **OK**.
4.  Przejdź do **Budżetowanie**&gt;**instalacji**&gt;**budżetu****planowania**&gt;**proces planowania budżetu**.
5.  Wybierz proces, gdzie należy stosować szablon uzasadnienia i kliknij przycisk **edytować**.
6.  W **szablon dokumentu uzasadnienia** pól, wybierz odpowiedni szablon i Zapisz.

##### <a name="edit-and-save-personalized-justification-documents"></a>Edytować i zapisywać dokumenty uzasadniające spersonalizowane

1.  W usłudze Dynamics 365 dla operacji Tworzenie nowego planu budżetu lub Otwórz istniejący plan budżetu.
2.  W **uzasadnienie** menu rozwijanego, wybierz **Tworzenie nowego uzasadnienia**.
3.  Po wypełnieniu pól szczegółów, zaznacz, aby przekazać dokument spersonalizowane ze **uzasadnienie** menu rozwijanego.



